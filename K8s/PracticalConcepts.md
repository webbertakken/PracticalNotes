# Kubernetes - Practical Concepts
This page holds conceptual steps and explanations of K8s ideas and tasks

## App management
- Create a namespace (if not exists)
- Change context to that namespace
- &lt;any tasks to the app&gt;
- Change context back to no-namespace

___Note:__ Any tasks performed to any namespaced app should be wrapped by this practise_

## App deployment
- Define the deployment
- Expose its services
- Deploy it to the cluster

## Debugging Minikube
Don't spend too much time, instead just
[recreate the cluster](https://github.com/kubernetes/minikube/issues/2755#issuecomment-385624552).
