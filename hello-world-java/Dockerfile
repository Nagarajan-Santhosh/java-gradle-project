#FROM ubuntu:latest

#MAINTAINER Madura Dissanayake <madura.d@aeturnum.com>

#VOLUME /tmp

#RUN apt update && apt upgrade \ 
 #   && cd /tmp \ 
  #  && apt install -y wget unzip \ 
   # && wget https://services.gradle.org/distributions/gradle-6.3-bin.zip \ 
   # && unzip gradle-*.zip \ 
   #  && mkdir /opt/gradle \ 
   # && cp -pr gradle-*/* /opt/gradle \ 
   # && touch /etc/profile.d/gradle.sh \ 
   # && echo "export PATH=/opt/gradle/bin:${PATH}" >> /etc/profile.d/gradle.sh \ 
   # && chmod +x /etc/profile.d/gradle.sh \ 
   # && source /etc/profile.d/gradle.sh \ 
   # && gradle -v \ 
 # && mkdir -p /app

#ARG JAR_FILE="build/libs/helloWorld-0.1.0.jar"

#COPY ${JAR_FILE} /app/app.jar

#ENTRYPOINT ["java","-jar","/app/app.jar"]


FROM gradle:7.6.0-jdk8-jammy

VOLUME /tmp

WORKDIR /app

COPY . .

RUN ./gradlew build

#ARG JAR_FILE="/app/build/libs/*.jar"
#RUN /app/build/libs/*.jar /app/app.jar

EXPOSE 8181/tcp

ENTRYPOINT ["java","-jar","/app/build/libs/helloWorld-0.1.0.jar"]


