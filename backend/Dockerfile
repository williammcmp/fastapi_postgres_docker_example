# pull official base image
FROM python:3.9.1-alpine

# set work directory
WORKDIR /usr/backend/app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# copy requirements file
COPY ./requirements.txt /usr/backend/app/requirements.txt

# install dependencies
RUN set -eux \
    && apk add --no-cache --virtual .build-deps build-base \
    libressl-dev libffi-dev gcc musl-dev python3-dev \
    postgresql-dev \
    && pip install --upgrade pip setuptools wheel \
    && pip install -r /usr/backend/app/requirements.txt \
    && rm -rf /root/.cache/pip

# copy project
COPY . /usr/backend/app/