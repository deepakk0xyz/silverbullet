#meta

```space-lua
function split_string(str, sep)
  local result = {}
  for value in string.gmatch(str, "([^" .. sep .. "]+)") do
    table.insert(result, value)
  end
  return result
end
```