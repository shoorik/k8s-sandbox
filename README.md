# k8s-sandbox

## Bare Minimum

from: https://kubernetes.io/docs/tutorials/hello-minikube/

A Kubernetes Pod is a group of one or more Containers, tied together for the purposes of administration and networking. The Pod in this tutorial has only one Container. A Kubernetes Deployment checks on the health of your Pod and restarts the Pod’s Container if it terminates. Deployments are the recommended way to manage the creation and scaling of Pods.

Create a Deployment that manages a Pod

```
kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node
```

View deployments

```
kubectl get deployments
```

View pods

```
kubectl get pods
```

View events for the entire cluster

```
kubectl get events
```

View kubectl configuration (all clusters, etc)

Stored in ~/.kube/config file:

```
kubectl config view
```

Expose as service

By default, the Pod is only accessible by its internal IP address within the Kubernetes cluster. To make the hello-node Container accessible from outside the Kubernetes virtual network, you have to expose the Pod as a Kubernetes Service.

```
kubectl expose deployment hello-node --type=LoadBalancer --port=8080
```

Review services

```
kubectl get services
```

Run the service

http://localhost:8080

Clearing

```
kubectl delete service hello-node
```

then

```
kubectl delete deployment hello-node
```

## Run a stateless application using a deployment

from: https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/

