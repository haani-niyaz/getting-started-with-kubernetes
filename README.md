# Getting Started with Kubernetes


### Create a resource

```
$ kubectl create -f pod.yaml
```

### Access pod from host for debugging purposes

```
Access pod (container) port from host on 8888
$ kubectl port-forward kubia-manual 8888:8080
```


## Labels


### Show labels

```
$ kubectl get pods --show-labels

$ kubectl get po -l creation_method=manual

$ kubectl get po -L env

$ kubectl ge po <pod-name> -o yaml
```

## Namespace

### Show namespaces

```
$ kubectl get ns
```

### Create a namespace

```
$ kubectl create namespace bitbucket
```

### Check current context

```
$ kubectl config current-context 
```

### Change context

```
$ kubectl config use-context <context-name>
```


### Set namspace within context

```
$ kubectl config set-context minikube --namespace bitbucket
```

## Secrets

### Create secret as a file

```
$ kubectl create secret generic bitbucket-properties --from-file=./bitbucket.properties
```

### Describe 

```
$ kubectl get secret bitbucket-properties -o yaml
```


#### Decode

1. Run the above command
2. Run: `$ echo '<encoded text>' | base64 --decode`




