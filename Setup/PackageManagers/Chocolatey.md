# Setup Chocolatey - Windows package manager

#### Installation
Follow installation instructions from the [official website 🗗](https://chocolatey.org/)

#### Set environment
Choose the folder where packages are 
[saved](https://github.com/chocolatey/choco/wiki/GettingStarted#where-are-chocolatey-packages-installed-to)
by setting the environment variable to desired directory.

```powershell
\> $env:ChocolateyBinRoot="C:\dev\"
\> $env:ChocolateyToolsLocation="C:\dev\"
\> $env:InstallDir="C:\dev\"
```
