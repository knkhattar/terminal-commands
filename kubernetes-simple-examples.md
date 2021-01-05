# Nginx 
## Deployment  

````
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-nginx
spec:
  selector:
    matchLabels:
      run: my-nginx
  replicas: 2
  template:
    metadata:
      labels:
        run: my-nginx
    spec:
      containers:
      - name: my-nginx
        image: nginx
        ports:
        - containerPort: 80
  ````      
## Service
```
apiVersion: v1
kind: Service
metadata:
  name: my-nginx
  labels:
    run: my-nginx
spec:
  ports:
  - port: 80
    protocol: TCP
  selector:
    run: my-nginx
    
````

# Service labels  
Note : spec.selector field of the service should match the spec.template.metadata.labels of the pod created by the Deployment.

# Deployment  
kubectl apply -f filename.yml

# Delete resources

* kubectl delete deploy <deployment name>
* kubectl delete service <service name>  

