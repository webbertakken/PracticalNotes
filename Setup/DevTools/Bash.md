# Setup Bash in Windows Subsystem for Linux

## Installing bash in Windows Subsystem for Linux

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