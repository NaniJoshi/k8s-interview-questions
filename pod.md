---
id: Pods
title: Pods Overview
---

## What is a Pod?
* Pod is a smallest object of kubernetes and which will hold container(s).
* A pod definition can have 4 mandatory basic fields.
    * apiVersion --> for pods it is v1.
    * kind --> kind is a pod in this case.
    * metadata --> it will contain info about the pod like name, namespaces, labels and etc.
    * spec --> spec will have the container information.

## Pod example?
```
apiVersion: v1
kind: pod
metadata: 
  name: basic-pod
spec: 
  - containers:
    image: nginx
    name: nginx
```

## Pod creation in two ways
* Declerative way --> craete pod using a file and create using following command
```
kubectl create -f pod.yaml
```
* Imperative way --> create pod using kubectl commands as follows
```
kubectl run demo --image=nginx --generator=run-pod/v1
```
