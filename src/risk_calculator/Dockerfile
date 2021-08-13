FROM python:3.9-slim
LABEL maintainer="stevenbetancurt@hotmail.com"

RUN apt-get update \
#    && apt-get install -y software-properties-common \
#    && rm -rf /var/lib/apt/lists/* \
#    && add-apt-repository ppa:ubuntugis/ppa \
#    && apt-get update \
    && apt-get install -y \
        gdal-bin \
        libgdal-dev \
    && rm -rf /var/lib/apt/lists/* 

ARG CPLUS_INCLUDE_PATH=/usr/include/gdal
ARG C_INCLUDE_PATH=/usr/include/gdal
ARG GDAL_DATA=/usr/local/lib/python3.9/site-packages/fiona/gdal_data

COPY ./requirements.txt ./

RUN pip install -r requirements.txt

# docker build -t stevensotelo/fauno_risk:latest .
# docker tag xx stevensotelo/fauno_risk:latest

