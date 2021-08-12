FROM python:3.9-slim
LABEL maintainer="stevenbetancurt@hotmail.com"

ENV VERSION=0.2.0
ENV SECRET_KEY=
ENV MONGO_USER=
ENV MONGO_PWD=
ENV MONGO_DB=
ENV MONGO_PORT=
ENV MONGO_SERVER=
ENV DEBUG=
ENV ORM_PATH=/app/service/orm

WORKDIR /app

COPY ./requirements.txt ./

RUN apt-get update \
    && apt-get install -y \
        vim \
        wget \
        unzip \
    && rm -rf /var/lib/apt/lists/* 

RUN pip install -r requirements.txt \
    && cd /app \
    && wget https://github.com/CIAT-DAPA/dci_fauno/releases/download/${VERSION}-service/service.zip \
    && unzip service.zip \
    && rm service.zip \
    && rm requirements.txt

EXPOSE 80

CMD ["python", "/app/service/api.py"]

# docker build -t stevensotelo/fauno_service:latest .
# docker tag xx stevensotelo/fauno_service:latest

# docker run -it --rm --env-file ./.env  -p 5000:80 --name fauno_service stevensotelo/fauno_service:latest /bin/bash
# docker run -d --rm --env-file ./.env  -p 5000:80 --name fauno_service stevensotelo/fauno_service:latest
