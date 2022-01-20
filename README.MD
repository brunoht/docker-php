# PHP Playground

## Download

```bat
git clone https://github.com/brunoht/docker-php.git
cd docker-php
```

## Build da imagem

```bat
docker build -t php-playground-img .
```

## Executando o container

Vá até o diretório onde está a aplicação PHP.

```bat
docker run --rm -it --name php-playground --user $USER:$USER -v $('pwd'):/app -p 8080:80 php-playground-img bash
```

## Comandos PHP

Inicia o servidor web buil-in do PHP

```bat
php -S 0.0.0.0:80 -t public
```