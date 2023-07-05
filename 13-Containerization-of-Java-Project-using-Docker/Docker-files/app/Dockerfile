FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/colossus06/20-realtime-devops-projects.git
RUN cd 20-realtime-devops-projects/13-Containerization-of-Java-Project-using-Docker/ && mvn -f ./pom.xml install -X

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE 20-realtime-devops-projects/13-Containerization-of-Java-Project-using-Docker/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]