# sshd

FROM centos

RUN yum -y update

RUN yum -y install openssh-server

EXPOSE 22
CMD /usr/sbin/sshd
