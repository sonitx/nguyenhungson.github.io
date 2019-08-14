---
layout: post
title:  "How to install Oracle JDK 11 on Ubuntu 16.04"
date:   2019-03-10 22:30:00 +0700
categories: java
tags: java
---
## 1. Download JDK 11
You can download JDK 11 from Official Oracle site. 
https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html

## 2. Install Java with .deb file
```bash
sudo dpkg -i jdk-11.0.2_linux-x64_bin.deb
```

## 3. Configure Oracle Java on Ubuntu
```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-11.0.2/bin/java 2
```
```bash
sudo update-alternatives --config java
```

## 4. Make Oracle Java as a default Java compiler
```bash
sudo update-alternatives --install /usr/bin/jar jar /usr/lib/jvm/jdk-11.0.2/bin/jar 2
```
```bash
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-11/bin/javac 2
```
```bash
sudo update-alternatives --set jar /usr/lib/jvm/jdk-11.0.2/bin/jar
```
```bash
sudo update-alternatives --set javac /usr/lib/jvm/jdk-11.0.2/bin/javac
```

## 5. Check Java version 
Run this command below
```bash
java --version
```

And you will see output below if installation is successful.
```bash
java 11.0.2 2019-01-15 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.2+9-LTS)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.2+9-LTS, mixed mode)
```