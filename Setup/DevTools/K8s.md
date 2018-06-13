# Setup Kubernetes tools

## Install Minikube
[Official documentation](https://github.com/kubernetes/minikube#installation)

### Prerequisites
Operating system must have access to a Hypervisor

### Installation
#### Windows:
Install minikube
```powershell
\> choco install minikube
```

###### When using Hyper-V:
Follow this [guide](https://medium.com/@JockDaRock/minikube-on-windows-10-with-hyper-v-6ef0f4dc158c)
and disable IPv6 on both the default virtual switch and the newly created external virtual switch.

#### Linux:
```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

#### MacOS:
```bash
$ brew cask install minikube
```

## Install Kubectl
[Official documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl)

### Installation
#### Windows:
```powershell
\> choco install kubernetes-cli
```

#### Linux:

#### MacOS:
```
homebrew install kubectl
```

## Install Heapster, InfluxDB, Grafana
On minikube, enable addons:
```bash
$ minikube addons enable heapster
```
Wait for it to be up
```bash
$ kubectl get pods --namespace=kube-system --watch
```
Then open the dashboard using Grafana Dashboard
```bash
$ kubectl addons open heapster
```
