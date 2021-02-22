# Guia de setup para o treinamento

O Objetivo deste documento é listar as linguagens, IDEs e ferramentas que necessitam ser instaladas para os dias subsequentes do treinamento.

## Linguagens

### Ruby
Devido à necessidade de utilizar diferentes versões do ruby baseado nas necessidades de cada contexto sugerimos que o ruby seja instalado utilizando o [RVM (Ruby Version Manager)](https://rvm.io/).

Existe um package do rvm para ubuntu facilitando a instalação: [RVM package for Ubuntu](https://github.com/rvm/ubuntu_rvm)

Após a instalação do rvm instalar a versão 2.4.10 do ruby

Obs:
1.  Seguir as instruções para habilitar o login shell no terminal.
2.  É necessário reiniciar o computador ou realizar logout/login para terminar a instalação do RVM.

### NodeJS
É recomendado que a instalação seja realizada utilizando o [NVM (Node Version Manager)](https://github.com/nvm-sh/nvm) para facilitar a utilização de múltiplas versões no dia a dia.

Após a instalação selecionar como default a versão v12.18.4.

Obs:
1.  É necessário reiniciar o computador ou realizar logout/login para terminar a instalação do NVM.

### Java
Instalar o JDK (pode ser a versão 11) para permitir o desenvolvimento e execução de aplicações em Java. A instalação pode ser feita pelo pacote *default-jdk* do apt-get no Ubuntu.

Tambem será necessario instalar o Maven para gerenciamento das dependências do projeto Java. Pelo instalar o próprio pacote *maven* do apt-get.

### Python
Instalar o Python na versão 3.8 ou superior e o virtualenv para isolar o ambiente python entre os projetos.

A instalação pode ser realizada pelo próprio apt-get, dependendo da versão da maquina seria algo como:

```shell
sudo apt-add-repository ppa:deadsnakes/ppa -y
sudo apt-get update
sudo apt-get install -y python3.8 python3.8-dev python3.8-distutils python3.8-pip
pip3 install virtualenv
```

**Ponto de Atenção:** Muito cuidado com a instalação do python, o ubuntu utiliza internamente o python que já vem pré-instalado (no caso do ubuntu 18 é a versão 2.7), portanto não é recomendado alterar essa instalação ou os links simbólicos dela.

Após o fim da instalação para criar um ambiente virtual podemos seguindos os seguintes passos:
```shell
#Cria o ambiente virtual "myenv" na home do usuario
python3.8 -m venv ~/myenv

#Ativa o ambiente virtual
source ~/myenv/bin/activate

#Desativa o ambiente virtual
deactivate
```

## IDEs
### Visual Studio Code (vscode)

Como IDE para codificação será **necessária** a instalação do Visual Studio Code.

A instalação pode ser realizada pelo [download do .deb no site oficial](https://code.visualstudio.com/download) ou pelo [snap](https://snapcraft.io/code) no Ubuntu.

**Extensões Necessárias:**
- [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)

**Extensões Recomendadas:**
- [Docker for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=formulahendry.docker-extension-pack)
- [Node.js Modules Intellisense](https://marketplace.visualstudio.com/items?itemName=leizongmin.node-module-intellisense)
- [Git Extension Pack](https://marketplace.visualstudio.com/items?itemName=donjayamanne.git-extension-pack)


#### Dbeaver
Como ferramenta para acesso ao banco de dados recomendamos que seja instalado o Dbeaver.

A Instalação pode ser realizada pelo próprio apt-get, snap ou .deb conforme o guia de [instalação oficial do DBeaver](https://dbeaver.io/download/).


## Ferramentas
### Git
Instalar o git que será utilizado como ferramenta de SCM. A instalação pode ser realizada pelo próprio apt-get.

### Docker
O Docker é a ferramenta que utilizaremos para a criação, execução e publicação de containers.

Seguir a instalação descrita no site oficial:

**Ubuntu:** [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/) (Seguir a sessão [Install using the repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

**Mac:** [Install Docker Desktop on Mac](https://docs.docker.com/docker-for-mac/install/)

Após a instalação no ubuntu seguir os passos para executar comandos sem utilizar o root: [Post-installation steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/).

### Docker compose
O Docker Compose é a ferramenta que utilizaremos para realizar a orquestração de containers de forma declarativa e simples facilitando a construções de um ambiente local com múltiplas dependências.

Seguir a instalação descrita no site oficial: [Install Docker Compose](https://docs.docker.com/compose/install/)

### Chrome + chromedriver
Para automação de testes visuais será necessária a instalação do [Chrome](https://www.google.com/chrome/) e o [chromedriver](https://chromedriver.chromium.org/downloads).

### Github
Será necessário criar um cadastro ativo no [Github](https://github.com/join?source=login) com o email corporativo da C&T.

### Terminator (opcional)
Possibilita a abertura de múltiplos terminais na mesma janela. Pode ser instalado pelo próprio apt-get.


## Como validar se tudo está certo?

Executar os comandos abaixo para validar as versões instaladas, as versões podem variar um pouco mas o importante é que não ocorra nenhum erro na execução.


```shell
docker --version
# Docker version 20.10.3, build 48d30b5
docker-compose --version
# docker-compose version 1.28.2, build 67630359
java --version
# openjdk 11.0.9.1 2020-11-04
# OpenJDK Runtime Environment (build 11.0.9.1+1-Ubuntu-0ubuntu1.18.04)
# OpenJDK 64-Bit Server VM (build 11.0.9.1+1-Ubuntu-0ubuntu1.18.04, mixed mode, sharing)
javac --version
# javac 11.0.9.1
nvm --version
# 0.37.2
rvm --version
# rvm 1.29.12 (manual) by Michal Papis, Piotr Kuczynski, Wayne E. Seguin [https://rvm.io]
go version
# go version go1.15.6 linux/amd64
node --version
# v12.18.3
ruby --version
# ruby 2.4.10p364 (2020-03-31 revision 67879) [x86_64-linux]
python3.8 --version
# Python 3.8.6
```
