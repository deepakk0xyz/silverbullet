---
priority: 2
tags:
  - home
---
# Want To Watch
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Shows"
      and status != "Watched"
      order by name
    ]])}
# Watched
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Shows"
      and status == "Watched"
      order by name
    ]])}
