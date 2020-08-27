FROM ubuntu AS clone

#Install git
RUN apt-get update
RUN apt-get install -y git
WORKDIR /workspace
RUN git clone https://github.com/kkenan/basic-microservices

FROM maven:3.6.1-jdk-8-slim AS build
WORKDIR /workspace
COPY --from=clone /workspace/basic-microservices/spring-boot-app/src /workspace/src
COPY --from=clone /workspace/basic-microservices/spring-boot-app/pom.xml /workspace
RUN mvn -f pom.xml clean package

FROM openjdk:8-jdk-alpine
WORKDIR /workspace
COPY --from=build /workspace/target/*.jar /workspace/app.jar
ADD app-config.yml .
RUN ls
EXPOSE 8080
ENTRYPOINT ["java","-jar","/workspace/app.jar","--spring.config.location=/workspace/app-config.yml"]
