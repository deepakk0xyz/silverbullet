#meta

# Media Template

```space-lua
function mediaTemplate(media)
  return dom.div {
    dom.img { src = media.poster; };
    dom.br {};
    dom.span { media.name; };
  };
end