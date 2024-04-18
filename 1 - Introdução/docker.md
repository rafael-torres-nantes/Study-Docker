# Docker

O __Docker__ é uma ferramenta que __simplifica o processo de configuração e execução de aplicações__ por meio de __containers__, que funcionam como __ambientes isolados__ para rodar nossas aplicações. 

Ele oferece a flexibilidade de criar ambientes independentes que podem ser executados em diferentes sistemas operacionais, garantindo também __alto desempenho__ para os projetos.

## Motivos para utilizar Docker

- __Velocidade na configuração do ambiente:__ Containers Docker podem ser configurados rapidamente, reduzindo o tempo necessário para configurar o ambiente de desenvolvimento;

- __Baixa manutenção:__ Os containers são executados exatamente como configurados, reduzindo a necessidade de manutenção constante;

- __Performance:__ Containers Docker compartilham o kernel do sistema operacional hospedeiro, proporcionando melhor desempenho e utilização mais eficiente dos recursos do sistema em comparação com máquinas virtuais tradicionais.

- __Matrix from Hell:__ Antes do Docker, os desenvolvedores muitas vezes enfrentavam desafios relacionados à inconsistência de ambientes, problemas de compatibilidade e dificuldades na configuração de máquinas virtuais, uma realidade que o Docker ajuda a superar.;

<p align="center">
    <img src="/1 - Introdução/assets/matrix.png" width="480" height="320">
</p>

## Instalação no Windows

Para instalar o [Docker no Windows](https://docs.docker.com/desktop/install/windows-install/), utilizaremos o Docker Desktop. Além de fornecer uma interface gráfica para gerenciar o Docker, o Docker Desktop também inclui suporte para executar comandos Docker no terminal.

 É importante observar que existem duas versões disponíveis, e a escolha dependerá da versão do seu sistema operacional Windows.



## Instalação no Linux

A instalação do [Docker no Linux](https://docs.docker.com/desktop/install/linux-install/) varia de acordo com a distribuição utilizada. 

Recomenda-se seguir a documentação oficial do Docker para instalar a versão compatível com sua distribuição. Após a instalação, o Docker estará disponível para uso via terminal.

```bash
sudo apt-get update
sudo apt-get install ./docker-desktop-<version>-<arch>.deb
```

## Instalação no macOS

Assim como no Windows, o [Docker MacOS](https://docs.docker.com/desktop/install/mac-install/)_ também podemos utilizar o Docker Desktop para instalar e gerenciar o Docker. 

O Docker Desktop oferece uma experiência semelhante à do Windows, incluindo suporte para executar comandos Docker no terminal. Portanto, a instalação e o uso do Docker no macOS são semelhantes aos passos realizados no Windows.