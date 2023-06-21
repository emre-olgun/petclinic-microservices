FROM openjdk:11-jre
ENV DOCKERIZE_VERSION v0.6.1
ARG EXPOSED_PORT=8761
ENV SPRING_PROFILES_ACTIVE docker,mysql
ADD https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz dockerize.tar.gz
RUN tar -xzvf dockerize.tar.gz
RUN chmod +x dockerize
ADD ./target/*.jar app.jar
EXPOSE ${EXPOSED_PORT}
ENTRYPOINT ["java", "-jar", "app.jar"]