FROM node:latest

LABEL maintainer="Adilson Feitoza"

ENV NODE_ENV=testing
ENV PORT=3000

COPY . /var/www

WORKDIR /var/www

RUN npm install 

ENTRYPOINT [ "npm", "start" ]

EXPOSE $PORT