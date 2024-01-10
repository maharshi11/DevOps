FROM optimusacr01.azurecr.io/optimus-alpine:3.15.4

RUN apk update \
    && apk upgrade \
    && apk --no-cache add openjdk11 --repository=http://dl-cdn.alpinelinux.org/alpine/edge/community \
    && apk add py3-pip
