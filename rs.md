---
id: replication sets
title: rs overview and questions
---

## What is replication set?
* replication is nothing but a kubernetes entity/controller which will ensure/maintains that the current state and desired stste are same or maintain specified number of pods in running state.

## What is the Differences between Replicaset and Deployment?
* In replicaset we can not change the image spec, where as we can change image spec in Deployment. We can not change anything in rs but we can change in deployment at code level. we can maintain only replicas in replicationset, where as deplyments can maintain replicas as well as versions of images also. We can update and rollback versions in deployment not in replicasets.

## What is Statefulset ?
* Stateful sets name can not be changed and must be same. we use sts mostly for db's.

## What is Daemonset?
* which will ensure that the copy of a pod runs on all the nodes.
