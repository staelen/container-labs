FROM node:latest

ENV DB_HOST=nwdb DB_PORT=3306 DB_USER=root DB_PASSWORD=changeit APP_PORT=3000 APP_DIR=/northwind

WORKDIR ${APP_DIR}

ADD config config
ADD public public
ADD views views
ADD main.js .
ADD package.json .

RUN npm install

EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]