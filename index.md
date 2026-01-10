# Home

${treeview(query[[
  from index.tag "home"
  order by priority, name
  select {name=_.name, path=_.path}
]])}
 