# Azure - Deploy application to Kubernetes

The name of the Azure Contianer Registry will be referred to as `<AcrName>`.
Its DNS-name will be referred to as `<AcrDnsName>`.

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

## Push & Deploy
See Kubernetes' [commands](../../K8s/commands.md).
