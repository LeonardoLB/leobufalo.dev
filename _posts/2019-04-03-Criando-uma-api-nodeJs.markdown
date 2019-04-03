---
title: "Criando uma API usando NodeJs utilizando Express.js"
layout: blog
date: 2019-03-28 10:30
tag:
- api
- nodejs
- expressjs
- development
# image: https://koppl.in/indigo/assets/images/jekyll-logo-light-solid.png
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "Criando uma API simples, utilizando NodeJs e Expressjs de forma
simples e rápida"
category: project
author: leo
externalLink: false
---

Nesse post vamos criar de maneira simples uma api usando Nodejs é um micro framework
chamado [Expressjs](https://expressjs.com), que nos permite definir rotas de maneira
muito simples, assim podemos criar uma api em alguns minutos e já poder subir em serviços
como por exemplo: [Heroku](https://www.heroku.com/), ou [Netlify](https://www.netlify.com/).

Primeiro vamos dar uma olhada nos requisitos que precisamos para prosseguirmos:

## Requisitos

- Npm Package
- Nodejs

Vamos começar, escolha um editor de texto da sua preferência, eu particulamente gosto de
utilizar o [Visual Code](https://code.visualstudio.com/), vamos iniciar o projeto, eu irei
deixar o nome como 'exemplo-api-express', abra o projeto em seu terminal e vamos começar a
estruturar nosso pequeno projeto. Abra seu terminal e execute o comendo:
```
npm init -yes
```
Essa linha irá adicionar ao nosso projeto um arquivo chamado package.json e nele irá conter informações
que o compõem. Se você abrir o package.json deverá se parecer com isso:
```
{
  "name": "example-api-express",
  "version": "1.0.0",
  "description": "",
  "main": "rotas.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
Se você não conhece nada sobre o arquivo package.json aconselho uma breve [leitura](https://medium.com/trainingcenter/tudo-que-voc%C3%AA-queria-saber-sobre-o-package-lock-json-mas-estava-com-vergonha-de-perguntar-e70589f2855f) para ajudar a entender melhor. Novamente no terminal vamos instalar nosso framework, executando:
```
npm install express
```
Nesse momento deverá aparecer em seu projeto uma pasta chamada node_modules, nessa pasta contém todas as
nossas dependências, inclusive o express que instalamos a pouco e suas dependências também.

Agora com o express instalado, vamos usufruir desse belíssimo framework, dentro do projeto crie um arquivo javascript chamado "rotas.js".

Agora vamos "requerir" o framework que foi instalado em nossa node_modules para isso vamos adiconar nossa
primeira linha ao arquivo:
```
const express = require('express')
```

e em seguida vamos startar o express:
```
const app = express()
```
Agora nosso arquivo deve estar assim:

[imagemfile]()

Nesse momento com apenas 2 linhas escritas já podemos definir nossa primeira rota e para fazer isso vamos adicionar o seguinte código:
```
app.get('/rota', function (request, response) {
    response.json("Rota testada")
})

app.listen(4001)

```

Explicando o que aconteceu acima, dentro da instâcia do app temos alguns metodos que podemos utilizar
para que possamos definir a rota e os verbos HTTP, caso não conheça os verbos aconselho mais uma [leitura](https://www.devmedia.com.br/servicos-restful-verbos-http/37103), no exemplo mostrei um simples GET.

Neste metodo get passamos dois paramêtros, o primeiro é a rota, o caminho que deverá ser requisitado, e o
segundo paramêtro é a função que será executada, também conhecida como callback.


O nosso callback recebe dois paramêtros, o resquest e response, no response é onde temos informações de
requisições como POST, PUT, DELETE entre outros, e no response é onde devolvemos a resposta da requisição.

O metodo app.listen() informa em qual porta do nosso querio 127.0.0.1 será executado nossa api então basta informar uma porta que não esteja sendo utilizada!

Agora seu arquivo deve estar assim:

[imagemfile2]()

Nesse momento execute em seu terminal
```
node rotas.js
```

Pronto! Se você acessar
```
127.0.0.1/rotas
```

[imagemfile3]()

Ja poderemos visualizar nosso retorno! e nesse momento já criamos uma api com uma rota
que devolve um valor conteúdo com poucas linhas
