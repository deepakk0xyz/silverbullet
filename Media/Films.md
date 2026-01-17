---
priority: 2
tags:
  - home
---

${widget.html(
  dom.div(
    utils.map(query[[
      from index.tag "item"
      where page == "Data/Films"
      order by name
    ]], mediaTemplate)
  )
)}
