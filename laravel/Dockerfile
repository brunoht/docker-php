FROM ubuntu:20.04

# altere para o mesmo nome do usuario do seu sistema operacional
ARG USER=ti

RUN apt update && apt install php-fpm php-mysql php-mbstring php-xml php-bcmath php-cli unzip vim -y

RUN apt install curl -y && curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php && \
  php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer

RUN apt install php-curl -y

RUN useradd -ms /bin/bash ${USER}

USER ${USER}

WORKDIR /app

EXPOSE 8000

CMD [ "php", "artisan", "serve", "--host=0.0.0.0" ]