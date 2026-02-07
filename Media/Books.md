---
priority: 2
tags:
  - home
---

# Want To Read
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Books"
      and status != "Read"
      order by name
    ]])}

# Read
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Books"
      and status == "Read"
      order by name
    ]])}
