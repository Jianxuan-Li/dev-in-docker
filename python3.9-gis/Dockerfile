# Docker file for Python GIS development
# Do not use this image in production
FROM ubuntu:20.04

# Set timezone
ENV TZ Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE en_US:en

# Set DNS
# RUN echo "nameserver 1.1.1.1" >> /etc/resolv.conf

RUN apt-get update -y && apt-get install -y \ 
    wget python3.9 python3-pip python3-venv \
    # For postgis and Django gis
    gdal-bin python3-gdal libgdal-dev \
    # Other utils
    gettext iputils-ping telnet net-tools vim curl \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3 -

ENV PATH="$PATH:/root/.poetry/bin"

# Project initalization
RUN mkdir /code
VOLUME  ["/code"]
WORKDIR /code
EXPOSE 8000
