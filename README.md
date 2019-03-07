Comandos básicos do Docker para podermos baixar imagens e interagir com o container.
Imagens do Docker possuem um sistema de arquivos em camadas (Layered File System) e os benefícios dessa abordagem principalmente para o download de novas imagens.
Imagens são Read-Only sempre (apenas para leitura)
Containers representam uma instância de uma imagem
Como imagens são Read-Only os containers criam nova camada (layer) para guardar as alterações
O comando Docker run e as possibilidades de execução de um container
Segue também uma breve lista dos comandos utilizados:

docker ps - exibe todos os containers em execução no momento.
docker ps -a - exibe todos os containers, independente de estarem em execução ou não.
docker run -it NOME_DA_IMAGEM - conecta o terminal que estamos utilizando com o do container.
docker start ID_CONTAINER - inicia o container com id em questão.
docker stop ID_CONTAINER - interrompe o container com id em questão.
docker start -a -i ID_CONTAINER - inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.
docker rm ID_CONTAINER - remove o container com id em questão.
docker container prune - remove todos os containers que estão parados.
docker rmi NOME_DA_IMAGEM - remove a imagem passada como parâmetro.
docker run -d -P --name NOME dockersamples/static-site - ao executar, dá um nome ao container.
docker run -d -p 12345:80 dockersamples/static-site - define uma porta específica para ser atribuída à porta 80 do container, neste caso 12345.
docker run -d -e AUTHOR="Fulano" dockersamples/static-site - define uma variável de ambiente AUTHOR com o valor Fulano no container criado.
docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM - cria um volume no respectivo caminho do container.
docker inspect ID_CONTAINER - retorna diversas informações sobre o container.

Aprendemos neste capítulo:

A entender o papel do arquivo DockerFile para criar imagens.
O Dockerfile define os comandos para executar instalações complexas e com características específicas.
Vimos os principais comandos como FROM, MAINTAINER, COPY, WORKDIR, RUN, EXPOSE e ENTRYPOINT
A subir uma imagem criada através de um Dockerfile para o Docker Hub e disponibilizar para os desenvolvedores
Lembrando também:

as imagens são read-only sempre
um container é uma instância de uma imagem
para guardar as alterações a docker engine cria uma nova layer em cima da última layer da imagem
Segue também uma breve lista dos comandos utilizados:

docker build -f Dockerfile - cria uma imagem a partir de um Dockerfile.
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM - constrói e nomeia uma imagem não-oficial.
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE - constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.
docker login - inicia o processo de login no Docker Hub.
docker push NOME_USUARIO/NOME_IMAGEM - envia a imagem criada para o Docker Hub.
docker pull NOME_USUARIO/NOME_IMAGEM - baixa a imagem desejada do Docker Hub.

Neste capítulo aprendemos:

Que imagens criadas pelo Docker acessam a mesma rede, porém apenas através de IP.
A criar uma rede e através do seu nome realizar a comunicação entre os containers.
Que durante a criação de uma rede precisamos indicar qual driver utilizaremos, geralmente, o driver bridge.
Segue também uma breve lista dos comandos utilizados:

hostname -i - mostra o ip atribuído ao container pelo docker (funciona apenas dentro do container).
docker network create --driver bridge NOME_DA_REDE - cria uma rede especificando o driver desejado.
docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM - cria um container especificando seu nome e qual rede deverá ser usada.

O Docker Compose não é instalado por padrão no Linux, então você deve instalá-lo por fora. Para tal, baixe-o na sua versão mais atual, que pode ser visualizada no seu GitHub, executando o comando abaixo:

sudo curl -L https://github.com/docker/compose/releases/download/1.15.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
Após isso, dê permissão de execução para o docker-compose:

sudo chmod +x /usr/local/bin/docker-compose
Pronto, o Docker Compose já está instalado no seu Linux!

Nesse aula aprendemos:

A necessidade de usar o Docker Compose
Configurar o build de vários containers através do docker-compose.yml
subir e parar os containers de maneira coordenada com Docker Compose
Segue também uma breve lista dos novos comandos utilizados:

docker-compose up - sobe os serviços criados
docker-compose down - para os serviços criados.
docker-compose ps - lista os serviços que estão rodando.
docker exec -it alura-books-1 ping node2- executa o comando ping node2 dentro do container alura-books-1

Segue a lista com os principais comandos utilizados durante o curso:

Comandos relacionados à informações
docker version - exibe a versão do docker que está instalada.
docker inspect ID_CONTAINER - retorna diversas informações sobre o container.
docker ps - exibe todos os containers em execução no momento.
docker ps -a - exibe todos os containers, independente de estarem em execução ou não.
Comandos relacionados à execução
docker run NOME_DA_IMAGEM - cria um container com a respectiva imagem passada como parâmetro.
docker run -it NOME_DA_IMAGEM - conecta o terminal que estamos utilizando com o do container.
docker run -d -P --name NOME dockersamples/static-site - ao executar, dá um nome ao container.
docker run -d -p 12345:80 dockersamples/static-site - define uma porta específica para ser atribuída à porta 80 do container, neste caso 12345.
docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM - cria um volume no respectivo caminho do container.
docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM - cria um container especificando seu nome e qual rede deverá ser usada.
Comandos relacionados à inicialização/interrupção
docker start ID_CONTAINER - inicia o container com id em questão.
docker start -a -i ID_CONTAINER - inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.
docker stop ID_CONTAINER - interrompe o container com id em questão.
Comandos relacionados à remoção
docker rm ID_CONTAINER - remove o container com id em questão.
docker container prune - remove todos os containers que estão parados.
docker rmi NOME_DA_IMAGEM - remove a imagem passada como parâmetro.
Comandos relacionados à construção de Dockerfile
docker build -f Dockerfile - cria uma imagem a partir de um Dockerfile.
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM - constrói e nomeia uma imagem não-oficial.
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE - constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.
Comandos relacionados ao Docker Hub
docker login - inicia o processo de login no Docker Hub.
docker push NOME_USUARIO/NOME_IMAGEM - envia a imagem criada para o Docker Hub.
docker pull NOME_USUARIO/NOME_IMAGEM - baixa a imagem desejada do Docker Hub.
Comandos relacionados à rede
hostname -i - mostra o ip atribuído ao container pelo docker (funciona apenas dentro do container).
docker network create --driver bridge NOME_DA_REDE - cria uma rede especificando o driver desejado.
