FROM ubuntu:16.04
MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

RUN apt-get update

# Installs
#RUN apt-get install -y python2.7
RUN apt-get install -y python-dev
RUN apt-get install -y python-pycurl
RUN apt-get install -y python-software-properties
RUN apt-get install -y software-properties-common
RUN apt-get install -y python-pip
RUN apt-get install -y build-essential
RUN apt-get install -y curl
RUN apt-get install -y git
RUN apt-get install -y libffi-dev
RUN apt-get install -y libssl-dev
RUN apt-get install -y libpq-dev
RUN apt-get install -y sudo
RUN apt-get install -y vim
RUN apt-get install -y wget

# Installs Python 3.5.
RUN add-apt-repository ppa:fkrull/deadsnakes
RUN apt-get update
RUN apt-get install -y \
    python3.5 \
    python3.5-dev \
    python3-pip
