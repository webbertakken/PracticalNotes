# Setup Docker

## Setting up Docker for Windows

- Download and install Docker CE from the [official website](https://store.docker.com/editions/community/docker-ce-desktop-windows). 
- Open settings and expose the daemon without TLS (if you understand the risks)
    - _Exposing the daemon without TLS will open it up for bash in WSL_
- Turn off experimental features until you need them
    - _Experimental features produced problems with containers filesystems for me before_ 

## Setting up Docker for Bash in Linux Subsystem for Windows
### Remove any old versions
Prevent troubleshooting as per [MS WSL #2288](https://github.com/Microsoft/WSL/issues/2288):
```
$ sudo rm /var/lib/dpkg/info/docker.prerm
$ sudo rm /var/lib/dpkg/info/docker.io.prerm
$ sudo rm /var/lib/dpkg/info/docker-ce.prerm
```
It's fine if it says the file or directory doesn't exist.

Now remove any existing packages:
```
$ sudo apt-get remove docker-compose docker-ce docker docker-engine docker.io
```

### Install Docker
Install packages to allow apt to use a repository over HTTPS
```
$ sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```
Add Docker's official GPG key
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Set up the repository
```
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Update source lists
```
$ sudo apt-get update
```

Install Docker
```
$ sudo apt-get install docker-ce
```

Or otherwise [official documentation](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
or this [blogpost from Tomas Lycken](https://blog.jayway.com/2017/04/19/running-docker-on-bash-on-windows/).

### Connecting Docker to Docker Daemon on Windows

Check if host OS Docker daemon can be reached:
```
$ docker -H tcp://0.0.0.0:2375 images
```

If so, set it as default:
```
$ echo "export DOCKER_HOST='tcp://0.0.0.0:2375'" >> ~/.bashrc
```

Check if it worked:
```
$ docker images
```
If that didn't work. Look in this [blogpost from Tomas Lycken](https://blog.jayway.com/2017/04/19/running-docker-on-bash-on-windows/) for any updates.

## Install Compose (Docker Composer)

See below or read the [Compose official documentation](https://docs.docker.com/compose/install/).

### Windows
Docker CE for Windows already includes Compose.

### Bash in Linux Subsystem for Windows
Install using Pythons package manager
```
$ sudo pip install docker-compose
```

verify by running
```
$ docker-compose
```

## Install Kompose (Kubernetes Composer)

See below or read the [Kompose official documentation](https://kubernetes.io/docs/tools/kompose/user-guide/#installation).

### Linux
```
$ curl -L https://github.com/kubernetes/kompose/releases/download/v1.12.0/kompose-linux-amd64 -o kompose
$ chmod +x kompose
$ sudo mv ./kompose /usr/local/bin/kompose
```

### macOS
```
$ curl -L https://github.com/kubernetes/kompose/releases/download/v1.12.0/kompose-darwin-amd64 -o kompose
$ chmod +x kompose
$ sudo mv ./kompose /usr/local/bin/kompose
```

### Windows
```
\> go get -u github.com/kubernetes/kompose
```