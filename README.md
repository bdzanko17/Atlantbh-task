# Simple Microservices Project

## Description

The project consists of two simple services:
 - spring-boot-app - Java application with SpringBoot and connection to postgresql database server
 - node-app - Node.js application with Express
### Node.js 
This is a simple node.js based app that exposes following endpoints:

```
GET /node/api/v1/result
```
### Spring-Boot
This is a simple spring-boot app. The application connects to postgres database (connection defined in `spring-boot-app/app-config.yml`) and connects to node-app.

```
GET /java/api/v1/status
```
```
GET /java/api/v1/node
```

 ##  Instructions for running microservices project with docker-compose
 
 ## Steps
 1. If you have running postgresql service on 5432 you must stop it 
 2. Install Docker egine from https://docs.docker.com/engine/install/
 3. Install Docker compose from https://docs.docker.com/compose/install/
 4. Test previous installation <br />`docker --version` <br /> `docker-compose --version`
 5. Clone this repository `git clone https://github.com/bdzanko17/Atlantbh-task.git`
 6. Make sure that you are positioned in cloned repository
 7. Run `docker-compose build` for  building custom images
 8. Run `docker-compose up` for running dockerized microservices project
 
 ## Test running applications with bash file 
 - Once all services (containers) are running, execute health_check.sh script locally and verify its output is All checks passed.
 
