# Windows Shells 
It is recommended to install both Ubuntu bash and Cmder or Conemu, for maximum flexibility.

## Ubuntu Bash in Windows Subsystem for Linux

#### Installation

- Go to `Settings` > `Apps & features`
- Under "Related settigns" click on `Programs and Features`
- Go to `Turn Windows features on or off`
- Enable Windows Subsystem for Linux
- Reboot
- Go to `Microsoft Store`
- Search for `Ubuntu`
- Install `Ubuntu`

Update source lists

```
$ sudo apt-get update
```

Make apt-get work with packages over https

```
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

## ConEmu or Cmder
ConEmu is a console emulator, with many features. Cmder a layer on top of ConEmu. 
Pick the one of your preference.

#### Installation
Open powershell with administrative permissions and use chocolatey to install either 
ConEmu or Cmder.
```powershell
\> choco install conemu
```
or
```powershell
\> choco install cmder
```

#### Common sense settings
Go to `Settings` > `Main` > `Size & Pos` and tick the boxes for:
- [x] `Snap to desktop edges`
- [x] `restore to active monitor`

#### Quake console
Once installed enable the quake console in the settings. The default hotkey for 
opening and closing the quake-style console  is ``ctrl + ` ``.

#### Example four-panel setup
Go to `Settings` > `Startup` > `Tasks` and add a new task by pressing the `+`-symbol.

Name the task `PS x2 & Bash x2` and tick the boxes:
- [x] Default task for new console
- [x] Default shell
- [x] Taskbar jump lists

Make sure not to set the `/dir`-parameter, so that external applications can provide their default directory.

In the empty text area paste the following snippet to be its contents

```
powershell.exe -new_console:n:t:PS

powershell.exe -cur_console:s1TVn:t:PS

bash.exe -cur_console:s1THn:t:Bash

bash.exe -cur_console:s2THn:t:Bash
```
