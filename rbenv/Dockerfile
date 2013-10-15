# sshd

FROM base

RUN apt-get update; apt-get upgrade -y

RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:password' |chpasswd

RUN apt-get install -y git curl g++ zlib1g-dev libssl-dev libreadline-dev libyaml-dev libxml2-dev libxslt-dev sqlite3 libsqlite3-dev
RUN git clone git://github.com/sstephenson/rbenv.git ~/.rbenv
RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc
RUN git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

EXPOSE 22
CMD    /usr/sbin/sshd -D
