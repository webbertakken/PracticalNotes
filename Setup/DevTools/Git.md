# Setup Git

## Installation

#### Windows

```PS
choco install git
```

#### MacOS

```bash
brew update
brew install git
```

#### Debian-based

```bash
sudo apt update
sudo apt upgrade
sudo apt install git
```

#### Redhat-based

```bash
sudo yum upgrade
sudo yum install git
```

#### Documentation

Alternatively follow the [Official Documentation 🗗](https://git-scm.com/download/)

## Configuration

The most common way to configure git is to change the global configuration for a user on a machine.
Assuming this is what we want to achieve, the `--global` flag is used.

#### Line-endings
Let's all just agree that we only need `\n` characters. 

To not enforce this globally we keep end of line enforcement at native but disable autocrlf.
```
git config --global core.eol native
git config --global core.autocrlf false
```

#### User credentials

```bash
git config --global user.name <your-username>
git config --global user.email <your-email-address>
```

The recommended way of connecting to a git repository is by using ssh key, protected by a password.
Note that you might end up typing this password a few times a day so don't make it too long.

There is an excellent documentation by github on
[how to create and configure an ssh key 🗗](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).

#### Enable colors

```bash
git config --global color.ui auto
git config --global color.branch auto
git config --global color.status auto
```

#### Enable rebasing by default

```bash
# Never rebase master
git config --global branch.master.rebase false
# Always rebase feature branches
git config --global branch.autosetuprebase always
```
