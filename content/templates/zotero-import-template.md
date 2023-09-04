---
alias: [{% if shortTitle %}"{{shortTitle | safe}}"{% else %}"{{title | safe}}"{% endif %}]
title: {{title}}
tags: #article 
---

- Date read: {{importDate | format("YYYY-MM-DD")}}
- Bibtex: @{{citekey}}
- Bibliography: {{bibliography}}

---
# Example citation


---
# My notes


---

# Abstract
{{abstractNote}}

{%- for attachment in attachments | filterby("path", "endswith", ".pdf") %}
PDF: [{{attachment.title}}](file://{{attachment.path | replace(" ", "%20")}})  
{%- endfor -%}