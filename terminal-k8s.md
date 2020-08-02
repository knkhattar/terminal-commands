Refer https://kubernetes.io/docs/reference/kubectl/cheatsheet/
kubectl version

   #  Start Stop
        ◦ sudo microk8s start/stop/status
   
   # Create vs Apply
    kubectl create is imperative -   
    kubectl apply is declarative // other changes stay
   # Modification
        * microk8s kubectl create -f infinispan.yaml
        * kubectl apply -f <file1>
        * kubectl apply -f <file1> -f <file2>  // multiple files can also be given
        * kubectl apply ./directory // will take all files inside
   # Basic Gets
        ◦ get nodes
        ◦ get service
        ◦ get deployment
        ◦ get pods
        * get all  // imp - lists pods service deployment replicasets
        * kubectl describe service <service name> // gives endpoints too
   # Interactive
        * kubectl exec -it [pod-name] bash //get inside pod bash prompt
   # Debug
         * kubectl logs [POD NAME]// MAY BE CONTAINER TOO also required
         * kubectl logs -f [POD NAME] # streaming logs - press enter for recent activity - time in utc
         * kubectl logs --previous ${POD_NAME} // for crashed container
         
   # Delete
        ◦ microk8s kubectl delete service [service name]
        * microk8s kubectl delete deployment [deployment name]
  # MISC
  * kubectl create deployment
