# Docker file for Python and PyGDAL deployment
FROM ubuntu:20.04

RUN apt-get update -y && apt-get install -y \ 
    python3 python3-gdal python3-pip \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*
