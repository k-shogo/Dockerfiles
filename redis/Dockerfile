FROM dockerfile/ubuntu
MAINTAINER Shogo Kawaguchi

RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive apt-get -y install \
    build-essential \
    curl && \
  curl -O http://download.redis.io/releases/redis-2.8.9.tar.gz && \
  tar zxvf redis-2.8.9.tar.gz && \
  cd redis-2.8.9 && \
  make && \
  cd src && \
  cp \
    redis-benchmark \
    redis-check-aof \
    redis-check-dump \
    redis-cli \
    redis-sentinel \
    redis-server \
    /usr/local/bin && \
  cd ../.. && \
  rm -r redis-2.8.9 redis-2.8.9.tar.gz

ADD redis.conf /etc/redis.conf
VOLUME /var/lib/redis
CMD ["/usr/local/bin/redis-server", "/etc/redis.conf"]
EXPOSE 6379
