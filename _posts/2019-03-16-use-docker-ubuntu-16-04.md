---
layout: post
title:  "How to use Docker on Ubuntu 16.04"
date:   2019-03-10 22:30:00 +0700
categories: java
tags: java
---
![](/images/docker.png)


## 1. Install Docker
Add the GPG key for the official Docker repository to your system:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Add the Docker repository to APT sources:
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

> Note: If you get an error: `sudo: add-apt-repository: command not found`. Let use below command to install
```bash
sudo apt-get install -y software-properties-common
```

Next, update the package database with the Docker packages from the newly added repo:
```bash
sudo apt-get update
```

Check cache to make sure you install Docker from Repo
```bash
apt-cache policy docker-ce
```
If you see output similar to the follow, docker is not installed 
```bash
docker-ce:
  Installed: (none)
  Candidate: 18.06.1~ce~3-0~ubuntu
  Version table:
     18.06.1~ce~3-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
``` 

Finally, install Docker:
```bash
sudo apt-get install -y docker-ce
```

Check status of docker, if you see `active (running)`, docker is running on your system
```bash
sudo systemctl status docker
```

## 2. How to build a docker image
First, create a Dockerfile to define image
```bash
FROM alpine:edge
MAINTAINER hungson.net
RUN apk add --no-cache openjdk8
```
FROM: 
