FROM node:20-alpine
WORKDIR /opt/server
COPY package.json /opt/server
COPY *.js .
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/users" \
    REDIS_URL="redis://redis:6379"

CMD ["node", "server.js"]
