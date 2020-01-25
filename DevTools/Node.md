# Setup Node.js and related tools

## Install

#### MacOS
Using Homebrew
```
brew install node
```

#### Windows
Using windows-nvm (Recommended)
Follow [nvm-windows](https://github.com/coreybutler/nvm-windows) official documentation

Using Chocolatey
```PS
choco nodejs.install
```

#### Linux
Follow [Node Version Manager 🗗](https://github.com/creationix/nvm) official documentation

## Setup most important tools globally
Node Package Manager (NPM) comes with the Node.js installation by default.

Install and update NPM, Yarn, Gulp, GruntJs, Firebase tools
```bash
npm install --global npm yarn gulp grunt firebase-tools
```

(windows only)
``` 
npm install --global --production windows-build-tools
```
