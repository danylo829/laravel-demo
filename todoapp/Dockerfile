FROM ubuntu:20.04

RUN apt update && DEBIAN_FRONTEND=noninteractive apt install -y --no-install-recommends git composer php-xml zip unzip php-zip php-mysql

RUN git clone https://github.com/laravel/quickstart-basic quickstart

WORKDIR "/quickstart"
COPY ./.env ./

RUN composer install

EXPOSE 8000

COPY ./wait.sh /usr/wait.sh
RUN chmod +x /usr/wait.sh