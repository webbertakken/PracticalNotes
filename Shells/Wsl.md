# Windows Subsystem for Linux

## WSL2 

Follow steps at https://docs.microsoft.com/en-us/windows/wsl/wsl2-install

## Deprecated: Ubuntu in WSL
Install Ubuntu Bash in Windows Subsystem for Linux

___Note:__ with Cmder installed, Ubuntu bash in WSL becomes less relevant. You might want to install it as needed._

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
