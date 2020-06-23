---
id: deployments
title: k8s deployments
---

## What is Deplyments?
* Deployment is nothing but a kubernetes controller which manages the replication set and pods. we can change image version and replicas of that image. we can rollback and rollingupdate. If pod fails to launch it will automatically re launch a new pod with the same image by using replication sets.

## How to create deployments using imperative method?
```
kubectl create deployment <dep-name> --image=<image-name> --restartpolicy=true
```

## How to change image or image version in the deployment
```
kubectl set image deployment/<dep-name> <cont-name>=<image:changeversion> --record
```

## How to check rollout status after change?
```
kubectl rollout status deployment.v1.apps/<dep-name>
```

## ## How to check rollout history?
```
kubectl rollout history deployment.v1.apps/nginx-deployment
```

## How to rollback to previous version?
```
kubectl rollout undo deployment.v1.apps/nginx-deployment
```

## How to rollback to a specific versions?
```
kubectl rollout undo deployment.v1.apps/nginx-deployment --to-revision=2
```
