# NodeJS Dockerfile
FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

# keep apt up to date
RUN apt-get update -qq

# install nodejs
RUN apt-get install -y nodejs npm

# create symbolic link
#RUN ln -s /usr/bin/nodejs /usr/bin/node

#ENV PATH "$PATH:/usr/bin/node"
#ENV PATH "$PATH:/usr/bin/npm"

# install dependencies
ADD . /tmp
RUN cd /tmp && npm install

# versions
RUN node -v
RUN npm -v

EXPOSE 3000

# bash
CMD ["node"]
