---
aliases: []
created: 2022-09-07
updated: 2023-09-01
---

# Interrupt coalescing is built into the design of postal services
Date created: 2022-07-18

Interrupt coalescing is a way for computers to throttle interrupts so that a system does not spiral into [[Thrashing]].

[[In the day of the postman]] discusses our pre-internet rhythm.

The way our postal system works shows this principle:

> At human scale, we get interrupt coalescing for free from the postal system, just as a consequence of their delivery cycle. Because mail gets delivered only once a day, something mailed only a few minutes late might take an extra twenty-four hours to reach you. Considering the costs of context switching, the silver lining to this should by now be obvious: you can only get interrupted by bills and letter at most once a day. What's more, the twenty-four-hour postal rhythm demands minimal responsiveness from you: it doesn't make any difference whether you mail your reply five minutes or five hours after receiving a letter.

---
# References
* Link to website, bibtex from Zotero or note with book/blog/etc summary