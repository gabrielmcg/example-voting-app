FROM node:5.11.0

WORKDIR /app

ARG PROXY
RUN npm config set proxy $PROXY
RUN npm config set https-proxy $PROXY

RUN npm install -g nodemon
ADD package.json /app/package.json
RUN npm config set registry http://registry.npmjs.org
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
