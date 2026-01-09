#meta

```space-lua
-- priority: 10
function treeview(tbl)
  local result = {}
  for _, item in ipairs(tbl) do
    local path = item.path
    if string.find(item.path, "/") then
      path = string.gsub(path, "/", "-")
    end
    table.insert(
      result, 
      "- [[" .. item.name .. "|" .. path .. "]]\n"
    )
  end
  return table.concat(result)
end
```
