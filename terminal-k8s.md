Refer https://kubernetes.io/docs/reference/kubectl/cheatsheet/
kubectl version

   #  Start Stop
        ◦ sudo microk8s start/stop/status
   # Basic Gets
        ◦ get nodes
        ◦ get service
        ◦ get deployment
        ◦ get pods
        * get all  // imp - lists pods service deployment replicasets
   # Create vs Apply
    kubectl create is imperative -   
    kubectl apply is declarative // other changes stay
   # Modification
        * microk8s kubectl create -f infinispan.yaml
        * kubectl apply -f <file1>
        * kubectl apply -f <file1> -f <file2>  // multiple files can also be given
        * kubectl apply ./directory // will take all files inside
   # Basic Gets
   kubectl describe service <service name> // gives endpoints too
   # Delete
        ◦ microk8s kubectl delete service infinispan-server
  # MISC
  * kubectl create deployment
