#meta 

```space-lua

slashcommand.define {
  name = "imdb";
  run = function()
    local id = editor.prompt("Enter IMDB ID:");
    local cmd = shell.run("imdb", {id});
    if cmd.code != 0 then
      editor.flashNotification("IMDB Command Failed.")
      return
    end    
    editor.insertAtCursor(cmd.stdout, false, true);
  end
}

```