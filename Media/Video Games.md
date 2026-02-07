---
priority: 2
tags:
  - home
---
# Want To Play

${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Video Games"
      and status != "Finished"
      order by name
    ]])}

# Finished
${mediaWidget(query[[
      from index.tag "item"
      where page == "Library/Data/Video Games"
      and status == "Finished"
      order by name
    ]])}
