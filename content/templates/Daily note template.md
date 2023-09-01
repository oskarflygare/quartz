# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>
#dailynote 

 [[<% tp.date.now("YYYY-MM-DD-ddd", -1, tp.file.title, "YYYY-MM-DD-ddd") %>]] | [[<% tp.date.now("YYYY-MM-DD-ddd", 1, tp.file.title, "YYYY-MM-DD-ddd") %>]]

---

# 📅 Micro-journal
- 

---

# 📝 Notes
- 

---

### Notes created today

```dataview

List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc

```

### Notes modified today

```dataview

List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc

```