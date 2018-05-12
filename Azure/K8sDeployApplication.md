# Azure - Deploy application to Kubernetes

The name of the Azure Contianer Registry will be referred to as `<AcrName>`.  
Its DNS-name will be referred to as `<AcrDnsName>`.

## Deploying the application (WIP)

## Tag the containers

#### Tag the containers to start with the AcrDnsName

<!---
Tag (or custom image name) the images:

https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-acr

Convert docker-compose
```
docker-compose up
docker-compose down
kompose convert
```

Deploy


https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-docker-cli

--->

## Login with Docker to make Kompose work

#### Set admin to enabled
```
$ az acr update -n <AcrName> --admin-enabled true
```

#### Retrieve the password
```
$ az acr credential show --name <AcrName> --query passwords[0]
```
Copy the password and use it when asked in the next step.

#### Docker login
```
$ docker login -u <AcrName> --password-stdin <AcrDnsName>
```