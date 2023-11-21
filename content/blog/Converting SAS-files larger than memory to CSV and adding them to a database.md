---
created: 2023-11-21
updated: 2023-11-21
tags:
  - writing/blog
  - python
  - DuckDB
draft: false
---
I'm used to working on data from clinical trials, which usually end up in small files that easily fit into memory of my laptop. I just load them into my statistical software and start my analyses.

For a new project we use data from Swedish nationwide registries, and the files ended up being *much* larger, often over 10GB. To add icing on the cake, the files were also in the `.sas7bdat` format from the statistical software SAS, which not available on MacOS. I was less than enthusiastic about firing up Windows using Boot Camp and decided to try to solve this issue using the available tools. Here, after much trial and error, is how I ended up doing it.

The full Python scripts I used are included at the end of the blog post if you want to re-use them. However, be aware that I am a beginner programmer and there are probably a ton of further optimizations to do. If you find something that works better, please let me know!

Many thanks to Robin who suggested DuckDB, and Jakob for encouraging me to dive into Python without any prior knowledge.
# The problem

- Plenty of `.sas7bdat` files exceeding available memory on my computer (16GB)
- No access to SAS
- End goal: have a solution that makes it easy to work with the files using R or Python

# My solution

- Read the SAS-files using *pandas* (100MB-1GB) or *pyreadstat* + *dask* (1GB and upwards)
	- Convert to *pandas* dataframe if necessary (DuckDB doesn't accept dask dataframes as of version 0.9.2)
- Write the dataframe to a *DuckDB* database
	- Export the database to `.csv` tables for long-term storage
- Interact with the tables of data by using the *DuckDB* API for R and Python
	- SQL commands directly or through translated *dplyr* verbs I am familiar with
- Bring manageable dataframes into memory for analysis and visualization after select/filter/join etc out of memory

## Some false starts

Here are some things I tried that didn't work out for one reason or the other. 

- I tried using the `read_sas()` function in the *haven* package in R, but couldn't find a good way to break up the large files into manageable chunks. Even though the function has arguments for chunks, it still seemed to read the entire file first to decide the number and size of chunks
- The *sas7bdat* package in Python could read large files but it didn't decode the SAS-files properly when converting to a pandas dataframe.

# Just the code, please

## Pandas import

The script I used for medium-sized files, 100MB to 1GB.

```python

# This one can be used for large-ish files (100MB to 1GB)
# But use dask-large-files.py for the really large files (1GB+)

# Import packages
import pandas as pd
import duckdb as duckdb
import time

start_time = time.time()

file_path = 'path_to_file.sas7bdat'

# Specify the chunk size (adjust based on available memory)
chunk_size = 800000

# Initialize an empty DataFrame to store the concatenated results
result_df = pd.DataFrame()

# Read the file in chunks
for chunk in pd.read_sas(file_path, chunksize=chunk_size):

	# Concatenate the chunk to the result DataFrame
	result_df = pd.concat([result_df, chunk], ignore_index=True)

print(result_df)

# Connect to DuckDB
con = duckdb.connect(database='name_of_database.db', read_only=False)

# Write dataframe to DuckDB
con.execute("CREATE TABLE name_of_table AS SELECT * FROM result_df")
  
# Close the connection
con.close()

# Time the script
end_time = time.time()

runtime = end_time - start_time

print(f"Script execution time: {runtime:.2f} seconds")

```

## Dask import

This is the script I used for the largest files, 1GB to ~30GB.

What ended up taking most of the time was converting the dask dataframe to pandas and writing it into DuckDB, so that's where I would try to make the code more efficient. Perhaps adjusting the chunk size or adding parallel processing.

```python

# %%
# Import packages
import pyreadstat
import dask.dataframe as dd
from dask.delayed import delayed
import duckdb
import os
import time
from datetime import datetime

# %%
start_time = time.time()

# %%
# Set working directory
new_dir = 'path_to_WD'
os.chdir(new_dir)

# %%
# Create chunks for reading the SAS file
def dask_sas_reader(filepath, chunksize):

	# Read metadata only of the SAS file in order to find out the number of rows
	_, meta = pyreadstat.read_sas7bdat(filepath, disable_datetime_conversion=True, metadataonly=True)

	# Helper function which reads a chunk of the SAS file
	def read_sas_chunk(offset):
		df, _ = pyreadstat.read_sas7bdat(filepath, disable_datetime_conversion=True, row_offset=offset, row_limit=chunksize)
		return df

	# Parallelize reading of chunks using delayed() and combine these in a dask dataframe
	dfs = [delayed(read_sas_chunk)(x) for x in range(0, meta.number_rows, chunksize)]
	return dd.from_delayed(dfs)

# %%
# Read using dask
dd_df = dask_sas_reader('path_to_file', chunksize=800000)

# %%
# Connect to DuckDB
con = duckdb.connect(database='database_name', read_only=False)

# %%
# Convert to pandas dataframe and write to DuckDB in chunks
chunk_size = 800000

# Get the list of delayed objects
delayed_dfs = dd_df.to_delayed()

	for i, delayed_df in enumerate(delayed_dfs):

	# Convert the delayed object to a Pandas DataFrame
	pandas_df = delayed_df.compute()

	# Write the DataFrame to DuckDB
	if i == 0:
		# If this is the first chunk, create a new table
		con.execute("CREATE TABLE name_of_table AS SELECT * FROM pandas_df")
	else:
		# If this is not the first chunk, append to the existing table
		con.execute("INSERT INTO name_of_table * FROM pandas_df")

	# Discard the Pandas DataFrame to free up memory
	del pandas_df

# %%
# Show the database tables
tables = con.execute("SHOW TABLES").fetchall()
print(tables)

# %%
# Close the connection
con.close()

# %%
end_time = time.time()

runtime = end_time - start_time

current_time = datetime.now().strftime("%H:%M:%S")

print(f'The script took {runtime:.2f} seconds to run and finished on {current_time}')

```

## Export to .csv files

Can be highly taxing for your computer if the database is large!

```python

import duckdb as duckdb
import os

# Set working directory
new_dir = 'path_to_WD'
os.chdir(new_dir)

# Connect to DuckDB
con = duckdb.connect(database='database_name.db', read_only=False)

# Export database to CSV
con.execute("EXPORT DATABASE 'name_of_folder'")

```