# Setup Node.js and related tools

## Windows
Official documentation


#### Using Chocolatey
```
> cinst nodejs.install
```

#### Using Scoop
```
> scoop install nodejs
```

### Setup most important tools globally
Node Package Manager (NPM) comes with the Node.js installation by default.

Install and update NPM, Yarn, Gulp, GruntJs
```
> npm install --global npm@latest yarn gulp grunt
```

## Bash in Windows Subsystem for Linux
Node.js
```
$ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
$ sudo apt-get install -y nodejs
```

Build tools
```
$ sudo apt-get install -y build-essential
```

### Setup most important tools globally
Node Package Manager (NPM) comes with the Node.js installation by default.

Install and update NPM, Yarn, Gulp, GruntJs
```
$ sudo npm install --global npm@latest yarn gulp grunt
```