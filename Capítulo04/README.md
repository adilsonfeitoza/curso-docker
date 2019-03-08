# Curso Docker - Cápitulo 04
    Neste capítulo vamos começar a criar nossas próprias imagens, podendo ser reutilizadas em outros locais
    

## Praticando com o `DockerFile`
- `docker build -f Dockerfile`: cria uma imagem a partir de um Dockerfile.
- `docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM` - constrói e nomeia uma imagem não-oficial.
- `docker build -f Dockerfile -t adilsonf/node .`: faz o build da imagem criada, com uma tag informando o caminho para o Dockerfile
- `docker run -d -p 8080:3000 adilsonf/node`: cria um container com a imagem criada

- `docker login`: inicia o processo de login no Docker Hub.
- `docker push NOME_USUARIO/NOME_IMAGEM` - envia a imagem criada para o Docker Hub.
- `docker pull NOME_USUARIO/NOME_IMAGEM` - baixa a imagem desejada do Docker Hub.