---
id: K8S
title: Interview Questions
---

## What is Kubernetes?
* kubenetes is a container orchestration tool. 
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
    * Kube-Api server
    * Scheduler
    * Controll manager
    * etcd
* Nodes
    * Kublet
    * kube-Proxy
    * Docker 

## What is the difference between image and a container?
* Docker image is template with basic os, application services and data     
* Docker container is a copy of image with additional resources like cpu, memory, network and storage.    
