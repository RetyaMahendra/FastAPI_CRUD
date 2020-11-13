# pull official base image
FROM python:3.6-slim-buster

# set working directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# set environment varibles
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install system dependencies
RUN apt-get update \
  && apt-get -y install netcat gcc libssl-dev \
  && apt-get -y install python3-dev default-libmysqlclient-dev build-essential \
  && apt-get clean

# install python dependencies
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools
COPY ./requirements.txt .
RUN pip install -r requirements.txt
#RUN pip install --trusted-host pypi.python.org -r requirements.txt

# add app
#CADD ../app .
