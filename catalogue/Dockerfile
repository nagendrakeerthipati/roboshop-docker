FROM node:20-alpine
WORKDIR /opt/server
COPY package.json /opt/server
COPY *.js .
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]
