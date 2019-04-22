# Curso Docker - Cápitulo 06
    A necessidade de usar o Docker Compose, para facilitar ao subir a aplicação
    Configurar o build de vários containers através do docker-compose.yml
    subir e parar os containers de maneira coordenada com Docker Compose

## Praticando com `Docker-compose`

- `docker-compose build` - executa as instruções do arquivo docker-compose.yml para subir as imagens
- `docker-compose up` - sobe os serviços criados
- `docker-compose up -d` - sobe os serviços criados e não bloqueia o terminal
- `docker-compose down` - para os serviços criados.
- `docker-compose ps` - lista os serviços que estão rodando.
- `docker exec -it alura-books-1 ping node2` executa o comando ping node2 dentro do container alura-books-1