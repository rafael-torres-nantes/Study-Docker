# Containers e Imagens

## Oque são imagens?

Imagens __são originadas de arquivos que programamos__ para que o Docker crie uma estrutura que execute determinadas ações em containers;

Elas contém informações como: imagens base, diretório base, comandos a serem executados, porta da aplicação e etc;

Ao rodar um container baseado na imagem, __as instruções serão executadas em camadas__;

> Arquivo DockerFile par construir imagem


## Como escolher uma boa imagem

Podemos fazer download das imagens em: https://hub.docker.com;

Porém __qualquer um pode fazer upload de uma imagem__, isso é um problema;

<p align="center">
    <img src="/3 - Imagens e Avançando Containers/assets/dockerSearchImages.png" width="480" height="320">
</p>

Devemos então nos atentar as __imagens oficiais__;
Outro parâmetro interessante é a __quantidade de downloads__ e a __quantidade de stars__;

