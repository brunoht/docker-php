# README

## Desenvolvimento com Docker

Primeira execução, após baixar o reposítório:

```bat
cp .env.example .env
docker build -t brunolohl/laravel .
docker run --rm -it --name lws-server --user $USER:$USER -v $('pwd'):/home/ti brunolohl/laravel bash
```

Dentro do container, instale as dependências do projeto

```bat
composer install
php artisan key:generate
exit
```


## Executando a aplicação

```bat
docker run --rm -d --name lws-server --user $USER:$USER -v $('pwd'):/home/ti -p 8000:8000 brunolohl/laravel
```

### Acessando o container

```bat
docker exec -it lws-server bash
```


### Parando a aplicação

```bat
docker stop lws-server 
```
