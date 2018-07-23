# Windows Shells 
It is recommended to install both Cmder and Ubuntu bash, for maximum flexibility.

## Cmder
Open powershell with administrative permissions and use chocolatey to install Cmder

```powershell
\> choco install cmder
```

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
