FROM python:3.8-slim-buster

RUN apt-get update && \
    apt-get install -y \
        wget=1.20.1-1.1 \
        zip=3.0-11+b1 \
        unzip=6.0-23+deb10u2 \
        git=1:2.20.1-2+deb10u3 \
        curl \
        npm=5.8.0+ds6-4+deb10u2 && \
    pip3 install --no-cache-dir --upgrade pip==20.1.1 && \
    npm install npm@7.0.0 -g && \
    npm install -g serverless@3.36.0 && \
    npm install -g serverless-compose@2.4.0 &&\
    apt-get -q -y clean && \
    rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*

ARG APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE=1
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash
RUN apt-get install -y nodejs

WORKDIR /work

ENTRYPOINT ["/bin/sh"]
