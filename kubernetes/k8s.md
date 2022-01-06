### kubernetes benefits
1. zero-downtime deployments
1. self-healing
1. scale containers

    ### kubectl
    ```sh
    kubectl version
    kubectl cluster-info
    kubectl get all
    kubectl run [container-name] --image=[image-name]
    kubectl port-forward [pod] --address=0.0.0.0 [ports]
    kubectl expose ...
    kubectl create [resource]
    kubectl apply [resource]
    kubectl delete pod [name-of-pod]
    kubectl delete deployment [name-of-pod]


##YML
kubectl create -f nginx.pod.yml --save-config
kubectl describe pod [pod-name]
kubectl apply -f nginx.pod.yml
kubectl exec [pod-name] -it sh
kubectl edit -f nginx.pod.yml
kubectl delete -f nginx.pod.yml
```
### web ui

https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/


### kubernets pods
- smallest object of the kubernets object model
- environment for continers
orgnize pplication "parts" into pods(server, caching, apis, dtabase, etc.)

- pod ip, memory, volumes, etc.shared across containers

- scale horizontally by adding pod replicas
- pods live nd die but never com back to life

### Probs
- readines probe: when should a container start receiving trffic?
- liveness probe: when hould a container restart?

### ReplicaSets
replicaSets act as a od controller
- self-healing mechanism
- ensure the requested number of pods are avaliable
- provide fault-tolernce
- can be used to scale pods
- relies on a pod template
- no need to create pods directly
- used by deployments

### a deployment manges pods
- pods are managed using replicasets
- scales replicasets, which scale pods
- supports zero-downtime updates by creating and destroying replicasets
- provides rollbck functionality
- creates a unique label that is assigned to the replicaset and generated pods
- yaml is very similar to  replicaset


### service
- services abstract pod ip addresses from consumers
- load balances between pods
- relies on lbels to associate a service with a pod
- node's kube-proxy creates a virtual ip for services
- layer 4 (tcp/udp over ip)
- services are not ephemeral
- creates endpoints which sit between a service and pod

### trouble shooting
```sh
#view the logs for a pod's container
kubectl logs [pod-name]

#view the logs for a specific container within a pod
kubectl logs [pod-name] –c [container-name]

#view th logs for a previously running pod
kubectl logs -p [pod-name]

#stream a pod's logs
kubectl logs -f [pod-name]
```sh

getting details about a pod
```sh
#descibe a pod
kubectl describe pod [pod-name]

#change a pod's output format
kubectl get pod [pod-name] -o yaml

#change  deployment's output format
kubectl get deployment [deployment-nme] -o yaml
```

shell into a pod container
```sh
# shell into a pod container
kubectl exec [pod-name] -it sh
```