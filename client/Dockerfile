FROM gcc:4.9
MAINTAINER soujiro0725

COPY . /usr/src/client
WORKDIR /usr/src/client
RUN gcc -o client client.c
EXPOSE 80
CMD ["./client"]
