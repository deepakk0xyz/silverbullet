#meta

```space-lua
treeview = treeview or {}

function treeview.to_lines(tree, skip)
  local lines = {}
  for key, value in pairs(tree) do
    if key ~= "page" then
      local subtree = treeview.to_lines(value, skip-1)
      if skip <= 0 then
        if value.page ~= nil then
          table.insert(lines, "- [[" .. value.page.name .. 
                                "|" .. key .. "]]\n")
        else
          table.insert(lines, "- " .. key .. "\n")
        end
      end
      for _, item in ipairs(subtree) do
        if skip > 0 then
          table.insert(lines, item)
        else
          table.insert(lines, "  " .. item)
        end
      end
    end
  end
  return lines
end

function treeview.template(tbl, skip)
  skip = skip or 0
  local tree = {}
  for _, page in ipairs(tbl) do
    local current = tree
    for item in string.gmatch(page.name, "([^/$]+)") 
    do
      current.page = nil
      if current[item] == nil then
        current[item] = {page=page}
      end
      current = current[item]
    end
  end
  return table.concat(treeview.to_lines(tree, skip))
end
```
