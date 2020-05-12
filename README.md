
# conda
```
$ cd ~/originals
$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ bash ~originals/Miniconda3-latest-Linux-x86_64.sh
```
Exit & re-enter shell (install adds a hook at end of `~/.bashrc`)

```
$ conda create --name foo ipython
$ conda info --envs
# conda environments:
base    *  /home/jgreve/miniconda3
foo        /home/jgreve/miniconda3/envs/exercism
$ conda activate foo
```
# ipython setup

```
$ ipython profile create
$ cp ~/.ipython/profile_default/ipython_config.py   ~/.ipython/profile_default/ipython_config.py.sav
$ diff ~/.ipython/profile_default/ipython_config.py   ~/.ipython/profile_default/ipython_config.py.sav
$ cp ~/.ipython/profile_default/ipython_config.py   ~/.ipython/profile_default/ipython_config.py.sav
$ diff ~/.ipython/profile_default/ipython_config.py.sav ~/.ipython/profile_default/ipython_config.py   
> c.InteractiveShell.colors = 'Linux'
> c.TerminalInteractiveShell.editing_mode = 'vi'
> c.TerminalInteractiveShell.editor = 'vi'
> c.TerminalInteractiveShell.extra_open_editor_shortcuts = False
> c.TerminalInteractiveShell.prompt_includes_vi_mode = True
> c.TerminalInteractiveShell.true_color = True
```

# Bash "command not found" has lengthy delay
Bash sometimes has long delay on command not found, or comes back with suggested packages to install.
`# sed -i 's/SoftwareSourceSearch=true/SoftwareSourceSearch=false/' /etc/PackageKit/CommandNotFound.conf`
https://forums.fedoraforum.org/showthread.php?240982-bash-hangs-on-quot-command-not-found-quot-and-pk-command-not-found

Hrrm... so [PackageKit](https://en.wikipedia.org/wiki/PackageKit) is "a consistent and high-level front end for a number of different package management systems."  
Oh joy.  

# Stupid gnome tricks
alt-tab cycles through "applications" instead of windows.
Based on: https://askubuntu.com/a/996410/806934

```
    Open Settings
    Select Devices->Keyboard (just "Keyboard Shortcuts" as of 2020 )
    Search for "Switch Windows" and enter Alt+Tab as the new shortcut.
    A dialog will tell you the shortcut is already being used by "Switch Applications", select Replace to confirm.
```
