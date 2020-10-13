# AnaSanti-docker-nodejsapp

Empacotar e distribuir uma aplicação real e todas as suas dependências na forma de um container Docker.


## Criando:

```
$ docker build -t anasanti/nodejs-image .
```

## Rodando

```
$ docker run -it -p 3000:3000 -h instance-hostname --rm --name nodejs-image anasanti/nodejs-image:latest
```

## Acessando

http://localhost:3000

Recebera a mensagem

Trabalho de Infra por Ana Santi!

## Imagem

Imagem no docker
https://hub.docker.com/r/anasanti/nodejs-image

