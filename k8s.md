---
id: K8S
title: Interview Questions
---

## What is Kubernetes?
* kubenetes is a container orchestration tool. 
* It is desined and developed by Google in 2000 and later in 2014 donated to Cloud Native Computing Foundation(CNCF).
* used to manage containers.

## What is the difference between kubernetes and docker?
* Docker is used for building the docker images and creating containers where as kubenetes used to manage the containers.

## Tell similar tools like kubernetes?
* docker swarm.
* Mesos.
* DC/OS.

## What is the difference between Docker swarm and Kubenetes?
* both are used for managing containers.
* Docker swarm is not container ready and not self healing.
* Kubernetes is modular, flexible and production ready tool.

## What is the difference between Automation and Orchestration?
* automation used for performing a single task.
* orchestration used for building a work flow.

## What is kubernetes Architecture?
* Master
    * Kube-Api server --> it is like entrypiont to the kubernetes or front end of the kubernetes, every request comes to api-server first.
    * Scheduler --> it will schedule the services on the nodes by checking which is available with etcd.
    * Controll manager
        * Node controll manager --> notify whether the node is up or not
        * Replication controller manager --> maintains current state and desired state
        * Endpoint controller manager --> it will creates the endpoints for services
        * Service Account controller manager --> it will allow to access external services like s3, rds, etc..
    * etcd --> It holds the information about master and nodes. it is like data store and key value pairs.
* Nodes
    * Kublet --> kubelet will ensures that the pods are in running state.
    * kube-Proxy --> it will take care of network related like ip address to the pods.
    * Docker --> docker will run the containers.

## What is the difference between image and a container?
* Docker image is template with basic os, application services and data     
* Docker container is a copy of image with additional resources like cpu, memory, network and storage.    

## Differences between Docker swarm and Docker-compose?
* Docker compose is used to create containers 
* Docker swarm is used to link those containers and manage containers.

## Differences between Bridge and Overlay network?
* Bridge is used to connect multiple containers with in the same node where as 

## What is host network?
* host network is used to assign hostnetwork directly to the container.

## Differences between container and vm?
* Container is a light weight software and we can ship and run anywhere
* VM is a 
