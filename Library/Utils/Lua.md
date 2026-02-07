#meta 

```space-lua
-- priority: 100
utils = utils or {}

function utils.map(tbl, func)
  local result = {}
  for key, value in ipairs(tbl) do
    result[key] = func(value);
  end
  return result
end

function utils.map_with_key(tbl, func)
  local result = {}
  for key, value in ipairs(tbl) do
    result[key] = func(key, value)
  end
  return result
end

function string.split(str, sep)
  local result = {}
  for value in string.gmatch(str, "([^" .. sep .. "]+)") do
    table.insert(result, value)
  end
  return result
end
```
