FROM freeyeti/dev-in-docker:node-12-yarn-2

ENV TZ Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Set LANG
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8

RUN apt-get update -y  \
    && apt-get install -y \
        curl python3 python3-pip python3-venv \
        gdal-bin python3-gdal pipenv gettext \
    && curl -fOL https://github.com/cdr/code-server/releases/download/v3.8.0/code-server_3.8.0_amd64.deb \
    && dpkg -i code-server_3.8.0_amd64.deb \
    && rm code-server_3.8.0_amd64.deb \
    && apt-get autoremove -y && apt-get autoclean -y && rm -rf /var/lib/apt/lists/*
