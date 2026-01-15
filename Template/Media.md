#meta

# Media Template

```space-lua
function mediaTemplate(items)
  local domElements = {};
  for _, item in ipairs(items) do
    print(item.poster);
    table.insert(domElements, dom.div {
      dom.img { src = item.poster; };
      dom.strong { item.name; };
    })
  end
  return domElements 
end