# Azure - Kubernetes prerequisites

#### Prerequisites
Register the required providers to create a AKS service
```
$ az provider register -n Microsoft.Network
$ az provider register -n Microsoft.Storage
$ az provider register -n Microsoft.Compute
$ az provider register -n Microsoft.ContainerService
```

#### Install Kube-cli
Install Azure Kubernetes Service CLI
```
$ az aks install-cli
```