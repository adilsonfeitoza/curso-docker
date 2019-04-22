# Curso Docker - Cápitulo 05
    Neste capítulo aprendemos ue imagens criadas pelo Docker acessam a mesma rede, porém apenas através de IP.
    A criar uma rede e através do seu nome realizar a comunicação entre os containers.
    Que durante a criação de uma rede precisamos indicar qual driver utilizaremos, geralmente, o driver bridge.
    

## Praticando com `NetWork`
- `hostname -i`: mostra o ip atribuído ao container pelo docker (funciona apenas dentro do container).
- `docker network ls`: lista as redes criadas
- `docker network create --driver bridge NOME_DA_REDE`: cria uma rede especificando o driver desejado.
- `docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM`: cria um container especificando seu nome e qual rede deverá ser usada.
- `docker run -d --name meu-mongo --network minha-rede mongo`: sobe um container com mongo dentro da minha-rede
- `docker run -d -p 8080:3000 --name alura-books --network minha-rede douglasq/alura-books:cap05`: sobe uma aplicação node, na mesma rede criada, que vai utilizar o banco de dados mongo