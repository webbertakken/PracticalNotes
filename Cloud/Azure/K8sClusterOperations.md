# Azure - Kubernetes cluster operations

## Walkthrough
The following link shows a walkthrough with an example app.
- https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough

## Detailed
#### Creating a cluster
- https://docs.microsoft.com/en-us/azure/aks/create-cluster

#### Connecting to Kube Cluster
To connect use the following command:
```
$ az aks get-credentials --resource-group apps-takken-io --name cluster1-kube-takken-io
```
Your kubectl is now configured to work with given cluster.


#### Scaling a cluster
- https://docs.microsoft.com/en-us/azure/aks/scale-cluster

#### Upgrade Kubernetes version on cluster
- https://docs.microsoft.com/en-us/azure/aks/upgrade-cluster

#### Deleting a cluster
- https://docs.microsoft.com/en-us/azure/aks/delete-cluster
