create a Dockerfile

build image:

```
docker build --tag helloworld:v1.0 .
```

list all images:
```
docker images
```

run service on k8s:

```
kubectl run hello-world --image=helloworld:v1.0 --image-pull-policy=Never --port=80

kubectl port-forward pods/hello-world 8080:80
```

Delete the pod and the image

```
kubectl delete pod hello-world 
# Remove the image
docker rmi nginx-helloworld:latest
```