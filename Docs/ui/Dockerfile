#FROM node:14.15.4
FROM optimusacr01.azurecr.io/optimus-base-node:current-alpine3.15

COPY build build

EXPOSE 5000

# Run the build
RUN node --version;\
    npm --version;\
    npm install -g serve;


#CMD ["serve", "-s",  "build", "-l", "5000"]
CMD ["serve", "-s",  "build"]

