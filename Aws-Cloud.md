---
id: AWS
title: Amazon Web Services
---

# Overview of AWS
link : https://d1.awsstatic.com/whitepapers/aws-overview.pdf

# Networking
## IP Address
     * IPv4 --> 32 bit -- Decimal (0-9)
     * IPv6 --> 128 bit -- Hexa decimal

## IPv4
* Binary -- 0 and 1
* decimal -- 0-9
* convert binary to decimal
* numbers are devided into 8 bits
    * 00000000.00000000.00000000.00000000 = 0.0.0.0
    * 11111111.11111111.11111111.11111111 = 255.255.255.255

* Private IP's Range:
    * 10.0. 0.0/8 IP addresses: 10.0. 0.0 – 10.255. 255.255.
    * 172.16. 0.0/12 IP addresses: 172.16. 0.0 – 172.31. 255.255.
    * 192.168. 0.0/16 IP addresses: 192.168. 0.0 – 192.168. 255.255.    

# Subnetting
## Subnet calculation
* Total VPC size
    * 2^n - 5 >= 200
* Subnet size
    * 2^n - 5 >= 100 
    * 2^n - 5 >= 30
    * 2^n - 5>= 20

# EC2 -- Elastic Compute Cloud
## Components of EC2
* AMI(amazon machine image) - OS Image 
* Instance type -- RAM and CPU
* VPC (virtual private cloud) -- Network
* EBS (Elastic Block Storage) -- storage
* Security
* Tags
* ssh

## Instance types
link : https://aws.amazon.com/ec2/instance-types/

## User Data
* user data is used to perfom some tasks at the time of instance launch. It executed only once and used to automate tasks. it wont execute again if we reboot the instance.

# Storage
## Block storge (EBS)
* smallest unit of storage is called block storage 
* we can attach this storage to one instance at a time

## File storage System (EFS--Elastic File Storage)
* It is Dynamic and can be attached to multiple instances
* if we change data it will reflects in all other instances
* Example are efs,nfs etc...

## Object Storage (S3-simple storage service)
* It is Url based storage 
* data will be stored in the form of objects
* It is a static data storage.

## Volume types
* Root volume type
* Data volume type

link : https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html
