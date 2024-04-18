#  Containers

Um __pacote de código que pode executar uma ação__, por exemplo: rodar uma aplicação de Node.js, PHP, Python entre outros. Basicamente, nossos projetos serão executados dentro dos containers que criamos ou utilizamos.

Containers utilizam __imagens__ para poderem ser executados. __Múltiplos containers podem rodar juntos__, exemplo: um para PHP e outro para MySQL;

> Dockerizar: Uma aplicação compatível com Docker

## Container X Imagem

__Imagem e Container__ são recursos fundamentais do Docker:

- __Imagem:__ É o "projeto" que será executado pelo container. Todas as instruções necessárias estão declaradas nela.

- __Container:__ É o Docker rodando uma imagem específica, consequentemente executando o código proposto por ela.

O fluxo é programarmos uma imagem e a executamos por meio de um container;


## Encontrar Imagem na Web

As imagens podem ser encontradas no repositório do Docker: https://hub.docker.com

Neste site podemos __verificar quais as imagens existem__ para tecnologia que estamos procurando, por exemplo: Node.js, e também aprender a como utilizá-las;

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/searchImages.png" width="480" height="320">
</p>

Para executar uma imagem em um container, utilizamos o comando:
```bash
docker run <imagem>
```


## Verificar Containers Executados

O comando __docker ps ou docker container ls__ exibe quais containers estão sendo executados no momento. Utilizando a __flag -a__, também podemos visualizar todos os containers já executados na máquina.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerPS.png" width="480" height="320">
</p>

Este comando é útil para __entender o que está sendo executado e acontece__ no nosso ambiente.

```bash
docker ps -a
```
ou
```bash
docker container ls -a
```

## Executar Container com Interação

Podemos rodar um container e deixá-lo __executando no terminal__utilizando a  __flag -it__. Desta maneira, podemos __executar comandos disponíveis no container__ que estamos utilizando o comando `run`.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerIT.png" width="480" height="320">
</p>

Podemos utilizar a imagem do ubuntu para isso!
```bash
docker run -it <imagem>
```

## Container X VM (Virtual Machine)

- __Container:__ é uma aplicação que serve para um determinado fim, não possui sistema operacional, seu tamanho é de alguns mbs;

- __VM:__ possui sistema operacional próprio, tamanho de GBs, executar diversas funções ao mesmo tempo;

Containers acabam gastando menos recursos para serem executados, por causa do seu uso específico.Enquanto VMs gastam mais recursos, porém podem exercer mais funções.

## Executar Container em Background

Quando iniciamos um container que persiste, ele __ocupa o terminal__.Para evitar isso, podemos executar um container em background utilizando __flag -d__ (detached). Podemos verificar __containers em background com docker ps__ também.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerDetached.png" width="480" height="320">
</p>

Podemos executar um container em background com o seguinte comando:
```bash
docker run -d <imagem>
```

## Portas

Os containers do Docker não têm conexão com o exterior por padrão. Portanto, precisamos expor portas utilizando a __flag -p__ . Por exemplo, `-p 80:80` significa que o container estará acessível na porta 80.
Desta maneira __o container estará acessível na porta 80__;

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerDetachedPort.png" width="480" height="320">
</p>

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerDetachedWeb.png" width="480" height="320">
</p>

Podemos testar este exemplo, em que 3000 é a porta exposta localmente e 80 é a porta do container, com o seguinte comando:
```bash
docker run -d -p 3000:80 <imagem>
```

## Parando Containers

Podemos parar um container utilizando o comando __docker stop <id ou nome>__. Isso libera os recursos que estão sendo utilizados pelo container.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerStop.png" width="480" height="320">
</p>


Podemos verificar os containers rodando com o comando __docker ps__:
```bash
docker stop <id>
```
> Utiliza-se qualquer comando que necessite um id de um container ou imagem com apenas seus __3 primeiros dígitos__
ou
```bash
docker stop <names>
```

## Iniciando Containers

Aprendemos já a parar um container com o stop, para voltar a rodar um container podemos usar o comando __docker start <id>__;

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerStart.png" width="480" height="320">
</p>

```bash
docker start <id>
```
> Lembre-se que o `docker run` sempre cria um novo container

## Definindo Nome do Container

odemos atribuir um nome específico a um container utilizando a __flag --name__. Se não especificarmos um nome, o container receberá um nome __aleatório__, o que pode ser problemático em um ambiente profissional.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerName.png" width="480" height="320">
</p>


A flag `--name` é utilizada juntamente com o comando `run`.
```bash
docker run -d -p 3000:80 --name applicationRafa <imagem>
```

## Verificando Logs

Podemos verificar o registro de atividades de um container utilizando o comando `logs`. Utilizamos da seguinte maneira: __docker logs <id>__.

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerLogs.png" width="480" height="320">
</p>

<p align="center">
    <img src="/2 - Trabalhando com Containers/assets/dockerLogs1.png" width="480" height="320">
</p>

As __últimas ações__ realizadas no container serão exibidas no terminal, o que é útil para monitorar o comportamento e diagnosticar problemas.

Por exemplo:
```bash
docker logs <id>
```

## Removendo Containers

Podemos __remover um container__ da máquina em que estamos executando o Docker utilizando o comando  __docker -rm <id>__. Se o container eestiver em execução ainda, podemos utilizar a  __flag -f__(force) para forçar a remoção.

Após a remoção, o container não será mais listado em `docker ps -a`.

```bash
docker rm -f <id>
```