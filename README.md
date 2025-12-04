# minikube_deployemnt
cd minikube_deployemnt

## Start Minikube

run  

    minikube start
    
## Build the image

run
    eval $(minikube docker-env)
    docker build -t kube-app:1.0 .
 
## Apply the deployment and Service

run

    kubectl apply -f deployment.yaml
   
    kubectl apply -f service.yaml


## Check the pods

run 

    kubectl get pods
    
    kubectl get svc

## Check the applicaion doea it works inside the cluster

run

    kubectl exec -it deploy/kube-app -- curl http://kube-app-service:3000

## Create the tunnel to access it from out side from the cluster    

run    

    minikube service kube-app-service


check the browser using the ip that shows after this

http://kube-app-service:3000  --- inside the clusters only

 eg: http://127.0.0.1:37447 --- on any browser or curl, the port may change each time.


     
