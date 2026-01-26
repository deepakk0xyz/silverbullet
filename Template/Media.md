#meta

# Media Template

```space-lua
function mediaTemplate(media)
  return dom.div {
    class = "media";
    dom.a {
      dom.img { src = media.poster; class = "poster"; };
      href = media.url;
      target = "_blank";
    };
    dom.br {};
    dom.a { media.name; class = "text title"; href = media.url; target = "_blank" };
    dom.div { 
      "Status: " .. media.status;
      class = "text"; 
    };
  };
end

function mediaWidget(q)
  local tbl = utils.map(q, mediaTemplate);
  tbl.class = "container";
  return widget.html(dom.div(tbl))
end
```

```space-style
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  flex: 1;
  justify-content: space-around;
  align-content: start;
  row-gap: 5em;
}

.media {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: start;
  position: relative;
}

.poster {
  width: 300px;
  height: 450px;
}

.text {
  display: flex;
  column-gap: 0px;
  text-wrap: wrap;
  width: 300px;
}

.title {
  font-weight: bold;
}

.title:link {
  text-decoration: none;
}

.media:hover > .edit {
  display: block;
}
```
