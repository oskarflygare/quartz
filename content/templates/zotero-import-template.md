---
aliases:
  - "{% if shortTitle %} {{shortTitle | safe}} {% else %} {{title | safe}} {% endif %}"
tags:
  - article
title: "{{title}}"
created: 
updated:
---

---

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