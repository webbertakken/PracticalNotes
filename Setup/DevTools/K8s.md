# Setup Kubernetes tools

## Minikube
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
Follow this [guide](https://medium.com/@JockDaRock/minikube-on-windows-10-with-hyper-v-6ef0f4dc158c) or in short:
1. Create external virtual switch named "Kubernetes Virtual Switch".
2. Disable IPv6 on all relevant network adapters.
3. Create the kubernetes cluster using hyperv and the newly created 
```powershell
\> minikube start --vm-driver=hyperv --hyperv-virtual-switch="Kubernetes Virtual Switch" --cpus=3 --memory=4096
```
If anything still doesn't work; disable `dynamic memory` in Hyper-V.

#### Linux:
```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

#### MacOS:
```bash
$ brew cask install minikube
```

## Kubectl
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

## Heapster, InfluxDB, Grafana
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

## Helm & Tiller
#### Install Helm
##### Windows
```powershell
choco install kubernetes-helm
```
##### MacOS
```bash
brew install kubernetes-helm
```
##### Linux
download from [https://github.com/kubernetes/helm/releases](https://github.com/kubernetes/helm/releases)
