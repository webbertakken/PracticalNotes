# Setup Kubernetes tools

## Install Minikube
[Official documentation](https://github.com/kubernetes/minikube#installation)

#### Prerequisites
Operating system must have access to a Hypervisor

#### Installation
Windows:
```powershell
\> choco install minikube
```

Linux:
```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

MacOS:
```bash
$ brew cask install minikube
```

## Install Kubectl
[Official documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl)

#### Installation
Windows:

Linux:

MacOS:
```
homebrew install kubectl
```
