# AnaSanti-docker-nodejsapp

Empacotar e distribuir uma aplicação real e todas as suas dependências na forma de um container Docker.

# Conteúdo

Dockerfile:

```
FROM node:10-alpine
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
WORKDIR /home/node/app
# Install app dependencies
COPY package*.json ./
USER node
RUN npm install
COPY --chown=node:node . .
EXPOSE 8080
CMD [ "node", "app.js" ]
```

app.js:

```
const express = require('express');
const app = express();
app.get('/', function (req, res) {
    res.send('Trabalho de Infra por Ana Santi!');
});
app.listen(3000, function () {
    console.log('Servidor na porta 3000!');
}); 
```


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

##Package

O package.json enconstrará as informações como nome, versão, autor e descrição.
Já no package-lock.json encontrá as informações da aplicação node e suas dependências

