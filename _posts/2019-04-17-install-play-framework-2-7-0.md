---
layout: post
title:  "Play Framework 2.7.0 & Undertow"
date:   2019-04-17 16:30:00 +0700
categories: java
tags: java
---
## Play Framework 2.7.0
### Install sbt
```bash
brew install sbt@1
```

### Create a Play project with sbt
```bash
sbt new playframework/play-java-seed.g8
```
Put name for project 
```bash
This template generates a Play Java project 

name [play-java-seed]: 
organization [com.example]:
```
Run below command to download dependencies and start the system 
```bash
sbt run
```
In browser, enter http://localhost:9000 to view the welcome page

To open Play project, use `File -> New -> Project from existing sources`, after choose `sbt` project

## Undertow API

## Connect from client machine to PostgreSQL Google Cloud
* Get my IP: http://ipv4.whatismyv6.com/
* Go to Google Cloud SQL (https://console.cloud.google.com/sql/instances/), choose instance -> Connections tab -> Under Authorized networks -> Click Add network
* Add my IP to it
* Connect from psql
```bash
psql -h 104.154.104.185 -U hungson -W -d hungson
```
-h (host), -U (username), -W (with password), -d (database)
### Some command for psql
* `\l` List all databases
* `\c hungson` switch to database hungson
* Create table `hs_table`
```sql
=> CREATE TABLE hs_table(id int, name varchar(50), PRIMARY KEY(id));
```
* `\dt` List all tables in current database
* `\du` List all user
* View current version of Postgres
```sql
SELECT version();
```
* `\q` Quit Postgres