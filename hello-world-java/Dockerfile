FROM openjdk:8-jdk-alpine

MAINTAINER Madura Dissanayake <madura.d@aeturnum.com>
VOLUME /tmp
RUN mkdir -p /app
ARG JAR_FILE="build/libs/helloWorld-0.1.0.jar"
COPY ${JAR_FILE} /app/app.jar

ENTRYPOINT ["java","-jar","/app/app.jar"]
