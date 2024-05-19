FROM ubuntu

RUN apt-get update
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get upgrade -y
RUN apt-get install -y nodejs

#WORKDIR /app

COPY package.json ./app/package.json
COPY package-lock.json ./app/package-lock.json

RUN cd app && npm install

COPY index.js ./app/index.js


ENTRYPOINT [ "node" , "./app/index.js" ]