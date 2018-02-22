FROM gcc:4.9
MAINTAINER soujiro0725

RUN apt-get update && apt-get -y install openssh-server ufw curl
RUN mkdir /var/run/sshd
RUN useradd -m soujiro0725 && echo "soujiro0725:soujiro0725" | chpasswd && gpasswd -a soujiro0725 sudo
RUN mkdir -p /home/soujiro0725/.ssh; chown soujiro0725 /home/soujiro0725/.ssh; chmod 700 /home/soujiro0725/.ssh
ADD ./.ssh/authorized_key.pub /home/soujiro0725/.ssh/authorized_key.pub
RUN chown soujiro0725 /home/soujiro0725/.ssh/authorized_key.pub; chmod 600 /home/soujiro0725/.ssh/authorized_key.pub

COPY . /usr/src/server
WORKDIR /usr/src/server
RUN gcc -o server server.c

EXPOSE 22 80

CMD /usr/sbin/sshd -D && ./server
