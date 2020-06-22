FROM python:3.8

ENV PYTHONUNBUFFERED 1
ENV PROJECT_NAME ${PROJECT_NAME}
ENV APP_CODE_PATH_CONTAINER ${APP_CODE_PATH_CONTAINER}

MAINTAINER ${PROJECT_NAME} LTD

COPY ./requirements.txt /requirements.txt
RUN apt-get update && apt-get install -y postgresql-client
RUN apt-get update && apt-get install -y gcc libc-dev
RUN pip install -r /requirements.txt

RUN mkdir ${APP_CODE_PATH_CONTAINER}/${PROJECT_NAME}
WORKDIR ${APP_CODE_PATH_CONTAINER}/${PROJECT_NAME}
COPY ./ ${APP_CODE_PATH_CONTAINER}/${PROJECT_NAME}

RUN useradd user
USER user