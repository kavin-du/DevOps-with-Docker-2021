FROM ubuntu:latest

WORKDIR /usr/src/app

EXPOSE 5000

RUN apt update && apt install -y curl

RUN curl -sL https://deb.nodesource.com/setup_14.x | bash

RUN apt install -y nodejs

COPY . .

RUN npm install

RUN REACT_APP_BACKEND_URL=http://localhost:8080 npm run build

RUN npm install -g serve

#ENV REACT_APP_BACKEND_URL=http://localhost:8080/ping

CMD ["serve", "-s", "-l", "5000", "build"]


