# Learning Notes : Kubernetes
The purpose of this article is to document what I learn about kubernetes. This is a beginner level article. The purpose of repository is to put the necessary code for embedding purpose.

## Requirement
1. Docker
2. Minikube (spec requirement : 2 cpus, 2GB of free memory, 20 gb of free disk space)

## Instruction
1. Start an instance of kubernetes cluster
    
    ```
    minikube start
    ```
2. create namespace
    ```
    kubectl apply -f namespace.yaml
    ```
3. check the created namespace
    ```
    # get all kubernetes 'namespace' kind of objects in the cluster
    kubectl get namespaces
    ```
4. create deployment
    ```
    kubectl apply -f deployment.yaml
    ```
5. check the deployment
    ```
    # get all kubernetes 'deployment' kind of objects in the namespace named 'development'
    kubectl get deployments -n development
    ```
6. check the pod created
    ```
    # get all kubernetes 'pods' kind of objects in the namespace named 'development'
    kubectl get pods -n development
    ```
7. create a load balancer service
    ```
    kubectl apply -f service.yaml
    ```
8. check the service created
    ```
    kubectl get services -n development
    ```
9. expose the cluster to the outside world
    ```
    minikube tunnel
    ```
10. test your running app
- open your browser
- go to '127.0.0.1'
- your app is running! yey
11. delete the namespace, deployment, and service (optional)
    ```
    kubectl delete -f namespace.yaml
    kubectl delete -f deployment.yaml
    kubectl delete -f service.yaml
    ```
12. stop and delete the minikube instances (dont skip this part. minikube instance reserve device resource)
    ```
    minikube stop
    minikube delete
    ```



