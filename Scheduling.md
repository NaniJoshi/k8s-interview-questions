---
id: Scheduling
title: Scheduling pods on a specific Node using taint and toleration
---

## What is Scheduler?

* Scheduler is an object of kubernetes which will schedule pods on nodes if we specify the node name other wise it will launch pod on nodes in randome basis like it will check which node has the resources like memory, cpu, and disk etc.

* Types of Scheduling using rule are as follows. 
     
     * nodeName: it is attribute where we can specify the name of the particuler node on which pod has to launch. it is a simplest form of selecting node.
     
     * nodeSelector: It is an attribute where we can specify node labels, so that the scheduler will check node labels on the node if they matches it will launch the pod on that node. 

     * nodeAffinity / anti-affinity: We can give conditions in nodeAffinity. It is just like nodeSelector with more conditions.

     * podAffinity / anti-affinity: no two pods will run on a single node.

     * taint and tolerance: taint will be defined at node leven and tolerance should be defined at the pod level.
     ```
     kubectl taint node nodename app=web:NoSchedule
     
     to untaint

     kubectl taint node nodename app:NoSchedule-
     ```