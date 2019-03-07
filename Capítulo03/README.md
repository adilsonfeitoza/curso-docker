# Curso Docker - Cápitulo 02

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