# VSC R Debugger with renv

Creating the renv in a subfolder of the workspacefolder somehow makes the debugger not find installed packages.

## To Reproduce

Open the working and not-working folder each in VS Code.

### working

```
radian
renv::init()
renv::install()
```

### not-working

```
cd another-folder
radian
renv::init()
renv::install()
```

### then for both

Start 'Debug R-File' for the *.r file.
