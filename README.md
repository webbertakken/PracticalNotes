# PracticalNotes
___My Developer's Notebook 📓___ 
for reinstalling tools after reinstalling the operating system.

---

Featuring a list of tools and configurations, aimed to:
- be __quickly setup__
- applicable __cross-platform__
- provide a comprehensive development environment
- support __web__ and __game__ development

---

## Prerequisites

These will serve as prerequisites for everything below;

- Windows - [OS Components](./OsComponents/Windows.md)
- MacOS - _(none)_
- Linux - _(none)_

## Package managers

Command line interface for quickly installing new software;

- Windows ([Chocolatey](./PackageManagers/Chocolatey.md))
- MacOS ([Homebrew](./PackageManagers/Homebrew.md))

## Browsers

For surfing and developing;

- [Brave 🗗](https://brave.com/)
- [Chrome 🗗](https://www.google.com/chrome/)
- [Edge 🗗](https://www.microsoft.com/edge)
- [Firefox 🗗](https://www.mozilla.org)
- [Opera 🗗](https://www.opera.com)
- [Safari 🗗](https://www.apple.com/safari/) (MacOS only)
- [Vivaldi 🗗](Browsers/Vivaldi.md)

#### Useful extensions

Pick any you may like;

> __Note:__ Brave, Chrome, Edge, Vivaldi are all ___Chromium___ based.

- LastPass 
(
[Chromium 🗗](https://chrome.google.com/webstore/detail/lastpass-free-password-ma/hdokiejnpimakedhajhdlcegeplioahd),
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/lastpass-password-manager/)
)
- React Developer Tools (
[Chromium 🗗](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi),
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/react-devtools/)
)
- Redux Developer Tools (
[Chromium 🗗](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd),
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/reduxdevtools/)
)
- Chrome logger (
[Chromium 🗗](https://chrome.google.com/webstore/detail/chrome-logger/noaneddfkdjfnfdakjjmocngnfkfehhd),
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/chromelogger/)
)
- AddBlock Plus (
[Chromium 🗗](https://chrome.google.com/webstore/detail/adblock-plus/cfhdojbkjhnklbpkdaibdccddilifddb),
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/adblock-plus)
)
- Lighthouse (
[Chromium 🗗](https://chrome.google.com/webstore/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk?hl=en) only, see
[#6032 🗗](https://github.com/GoogleChrome/lighthouse/issues/6032)
)
- Tampermonkey (
[Chromium 🗗](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en), 
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/tampermonkey/)
)
- Stylus (
[Chromium 🗗](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne?hl=en), 
[Firefox 🗗](https://addons.mozilla.org/en-GB/firefox/addon/styl-us/)
)

#### Scripts

- [Github dark theme 🗗](https://github.com/StylishThemes/GitHub-Dark-Script/blob/master/README.md)
- [Gitlab dark theme 🗗](https://gitlab.com/vednoc/dark-gitlab)

## General tools

- File Archiving (Windows: [7-Zip 🗗](https://www.7-zip.org/download.html))
- Recording screen/camera (Windows: [ScreenToGif 🗗](https://github.com/NickeManarin/ScreenToGif))

## Development tools
   
[//]: # (Note that the order of these does matter, when seperated by a new line)

[//]: # (Dependencies: none)
#### Shells

- Linux
- MacOS
- Windows ([Cmder](./Shells/Cmder.md), [WSL](./Shells/Wsl.md))

[//]: # (Dependencies: Shells)
#### IDE
- [PhpStorm](Ide/PhpStorm.md)
- [VSCode](Ide/VsCode.md)
- [Android Studio](Ide/AndroidStudio.md) (incl. Android SDK)
   
[//]: # (Dependencies: WSL)
#### Runtimes & CLIs
- [Git](./DevTools/Git.md)
- [Go](./DevTools/GoLang.md) - [https://golang.org/doc/install 🗗](https://golang.org/doc/install)
- [Python](./DevTools/Python.md) (including pip)
- [PHP](./DevTools/Php.md) (including XDebug, Composer, Symfony etc.)
- [Node.js](./DevTools/Node.md) (including NPM, Yarn, Gulp etc.)
- [Flutter](./DevTools/Flutter.md)

[//]: # (Dependencies: Go)
#### Docker
- [Docker](./DevTools/Docker.md)
- [Compose](./DevTools/Docker.md#Install-Compose-Docker-Composer)
- [Kompose](./DevTools/Docker.md#Install-Kompose-Kubernetes-Composer)

[//]: # (Dependencies: Hypervisor)
#### Kubernetes 
- [Kubernetes](./DevTools/K8s.md)
- [Minikube](./DevTools/K8s.md#Install-Minikube)
- [Kubectl](./DevTools/K8s.md#Install-Kubectl)

#### Serverless
- _TBD_

[//]: # (Dependencies: none)
#### Cloud CLIs
 - Amazon ([aws 🗗](https://aws.amazon.com/cli/))
 - Google (gcloud, included in [Google Cloud SDK 🗗](https://cloud.google.com/sdk/install))
 - Azure ([az 🗗](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest))

 
## Reference docs

These are quick documentation references and cheat sheets

#### Cloud
 - [Azure](Reference/Cloud/Azure.md)
 - [Google Cloud](Reference/Cloud/Google.md)
 
#### Kubernetes (k8s)
 - [Practical concepts](Reference/K8s/PracticalConcepts.md)
 - [Commands](Reference/K8s/Commands.md)
