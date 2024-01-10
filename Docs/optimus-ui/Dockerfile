#FROM node:14.15.4
FROM optimusacr01.azurecr.io/optimus-base-node:current-alpine3.15

COPY . optimus-ui

EXPOSE 4000

# Run the build
#RUN chmod -R 777 /optimus-ui/*;\
#    npm install --global lerna;\
#    cd optimus-ui;\
#    lerna bootstrap;\
#    lerna link;\
#    npm cache clean --force;\
#    lerna run build;\
RUN npm update;\
    chmod -R 750 /optimus-ui/*;
    

CMD ["node", "optimus-ui/packages/ui-server/dist/main.js"]
