#meta

# Media Template

```space-lua
function mediaTemplate(media)
  local tree = string.split(media.page, "/");
  local page = string.lower(tree[#tree]);
  return dom.div {
    class = "media " .. page;
    dom.a {
      dom.img { src = media.poster; class = "poster " .. page; };
      href = media.url;
      target = "_blank";
    };
    dom.br {};
    dom.a { media.name; class = "text title " .. page; href = media.url; target = "_blank" };
    dom.div { 
      "Status: " .. media.status;
      class = "text " .. page; 
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

.games .poster {
  width: 100%;
  height: 100%;
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
