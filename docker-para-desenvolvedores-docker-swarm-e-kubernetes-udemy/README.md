# Curso da Udemy
* [Link do curso](https://www.udemy.com/course/docker-para-desenvolvedores-com-docker-swarm-e-kubernetes)
* [Link do material](https://github.com/matheusbattisti/curso_docker)


# Trabalhando com Containers

## O que é Docker?

* O **Docker** é um software que **reduz a complexidade de setup** de aplicações;
* Onde **configuramos containers**, que são como servidores para rodar nossas aplicações;
* Com facilidade, podemos criar **ambientes independentes** e que funcionam em diversos SO's;
* E ainda deixa os projetos **performáticos**;

## Por quê Docker?

* O Docker proporciona mais velocidade na configuração do ambiente de um dev;
* **Pouco tempo gasto em manutenção**, containers são executados como configurados;
* **Performance** para executar aplicação, mais performático que uma VM;
* Nos livra da **Matrix from Hell**;

# Conhecendo a Matrix from Hell

![](imgs/01.png)

## Diferença das versões de Docker

### Qual versão utilizar?

* O **Docker** é dividido em duas versões: **CE x EE**
* CE é a **Community Edition**, edição gratuita, que nos possibilita utilizar o Docker normalmente, é a que vamos optar;
* EE é a **Enterprise Edition**, edição paga, há uma garantia maior das versões que são disponibilizadas e você tem suporte do time do Docker;

## Testando o Docker!

* Vamos testar o Docker utilizando uma **imagem real**;
* Para rodar containers utilizamos o comando **docker run**;
* Neste comando **podemos passar diversos parâmetros**;
* Neste exemplo vamos passar apenas o nome da imagem que é **docker/whalesay**
* Um comando chamado cowsay e uma mensage;

```docker

<!-- cowsay envia mensagem para o container -->
<!-- Vai ver se existe a imagem de forma local para fazer o cache -->
<!-- Se nao conseguir vai puxar a imagem no repositório docker -->
<!-- executa o que a imagem possui em forma de container e retorna o resultado -->
docker run docker/walesay cowsay Hello_World

```

## O que são containers?

* Um **pacote de código que pode executar uma ação**, por exemplo: rodar uma aplicação de Node.js, PHP, Python e etc;
* Ou seja, os nossos projetos serão executados dentro dos containers que criarmosutilizarmos;
* **Containers utilizam imagens** para poderes ser executados;
* **Múltiplos containers podem rodar juntos**, exemplo: um para PHP e outro para MySQL

## Container X Imagem

* **Imagem e Container** são recursos fundamentais do Docker;
* Imagem é o **"projeto"** que será executado pelo container, todas as instruções estarão declaradas nela;
* Container é o **Docker rodando alguma imagem**, consequentemente executando algum código proposto por ela;
* O fluxo é: programamos uma imagem e a executamos por meio de um container;

## Onde encontrar imagens?
* Vamos encontrar imagens no repositório do Docker: <https://hub.docker.com>
* Neste site podemos **verificar quais as imagens existem** da tecnologia que estamos procurando, por exemplo: Node.js;
* E também aprender a como utilizá-las;
* Vamos executar uma imagem em um container com o comando: 

```docker
docker run <imagem>

<!-- download ubuntu:latest -->
docker run ubuntu

<!-- Abre o container com o terminal e voce consegue acessar tudo dentro do ubuntu -->
docker run -it ubuntu

<!-- Mostra os containers rodando -->
docker ps

```

## Verificar containers executados

* O comando **docker ps (versão antiga) ou docker container ls(versão recente)** exibe quais containers estão sendo executados no momento;
* Utilizando a flag -a, temos também todos os containers já executados na máquina;
* Este comando é útil para **entender o que está sendo executado e acontece** no nosso ambiente;

```docker

<!-- MOSTRA OS CONTAINERS RODANDO QUE ESTAO ATIVOS -->
docker ps

<!-- EXECUTA UM NOVO CONTAINER -->
docker run ubuntu

<!-- APARECE SOMENTE OS ATIVOS -->
docker ps

<!-- APARECE OS CONTAINERS EXECUTADOS -->
docker ps -a


```

## Executar container com interação

* Podemos rodar um container e deixá-lo **executando no terminal**;
* Vamos utilizar a **flag -it**;
* Desta maneira **podemos executar comandos disponíveis no container** que estamos utilizando o comando run;
* Podemos utilizar a imagem do ubuntu para isso!

```docker

<!-- ABRE TERMINAL COM JAVASCRIPT -->
docker run -it node

<!-- VOCE PODE EXECUTAR CÓDIGO JAVASCRIPT -->

```

## Container X VM (Virtual Machine)

* **Container é uma aplicação que serve para um determinado fim**, não possui sistema operacional, seu tamanho é de alguns mbs;
* VM possui sistema operacional próprio, tamanho de gbs, **pode executar diversas funções ao mesmo tempo**;
* Containers acabam gastando menos recursos para serem executados, por causa do seu uso específico;
* VMs gastam mais recursos, porém podem exercer mais funções;

## Executar container em background

* Quando iniciamos um container que persiste, **ele fica ocupando o terminal**;
* Podemos exeutar um container em background, para não precisar ficar com diversas abas de terminal aberto, utilizamos a **flag -d** (detached);
* Verificamos **containers em background com docker ps** também;
* Podemos utilizar o nginx para este exemplo!

```docker

<!-- nginx servidor web como se fosse apache -->
docker run nginx

<!-- PARA CONTAINER -->
docker stop <NOME_DO_CONTAINER>

<!-- NOME NAO VAI MAIS APARECER -->
docker ps

<!-- RODA EM BACKGROUND -->
docker run -d nginx

```

## Expor portas

* Os **containers de docker não tem conexão com nada de fora deles**;
* Por isso precisamos expor portas, a **flag é a -p** e podemos fazer assim: -p 80:80
* Desta maneira **o container estará acessível na porta 80**;
* Podemos testar este exemplo com o nginx!

```

<!-- DETACHED E EXPONDO A PORTA -->
docker run -d -p 80:80 nginx

docker stop <NOME_DO_CONTAINER>

<!-- PRIMEIRA PORTA A QUE VOCE QUER EXPOR NA SUA MÁQUINA -->
dokcer run -d -p 3000:80 nginx

```


## Parando containers

* Podemos parar um container com o comando **docker stop </id ou nome_do_container/>**

* Desta maneira estaremos liberando recursos que estão sendo gastos peolo mesmo;

* Podemos verificar os containers rodando com o comando **docker ps**;


## Iniciando container

* Aprendemos já a parar um container com o stop, para voltar a rodar um container podemos usar o comando **docker start </id/>**;
* Lembre-se que **o run sempre cria um novo container**;
* Então caso seja necessário aproveitar um antigo, opte pelo start;


## Definindo nome do container

* Podemos definir um nome do container com a flag **--name**;
* Se não colocamos, **recebemos um nome aleatório**, o que pode ser um problema para uma aplicação profissional;
* A flag run é inserida junto do **comando run**;








