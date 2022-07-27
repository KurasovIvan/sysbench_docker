FROM mysql:8.0-debian
clear
LABEL maintainer="Ivan Kurasov"

RUN apt-get update && apt-get install -y \
      apt-utils \
      zip unzip \
      git \
      curl && \
      apt-get clean && \
      rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN  curl -s https://packagecloud.io/install/repositories/akopytov/sysbench/script.deb.sh | bash && \
    apt -y install sysbench && \
    git clone https://github.com/Percona-Lab/sysbench-tpcc /usr/share/sysbench/percona && \
    cp /usr/share/sysbench/percona/* /usr/share/sysbench/

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=sbt
ENV MYSQL_USER=sb
ENV MYSQL_PASSWORD=sbpass

EXPOSE 3306