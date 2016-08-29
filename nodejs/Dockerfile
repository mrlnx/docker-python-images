# NodeJS Dockerfile
FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

# keep apt up to date
RUN apt-get update -qq

# install nodejs
RUN apt-get install -y nodejs npm

EXPOSE 3000

# bash
CMD ["/bin/bash/node"]
