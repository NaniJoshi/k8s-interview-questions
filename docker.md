---
id: Docker
title: Docker Document
---

## How to build an Docker image?
Files related to a specific prject can be put into a Folder. In that folder only we have to create a Dockerfile. Then we can build the Docker image using the Dockerfile.

## What is registry?
* Registry is a place where we store images

## What is Docker image?
* Image is nothing but a template which contains Data, OS, and Software.

## What is a Docker Container?
* Container is nothing but a copy of docker image with resources like cpu, memory, Network and storage.

## How to build docker image?
* Using Dockerfile 

* Docker file
```
cat <<EOF > Dockerfile
FROM httpd
COPY index.html /usr/local/apache2/htdocs
ENV name madhu
EOF
```
* build image 
```
docker build -t joshi/newimage:v1
```
* Push image to repository
```
docker login
docker push joshi/image:version(tag)
```

## What is Docker image naming convention?
* joshi/demo:v1
     * joshi is account name
     * demo is image name
     * v1 is tag name

## How to run docker container?
* using specific port use p(small) as option in docker run
```
docker run -d -p 8000:80 joshi/demo:v1
```
* using dynamic port assigning use P (capital) option 
```
docker run -d -P joshi/demo:v1
```

## How to exec into running container?
```
docker exec -it contid /bin/bash
```
