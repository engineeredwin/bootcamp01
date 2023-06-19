FROM openjdk:8 AS BUILD_IMAGE
LABEL "Project"="GTIprofile"
LABEL "Author"="GTI"
RUN apt update && apt install maven -y
RUN git clone -b docker https://github.com/engineeredwin/bootcamp01.git
RUN cd bootcamp01 && mvn clean install

FROM tomcat:8-jre11

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=BUILD_IMAGE bootcamp01/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
