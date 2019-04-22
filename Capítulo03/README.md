# Curso Docker - Cápitulo 03
    Neste capítulo vamos começar a trabalhar com volumes.
    Os containers são voláteis, não são nenhum dados apos removidos, por isso a necessidade de usar `Volumes`
    Podemos criar uma pasta ( que será nosso volume), que ira apontar para o `Docker Host`. Quando escrever na pasta sera escrito no `Docker Host`

## Praticando com o `Volumes`
- `docker run -v '/var/www' ubuntu`: cria um volume no respectivo caminho do container.
- `docker run -it -v 'C:\Users\adilson\Desktop:/var/www' ubuntu`: cria um volume no respectivo caminho informado.
- `docker inspect ID_CONTAINER`: retorna diversas informações sobre o container.

- `docker run -d -p 8080:3000 -v 'C:\Users\gold360\desktop\volume-exemplo:/var/www' -w '/var/www' node npm start`: cria um volume, sobe um container com node, o roda o comando `npm start` dentro do container, associa a porta 8080 com a 3000 do container e inicia o container dentro da pasta `/var/www`
- `docker run -d -p 8080:3000 -v "$(pwd):/var/www" -w /var/www' node npm start`: cria o volume na pasta que estiver executando o comando. 