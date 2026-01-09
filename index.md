# Home

${treeview(query[[
  from index.tag "page"
  where path
  order by priority, name
  select {
    name=name, 
    priority=priority, 
    path=path
  }
]])}
