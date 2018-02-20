FROM gcc:4.9
MAINTAINER soujiro0725

RUN apt-get update && apt-get -y install openssh-server ufw curl
RUN mkdir /var/run/sshd
COPY . /usr/src/server
WORKDIR /usr/src/server
RUN gcc -o server server.c
EXPOSE 80
CMD ["./server"]
