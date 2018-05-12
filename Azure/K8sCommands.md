# Azure - Kubernetes commands

## Status management

#### Get cluster nodes
```
$ kubectl get nodes
```

#### Get state of current services
```
$ kubectl get service [--watch]
```

#### Get running pods
```
$ kubectl get pod [--watch]
```

#### Get state of currently deployed resources
```
$ kubectl get deployment,svc,pods,pvc
```

## Application management

#### Deployment from Container Registry

See [Kubernetes Container Registry](K8sContainerRegistry.md) commands.

#### Create new application
```
$ kubectl create -f azure-application.yaml
```