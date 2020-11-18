FROM ubuntu:20.04

ARG NODE_VERSION=v12.18.2
ARG YARN_VERSION=v1.22.5
ARG NODE_DOWNLOAD_URL=https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION-linux-x64.tar.xz
ARG YARN_DOWNLOAD_URL=https://github.com/yarnpkg/yarn/releases/download/$YARN_VERSION/yarn-$YARN_VERSION.tar.gz

# Set timezone
ENV TZ Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8

ENV PATH /yarnpkg/yarn-$YARN_VERSION/bin:/nodejs/node-$NODE_VERSION-linux-x64/bin:$PATH

RUN apt-get update -y \
    && apt-get install -y \
        #
        # For node-sass
        python2.7 build-essential \ 
        #
        # Utils
        wget curl \
    && ln -s /usr/bin/python2.7 /usr/bin/python \
    && wget -q -O node.tar.xz $NODE_DOWNLOAD_URL \
    && wget -q -O yarn.tar.gz $YARN_DOWNLOAD_URL \
    && mkdir -p /nodejs && mkdir -p /yarnpkg \
    && tar -xJf node.tar.xz -C /nodejs \
    && rm node.tar.xz \
    && tar -xzf yarn.tar.gz -C /yarnpkg \
    && rm yarn.tar.gz \
    && apt-get autoremove -y && apt-get clean && rm -rf /var/lib/apt/lists/*

VOLUME  ["/code"]
WORKDIR /code
EXPOSE 9000