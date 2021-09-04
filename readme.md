# VSC R Debugger with renv

Creating the renv in a *subfolder* of the workspacefolder somehow makes the debugger not find installed packages.

## To Reproduce

Open the working and not-working folder each in their own VS Code instance.

### working

Execute the following in the VS Code terminal.

```bash
radian
renv::init()
renv::install()
```

Start 'Debug R-File' for the `do_sth.r` file and see that the `tidytransit` package **can** be loaded.

### not-working

Execute the following in the VS Code terminal.

```bash
cd another-folder
radian
renv::init()
renv::install()
```

Start 'Debug R-File' for the `do_sth.r` file and see that the `tidytransit` package **cannot** be loaded.

```log
Error in library("tidytransit") : 
  there is no package called 'tidytransit'
```
