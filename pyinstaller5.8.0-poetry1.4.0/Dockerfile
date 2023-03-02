# Docker file for Python and PyGDAL deployment
FROM ubuntu:22.04

# Set timezone
ENV TZ Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE en_US:en

RUN apt-get update -y && apt-get install -y \ 
    python3 python3-gdal python3-pip curl \
    && pip3 install --no-cache-dir pyinstaller==5.8.0 \
    && curl -sSL https://install.python-poetry.org | POETRY_VERSION=1.4.0 python3 - \
    && apt-get remove -y curl \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*

ENV PATH="/root/.local/bin:$PATH"
