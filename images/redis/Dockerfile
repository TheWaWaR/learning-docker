FROM        centos:centos7
MAINTAINER  weet <thewawar@gmail.com>

RUN rpm -ivh http://mirrors.ustc.edu.cn/fedora/epel/7/x86_64/e/epel-release-7-1.noarch.rpm
RUN yum install -y redis

EXPOSE      6379
ENTRYPOINT  ["/usr/bin/redis-server"]
# sudo docker run -p 6379:6379 -d centos-redis