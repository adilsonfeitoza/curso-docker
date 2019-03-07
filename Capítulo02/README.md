# Curso Docker - Cápitulo 03

### Principais estados de uma container

- `Running`: container em execução.
- `Stopped`: container parado.

## Layered Filesystem
    - Uma imagem possui N camadas, que podem ser compartilhadas entre diferentes imagens.
    - As camadas base de uma imagem são Read Only
    - O container cria uma camada acima das camadas existentes, e essa camada (layer) permite a leitura e escrita. (o container é criado acima das camadas existentes)
    - Essas imagens podem ser reaproveitadas por vários containers
    - Um container é uma instância de uma imagem

### Comandos básicos com containers

- `docker ps`: lista todos os containers ativos.
- `docker ps -a`: lista todos os containers criados, inclusive os parados.
- `docker ps -q`: lista somente os ID_CONTAINERS
- `docker run hello-world`: baixa uma imagem no docker-hub e faz sua inicialização.
- `docker run ubuntu echo 'Olá, Mundo'`: cria um novo container com ubuntu e executa o comando `echo "Olá, Mundo"` dentro do ubuntu.
- `docker run -it ubuntu`: associa o terminal atual com o terminal do container do ubuntu.
- `docker start --help`: mostra as opções de start.
- `docker start ID_CONTAINER`: starta um container já criado.
- `docker start -a -i ID_CONTAINER`: mostra as opções de start.
- `docker stop ID_CONTAINER`: para um container ativo. (Aguarda 10 segundos apos o stop)
- `docker stop -t 0 ID_CONTAINER`: para o container e sem aguardar 10 segundos.
- `docker stop $(docker ps -q)`: para todos os containers ativos.
- `docker rm ID_CONTAINER`: remove um container existente.
- `docker images`: lista as imagens criadas.
- `docker rmi 'nome_da_imagem'`: remove uma imagem criada.
- `docker container prune`: apaga todos os containers parados.

## Praticando com o `Docker Run`
- `docker run dockersamples/static-site`: username do dono da imagem / nome da imagem.
- `docker run -d dockersamples/static-site`: Executa o container em backgroud e printa o ID_CONTAINER
- `docker run -d -P dockersamples/static-site`: Linka uma porta da maquina com a porta do container docker. (é escolhido o número da porta automaticamente)
- `docker run -d -p 12345:80 dockersamples/static-site`: Linka a porta 12345 da maquina com a porta 80 do container.
- `docker run -d -P --name meu-site dockersamples/static-site`: cria um container com nome.
- `docker run -d -P -e AUTHOR='Adilson Feitoza' dockersamples/static-site`: define uma variavel de ambiente chamada AUTHOR
- `docker port ID_CONTAINER`: mostra os mapeamento das portas, na qual pode ser acessada via brownser ex: `http://localhost:32769`.
- `docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM`: cria um volume no respectivo caminho do container.
- `docker inspect ID_CONTAINER`: retorna diversas informações sobre o container.