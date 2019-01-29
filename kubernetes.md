Docker World 		-> Container 	-> Manager / Workers
Kubernetes World 	-> Pods  	-> Master / Nodes

Kubernetes runs container, but only inside pods. A pod can have multiple containers. 

Scale by replicating pods, not by replicating containers inside one pod. 

Pods are ephemeral, and all new pods get a new IP which creates problem as IP's can't be references directly. Solved by introducing a service between the pods and the user. The service exposes a stable IP and fixed DNS to the user so that the pods can be accessed from outside the cluster. Also keeps track of the IP endpoints of the pods currently active, loadbalancing, among other things. 

Labels can be put on the constiuent parts of the Kubernetes system, like pods and services. Pods and services are connected by matching labels. 

-- Pods --
Pods are atomic, either they exist, or they don't exist, and they are scheduled on nodes. They contain one or more (supporting) containers. The manifest file sent through the REST API controls the pod configuration. Each pod has its own IP. If there's more than one container in one pod, each can be accessed on different IP. 

- Communication -
Interpod communication is possible through the pod network. Inside the pod communication can be done over the shared localhost network. 
a
- States -
Manifest deployed through the apiserver, Pod is pending, pod is running, pod is succeeded. If it fails in pending or running, it gets state failed. 