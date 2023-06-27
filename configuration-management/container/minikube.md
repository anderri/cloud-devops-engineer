# Minikube



#### install hyperhit and minikube

`brew update`

`brew install hyperkit`

`brew install minikube`

`kubectl`

`minikube`

#### create minikube cluster

`minikube start --vm-driver=hyperkit`

`kubectl get nodes`

`minikube status`

`kubectl version`

#### delete cluster and restart in debug mode <a href="#user-content-delete-cluster-and-restart-in-debug-mode" id="user-content-delete-cluster-and-restart-in-debug-mode"></a>

`minikube delete`

`minikube start --vm-driver=hyperkit --v=7 --alsologtostderr`

`minikube status`

#### kubectl commands <a href="#user-content-kubectl-commands" id="user-content-kubectl-commands"></a>

`kubectl get nodes`

`kubectl get pod`

`kubectl get services`

`kubectl create deployment nginx-depl --image=nginx`

`kubectl get deployment`

`kubectl get replicaset`

`kubectl edit deployment nginx-depl`

#### debugging <a href="#user-content-debugging" id="user-content-debugging"></a>

`kubectl logs {pod-name}`

`kubectl exec -it {pod-name} -- bin/bash`

#### create mongo deployment <a href="#user-content-create-mongo-deployment" id="user-content-create-mongo-deployment"></a>

`kubectl create deployment mongo-depl --image=mongo`

`kubectl logs mongo-depl-{pod-name}`

`kubectl describe pod mongo-depl-{pod-name}`

#### delete deplyoment <a href="#user-content-delete-deplyoment" id="user-content-delete-deplyoment"></a>

`kubectl delete deployment mongo-depl`

`kubectl delete deployment nginx-depl`

#### create or edit config file <a href="#user-content-create-or-edit-config-file" id="user-content-create-or-edit-config-file"></a>

`vim nginx-deployment.yaml`

`kubectl apply -f nginx-deployment.yaml`

`kubectl get pod`

`kubectl get deployment`

#### delete with config <a href="#user-content-delete-with-config" id="user-content-delete-with-config"></a>

`kubectl delete -f nginx-deployment.yaml`

\#Metrics

`kubectl top` The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.



