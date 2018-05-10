# Hugo Static Site Test

This is an example of a hugo site running in a kubernetes cluster. The site will be always refreshed from the contents in the master branch using [Git Syc][https://github.com/kubernetes/git-sync]


## Running in Minikube

Create service and pod

```
$ kubectl create -f k8s/pod.yaml
$ kubectl create -f k8s/service.yaml
```

## View results 

```
$ minikube service blog-pod
```

