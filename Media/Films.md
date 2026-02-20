---
priority: 2
tags:
  - home
---

# Want To Watch
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Films"
      and status != "Watched"
      order by name
    ]])}
# Watched
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Films"
      and status == "Watched"
      order by name
    ]])}

