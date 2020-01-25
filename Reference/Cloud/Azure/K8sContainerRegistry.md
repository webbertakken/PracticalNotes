# Azure - Container Registry

## Managing Resource Groups
Create a Resource Group
```
az group create --name <ResourceGroup>
```

## Managing Container Registry
Create an ACR
```
az acr create --resource-group <ResourceGroup> --name <AcrName> --sku Basic
```

Login to ACR
```
az acr login --name <AcrName>
```

Get LoginServer DNS
```
az acr list --resource-group <ResourceGroup> --query "[].{acrLoginServer:loginServer}" --output table
```

## Registering Container Registry with Kubernetes Service

_**Note:** use bash here._

First, get the ID of the service principal configured for AKS. Update the resource group name and AKS cluster name to match your environment.
```
$ CLIENT_ID=$(az aks show --resource-group <MainResourceGroup> --name <KubernetesCluster> --query "servicePrincipalProfile.clientId" --output tsv)
```

Get the ACR registry resource id. Update the regsitry name to that of your ACR registry and the resource group to the resource group where the ACR registry is located.
```
$ ACR_ID=$(az acr show --name <AcrName> --resource-group <ResourceGroup> --query "id" --output tsv)
```
Create the role assignment, which grants the proper access.
```
$ az role assignment create --assignee $CLIENT_ID --role Reader --scope $ACR_ID
```
The Container Registry is now usable by the Kubernetes cluster
