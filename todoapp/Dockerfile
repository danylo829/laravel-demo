FROM ubuntu:20.04

RUN apt update && DEBIAN_FRONTEND=noninteractive apt install -y --no-install-recommends git composer php-xml zip unzip php-zip php-mysql

RUN git clone https://github.com/laravel/quickstart-basic quickstart

COPY ./wait.sh /usr/wait.sh
RUN chmod +x /usr/wait.sh

WORKDIR "/quickstart"
COPY ./.env ./

RUN composer install

EXPOSE 8000

CMD /usr/wait.sh --timeout=0 mysql_db:3306 && php artisan migrate && php artisan serve --host 0.0.0.0