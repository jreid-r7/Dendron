---
id: h8bh49rx6t2k4twhamtjvqu
title: Kubernetes
desc: ''
updated: 1723636850027
created: 1723636850027
isDir: false
---
**Why learn Kubernetes?**
This is all from a developer perspective. k8s is for automating deployment, scaling and management of deployments. It can monitor containers and deal with containers going down. We can package up our app and let k8s manage it for us. It gives us a robust networking system as well as service discovery and load balancing.

A container sits within a pod and we comunicate via the pod. Deployment is done via a ReplicaSet. We create services to allow pods to communicate and check healthe, etc. A Node is a VM and can run as many Pods as neccessary. There will be a Master Node which contains a Controller Manager, Scheduler, API Server etc. We talk to the Master Node using kubectl.

Running k8s 
1. Minikube
2. Docker Desktop - limited to one master and one worker node
3. kind - kubernetes in docker
4. kubeadm - most work

kubectl commands
- kubectl version
- kubectl cluster-info
- kubectl get all
- kubectl run [container-name] --image=[image-name]
- kubectl port-forward [pod] [ports]
- kubectl expose ...
- kubectl create [resource]
- kubectl apply [resource]

Web UI Dashboard - optional
- kubectl apply [dashboard-yaml-url]
- kubectl describe secret -n kube-system
- locate the kubernetes.io/service-account-token and copy the token
- kubectl proxy
- visit the dashboard url and login using the token

**Creating Pods**
Pods act as the hosts for our containers. A ppod is the basic execution unit of a k8s app. We can organise our application into Pods. We will often have a single container in a Pod.

Worker Node -> Pod(s) -> Container(s).

Pods can live or die but are never brought back to life - they can be replaced.
Pod containers share the same Network namespace (share IP/port)
Pod containers have the same loopback network interface (localhost)
Container processes need to bind to different ports within a Pod
Pods do not span nodes.

To create a Pod
- kubectl run ...
- kubectl create/apply with a yaml file
 to run the nginx:alpine container in a pod
 kubectl run [podname] --image=nginx:alpine

list pods
kubectl get pods

to enable a container to be called externally
kubectl port-forward [name-of-pod] 8080:80      (external-port:internal-port)

remove a pod
kubectl delete pod [name-of-pod]

kubectl delete deployment [name-of-deployment]    (permanent delete)

example run
kubectl run my-nginx --image=nginx:alpine
kubectl port-forward my-nginx 8080:80
kubectl get pods
kubectl delete pod my-nginx

YAML - textfile of maps and lists
Indentation matters and uses spaces
Maps:
 - name: value pairs
Lists:
 - sequence of items

key: value
complexMap:
  key1: value
  key2:
    subKey: value
items:
 - item1
 - item2
 itemsMap:
  - map1: value
     map1Prop: value
  - map2: value
     map2Prop: value

kubectl create -f nginx.pod.yml --dry-run --validate=true
kubectl apply -f nginx.pod.yml
- allows for updates - create or apply changes
kubectl create -f nginx.pod.yml --save-config
- store current properties in resource's annotations
kubectl exec my-nginx -it sh
- open a shell on a pod

Pod health - k8s relies on probes - a diagnostic performed periodically
Liveness Probe - are we healthy? should we restart?
Readiness Probe - are we ready to accept requests?
Failed pods are recreated by default

Types:
- ExecAction
- TCPSocketAction
- HTTPGetAction
Results
- Success
- Failure
- Unknown

**Creating Deployments**
A Pod on its own will just die if something goes wrong. We need a deployment to allow the Pod to be managed properly.

kubect run not only runs our Pod but also creates a Deployment and a ReplicSet. A ReplicaSet is a declaritive way to manage Pods. A deployment is a declaritive way to manage Pods using ReplicaSets.

Pods can be created and destroyed but never re-created. Deployments and ReplicaSets ensure Pods stay running and can be used to scale Pods. 

ReplicaSets act as a Pod controller:
- Self-healing mechanism
- Ensure the requested number of Pods are available
- Provide fault-tolerance
- Can be used to scale Pods
- Relies on a Pod template
- No need to create Pods directly!
- Used by Deployments

A Deployment manages Pods:
- Pods are managed using ReplicaSets
- Scales ReplicaSets, which scale Pods
- Supports zero-downtime updates by creating and destroying ReplicaSets
- Provides rollback functionality
- Creates a unique label that is assigned to the ReplicaSet and generated Pods
- YAML is very similar to a ReplicaSet

Deployment -> ReplicaSet -> Pod -> Container

How do you update existing Pods?
One of the strengths of k8s is zero downtime deployments
Update an apps Pods without impacting end users
Several options:
- Rolling updates
- Blue-green deployments
- Canary deployments
- Rollbacks

**Creating Services**

**Storage Options**

**ConfigMaps and Secrets**

**Putting it all together**