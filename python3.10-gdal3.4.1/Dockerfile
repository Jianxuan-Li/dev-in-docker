# Docker file for Python and PyGDAL deployment
FROM ubuntu:22.04

# Set timezone
ENV TZ America/Toronto
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE en_US:en

RUN apt-get update -y && apt-get install -y \ 
    python3 python3-gdal python3-pip \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*
