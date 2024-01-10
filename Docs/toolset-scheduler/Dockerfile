FROM optimusacr01.azurecr.io/optimus-base:alpine3.15.4

ADD rest/build/libs/rest.jar /temp/app.jar

ARG BUILD_PROFILE=dev
ENV BUILD_PROFILE=$BUILD_PROFILE
RUN echo $BUILD_PROFILE
EXPOSE 9090

RUN apk add --no-cache tini openrc busybox-initscripts ;
RUN mkdir -p /etc/periodic/always/ ;
RUN echo '* * * * * run-parts /etc/periodic/always' > /var/spool/cron/crontabs/root ;
RUN echo '#!/bin/sh' > /etc/periodic/always/schedulefile ;
RUN echo '/usr/bin/python3 /opts3/optimus-share/touch_new.py' >> /etc/periodic/always/schedulefile ;
RUN chmod a+x /etc/periodic/always/schedulefile ;

# Run the jar file
CMD ["java", "-jar", "-Dspring.config.location=/tmp/conf/application.yml","-Dspring.profiles.active=default", "-Djava.security.egd=file:/dev/./urandom", "/temp/app.jar"]

