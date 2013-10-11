# sshd
#
# VERSION               0.0.1

FROM base

RUN apt-get update

RUN apt-get install -y openssh-server

RUN mkdir /var/run/sshd
RUN echo 'root:password' |chpasswd

EXPOSE 22
CMD /usr/sbin/sshd -D
