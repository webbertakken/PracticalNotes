# Setup package manager

## Windows

- [Chocolatey](./PackageManagers/Chocolatey.md)

#### Set default install dir (optional)

Run `sysdm.cpl,3` or go to `Control Panel` > `System and Security` > 
`System` > `Advanced system settings` > `Advanced`.

Click on `Environment Variables` and add the following `User variables` for your user:

`ChocolateyToolsLocation` = `C:\Tools`

_The path could be anythign that you like. It can prove useful to keep the path short._

Then confirm and restart computer.

## MacOS

- [Homebrew](./PackageManagers/Homebrew.md)
