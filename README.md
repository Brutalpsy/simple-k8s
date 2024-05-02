## Feed a config file to k8s cluster with these commands

kubectl apply -f client-pod.yaml
kubectl apply -f client-node-port.yaml

## print the status of all running pods

kubectl get pods

## print the status of all services

kubectl get services

## by having a docker desktop k8s, can can access the site on

localhost:31515

## Get detailed info about an object

kubectl describe <object type> <object name>

or in our case:
kubectl describe pod client-pod

## or we can ommit the object name and use get information about all of that type

kubectl describe pods
or
kubectl describe pod

## To remove an object

we issue an imperative update command

kubectl delete -f <config file>
or in our case:
kubectl delete -f client-pod.yaml

## we can also get the status of deployments

kubectl get deployments

## get additional information regarding the pods

kubectl get pods -o wide

## imperative command to update an image

kubectl set image <object_type>/<object_name> <container_name>=<new image to use>

or in our case:

kubectl set image deployment/client-deployment client=brutalpsy/multi-client:v5
