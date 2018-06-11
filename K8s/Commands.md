# Kubernetes commands
The primary tool to administer k8s clusters is kubectl.

See the official documentation for the kubectl 
[cheat sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
and 
[reference](https://kubernetes.io/docs/reference/).


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
$ kubectl get pods [--watch]
```

#### Get detailed information about a pod
```
$ kubectl describe pod [pod name]
```

#### Get state of currently deployed resources
```
$ kubectl get deployment,svc,pods,pvc
```

## Application management

#### Deployment from Container Registry

See [Kubernetes Container Registry](K8sContainerRegistry.md) commands.

#### Create new application
run a specified deployment
```
$ kubectl create -f azure-application.yaml
```

or run a particular image:
```bash
$ kubectl run <desired name> --image=<docker image name> [--port=<portnumber>]
```

#### Expose a port
Expose a port for a resource (deployment, pod or other)
```
$ kubectl expose <type name> <identifier name> [--port=external port] [--target-port=container-port] [--type=service-type]
```
Exampe command:
```
$ kubectl expose deployment symfony-deployment --type=NodePort
```

#### Label a resource
Update a label on a resource
```bash
$ kubectl label <resource type> <identifier name> <key>=<value>
```
For example:
```bash
kubectl label pods foo unhealthy=true
```

## Application Scaling

#### Scale a deployment
```bash
$ kubectl scale deployment <deployment name> --replicas=<number>
```

#### Expose the NodePort
Expose 
```bash
$ kubectl expose deployment <deployment name> --type=NodePort
```

#### Set a LoadBalancer
Set a LoadBalancer service to talk to the NodePorts
```bash
$ kubectl expose deployment <deployment name> --type=LoadBalancer --port=8080 --target-port=8080 --name <LoadBalancer service name>
```

### Inspect the loadbalancer
```bash
$ kubectl describe services tomcat-load-balancer
```
External IP is given through DNS system of the cloud provider.

## Local management
#### Port forwarding
Forward a local port (on the machine where kubectl is run from) to a pod
```bash
$ kubectl port-forward <pod name> [[local-port:]remote-port]
``` 

#### Attaching to a Container's process
Attach to the process that is already running inside an existing container
```bash
$ kubectl attach <pod name> [-c <container>]
```

#### Executing commands
Execute a command in a pod
```bash
$ kubectl exec [-it] <pod name> [-c <container>] <command> [args]
```
Arguments: 
- `-i` option will pass stdin to the container
- `-t` will specify stdin is a TTY

For example, to open an interactive bash cli:
```bash
$ kubectl exec -it <pod name> bash
```
