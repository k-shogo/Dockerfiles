# sshd
#
# VERSION               0.0.1

FROM centos

RUN yum -y update

RUN yum -y install openssh-server

EXPOSE 22
CMD /usr/sbin/sshd
