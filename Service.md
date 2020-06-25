---
id: Servie
title: Services in k8s
---

# What is Sevice in k8s?
* Service is a kubernetes object which will be used to provide ip address and 
* Types of services
     * ClusterIp: For internal service communication we use ClusterIP service type. In-order to reach the specific pod/application from outside we need to portforward it.
     * NodePort: It is used to reach or communicate with application or service from outside.