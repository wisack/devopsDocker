FROM ubuntu:18.04
RUN apt-get update && apt-get install wget -y && apt-get install git -y 
WORKDIR /usr/local
RUN wget https://golang.org/dl/go1.15.10.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.15.10.linux-amd64.tar.gz
ENV PATH=$PATH:/usr/local/go/bin
WORKDIR /
EXPOSE 8080
RUN git clone https://github.com/docker-hy/material-applications.git
WORKDIR /material-applications/example-backend
ENV REQUEST_ORIGIN=http://localhost:5000
RUN go build
ENTRYPOINT ./server
