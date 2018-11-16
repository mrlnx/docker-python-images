# NodeJS Dockerfile
FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

# environment
ENV MYSQL_USER=mysql \
    MYSQL_GROUP=mysql \
    MYSQL_VERSION=5.7.23\
    MYSQL_DATA_DIR=/var/lib/mysql \
    MYSQL_RUN_DIR=/var/run/mysqld \
    MYSQL_LOG_DIR=/var/log/mysql\

# keep apt up to date
RUN apt-get update -qq
    && DEBIAN_FRONTEND=noninteractive apt-get install -y -q-q \
    && mysql-server=${MYSQL_VERSION}* \
    && sed -i "s/127.0.0.1/0.0.0.0/g" /etc/mysql/mysql.conf.d/mysqld.cnf \
    && mkdir ${MYSQL_RUN_DIR} \
    && chown -R ${MYSQL_USER}:${MYSQL_GROUP} ${MYSQL_RUN_DIR}
    && ln -s /usr/bin/mysql /usr/bin/mysql

ENV PATH "$PATH:/usr/bin/mysql"

# versions
RUN mysql -v

VOLUME ["${MYSQL_DATA_DIR}"]

EXPOSE 3306

CMD ["mysqld_safe"]
