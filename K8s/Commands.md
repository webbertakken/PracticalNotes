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

#### Get namespaces
```
$ kubectl get namespace
```

#### Resource management
```bash
$ kubectl addons open heapster
```

#### Internal network management
Run a box on the cluster
```
kubectl run curl --image=radial/busyboxplus:curl -i --tty
```
Then check the internal dns service (example)
```
nslookup <service name>
```

## Application management

#### Deployment from Container Registry

See [Kubernetes Container Registry](K8sContainerRegistry.md) commands.

#### Create new namespace
```bash
$ kubectl create namespace <namespace-name>
```

#### Change context to that namespace
```bash
$ kubectl config set-context $(kubectl config current-context) --namespace=<namespace-name>
# Validate it
$ kubectl config view | grep namespace:
```

#### Set a ResourceQuota
Create the ResourceQuota
```bash
$ kubectl create -f <resource-quota name>.yaml [--namespace=<target namespace>]
```
Confirm it's creation
```bash
$ kubectl get resourcequote [--namespace=<target namespace>]
```

#### Create new application
run a specified deployment
```
$ kubectl create -f <deployment name>.yaml [--namespace=<target namespace>]
```

or run a particular image:
```bash
$ kubectl run <desired name> --image=<docker image name> [--port=<portnumber>]
```

#### Expose a port
Expose a port for a resource (deployment, pod or other)
```bash
$ kubectl expose <type name> <identifier name> [--port=external port] [--target-port=container-port] [--type=service-type]
```
Example command:
```bash
$ kubectl expose deployment symfony-deployment --type=NodePort
```

#### Inspect the deployment
```bash
$ kubectl describe deployment <deployment name> --namespace=<namespace name>
```

#### (Development) Get loadbalancer ip
```bash
$ minikube service <loadbalancer name> --url
```

## Misc Commands

#### Label a resource
Update a label on a resource
```bash
$ kubectl label <resource type> <identifier name> <key>=<value>
```
For example:
```bash
kubectl label pods foo unhealthy=true
```

#### Deployment commands
```bash
$ kubectl get deployments
$ kubectl rollout status
$ kubectl set image
$ kubectl rollout history
```

## Secrets

#### Creating a secret
Example command for creating a secret
```bash
$ kubectl create secret generic <secret name> --from-literal=password=<somepassword>
```

#### List secrets
```bash
$ kubectl get secret
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

## Autoscaling
Enable Horizontal Pod Autoscaling for a deployment
```bash
$ kubectl autoscale deployment <deployment name> --cpu-percent=50 --min=<min pods> --max=<max pods>
```

Check Horizontal Pod Autoscaling status
```bash
$ kubectl get hpa
```

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
