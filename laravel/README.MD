# Laravel Playground

Container destinado ao desenvolvimento e execução de projetos Laravel.

## Primeira execução

Caso o seu diretório esteja vazio, você deve iniciar sua aplicação Slim

## Build da imagem

Inicie a imagem do container:

```bat
docker build -t laravel-playground-img .
```

## Executando o container

- Vá até o diretório onde você iniciará o seu projeto

```bat
cd /nome/do/diretorio
```

- Execute o container dentro do diretório que será criado o projeto:
  
```bat
docker run --rm -it --name laravel-playground --user $USER:$USER -v $('pwd'):/app -p 8080:80 laravel-playground-img bash
```

- Uma vez dentro do container, você pode executar toda a instalação utilizando o composer, conforme descrito no manual do Laravel: https://laravel.com/docs/8.x#installation-via-composer

- Ao término da instalação das dependências, saia do container:

```bat
exit
```

# Rodando o servidor com o Docker Compose

Após ter realizado a montagem do seu projeto, você pode utilizar o Docker Compose para instanciar a aplicação e acessá-la em seu navegador enquanto desenvolve. 

Para isso, você precisará copiar os arquivos Dockerfile e docker-compose.yaml para a raiz do seu projeto.

Feito isso, os comandos abaixo ficarão disponíveis para você.

## Iniciando o container

```bat
docker-compose up -d
```

> Ao executar o comando acima você conseguirá abrir a url http://localhost:8080 no seu navegador

## Acessando o container da aplicação

```bat
docker exec -it laravel-playground bash
```

## Parando o container

```bat
docker-compose down
```