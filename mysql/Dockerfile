FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

# environment
ARG MYSQL_USER=mysql
ARG MYSQL_GROUP=mysql
ARG MYSQL_VERSION=5.7.23
ARG MYSQL_DATA_DIR=/var/lib/mysql
ARG MYSQL_RUN_DIR=/var/run/mysqld
ARG MYSQL_LOG_DIR=/var/log/mysql

# keep apt up to date
RUN apt-get update -qq

RUN DEBIAN_FRONTEND=noninteractive
RUN apt-get install -y mysql-server
RUN sed -i "s/127.0.0.1/0.0.0.0/g" /etc/mysql/mysql.conf.d/mysqld.cnf
RUN mkdir ${MYSQL_RUN_DIR}
RUN chown -R ${MYSQL_USER}:${MYSQL_GROUP} ${MYSQL_RUN_DIR}
RUN ln -s /usr/bin/mysql /usr/bin/mysql

ENV PATH "$PATH:/usr/bin/mysql"

# versions
RUN mysql -v

VOLUME ["${MYSQL_DATA_DIR}"]

EXPOSE 3306

CMD ["mysqld"]
