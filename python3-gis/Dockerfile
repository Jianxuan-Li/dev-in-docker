# Docker file for Python development
FROM ubuntu:20.04

# Set timezone
ENV TZ Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE en_US:en

# Set DNS
RUN echo "nameserver 1.1.1.1" >> /etc/resolv.conf

RUN apt-get update -y && apt-get install -y \ 
    wget python3 python3-pip python3-venv \
    # For postgis and Django gis
    gdal-bin python3-gdal \
    # Other utils
    gettext iputils-ping telnet net-tools vim \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*

# Project initalization
RUN mkdir /code
VOLUME  ["/code"]
WORKDIR /code
EXPOSE 8000