Quick and dirty Jai lsp/tree-sitter for Zed. Need to have Jails compiled and on your path for this to work.

Before compiling Jails replace the line where server.project_root is set with:

```
if (body.params.rootPath != null) {
    log("Root Path: %", body.params.rootPath.*);
    server.project_root = body.params.rootPath.*;
}
```

in the handle_request function in Jails's main.jai. body.params.rootPath ends up being null and causes a crash if you don't put the gaurd here. Might cause some issues, but it seems to work without that value being set if you have Zed open at the root of your project.
