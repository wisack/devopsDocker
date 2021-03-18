FROM ubuntu:18.04
EXPOSE 5000
RUN apt-get update && apt-get install curl -y && apt-get install git -y
RUN git clone https://github.com/docker-hy/material-applications.git
WORKDIR /material-applications/example-frontend
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash
RUN apt-get install -y nodejs
RUN npm install && npm run build
RUN npm install -g serve
ENTRYPOINT ["serve", "-s", "-l", "5000","build"]
