FROM python:3.8

ENV PYTHONUNBUFFERED 1
ARG PROJECT_NAME=equilibrium
ARG APP_CODE_PATH_CONTAINER=/var/www

MAINTAINER ${PROJECT_NAME} LTD

COPY ./requirements.txt /requirements.txt
RUN apt-get update && apt-get install -y postgresql-client
RUN apt-get update && apt-get install -y gcc libc-dev
RUN pip install -r /requirements.txt

WORKDIR ${APP_CODE_PATH_CONTAINER}/${PROJECT_NAME}

RUN useradd user
USER user