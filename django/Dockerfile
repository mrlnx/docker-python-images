FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

ENV PYTHONUNBUFFERED 1

RUN apt-get update

RUN apt-get update && apt-get install -qq -y \
    postgresql-client

RUN pip install -U pip

# for now the requirements need to be added in the app
# the reason for this is that i am be able to
# change version numbers of the used packages

#RUN mkdir /django
#WORKDIR /django
#ADD requirements.txt /django/
#RUN pip install -r requirements.txt
#ADD . /django/

EXPOSE 8000
