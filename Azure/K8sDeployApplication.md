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

## Prepare the application

### Create images
Run the application so that it is built and we can see it work
```
$ docker-compose up
```

Shut down the application
```
$ docker-compose down
```

Check the images for correctness
```
$ docker-compose images
```

### Tag images
Tag the containers like `<AcrName>/<image-name>:<version>`

or

Give the configuration these tags as image names

See also: https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-acr

### Push (optional)
Push the containers that belong to the application in current folder
```
$ docker-compose push
```

_**Note:** if all goes well, docker-compose will attempt to push to the correct registry (i.e. my-registry.azurecr.io). With the correct access rights it should be able to succeed._

See also: https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-docker-cli

### Run the application
In case you have just pushed the images in the above step you can run the following command with the flag `--build none`
```
kompose up
```

Your application now runs on the Kubernetes cluster. But it's not yet happy.

Next up:

- Replication
- Persistent volumes
- Backup