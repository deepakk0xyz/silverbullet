---
priority: 2
tags:
  - home
---

${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Books"
      order by name
    ]])}
