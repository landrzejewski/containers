FROM node:18-alpine
ARG USERS_DIR=/users/
RUN mkdir /users
COPY *.js ${USERS_DIR}
COPY package.json ${USERS_DIR}
WORKDIR ${USERS_DIR}
RUN npm install
EXPOSE 3000
ENTRYPOINT ["node", "index.js"]
