# Hugo k8s Static Site Test

This is an example of a hugo site running in a kubernetes cluster. The site will be always refreshed from the contents in the master branch using [Git Syc](https://github.com/kubernetes/git-sync)


## Running in Minikube

Create service and pod

```
$ kubectl create -f k8s/pod.yaml
$ kubectl create -f k8s/service.yaml
$ kubectl create -f k8s/ingress.yaml
```

## View results 

The k8s ingress is configured to serve the service in port 80. At the same time, the hugo site is configured to use the "example.com" (configurable in the pod file) for navigation.

Get the minikube ip and map it to example.com in your /etc/hosts file
```
$ minikube ip
<your-minikube-ip>
```

on  your /etc/hosts

```
<your-minikube-ip> example.com
```

*note*: you can change the name in the [k8s/pod.yaml](k8s/pod.yaml) file

Now go to http://example.com, you should be able to see the example site
