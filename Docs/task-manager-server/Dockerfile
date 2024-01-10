

FROM optimusacr01.azurecr.io/optimus-base:alpine3.15.4

ADD rest/build/libs/rest.jar /temp/app.jar

ARG BUILD_PROFILE=dev
ENV BUILD_PROFILE=$BUILD_PROFILE
RUN echo $BUILD_PROFILE
EXPOSE 8286

# Run the jar file
CMD ["java", "-jar", "-Dspring.config.location=/tmp/conf/application.yml","-Dspring.profiles.active=default", "-Djava.security.egd=file:/dev/./urandom", "/temp/app.jar"]

