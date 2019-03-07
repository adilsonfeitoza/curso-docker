# Curso Docker - Cápitulo 01

### O que é o Docker?

Docker é uma plataforma Open Source escrito em Go, que é uma linguagem de programação de alto desempenho desenvolvida dentro do Google, que facilita a criação e administração de ambientes isolados pra prover ferramentas para deployar e rodar aplicações.

### Outras tecnologias do Docker

- `Docker Compose`: um jeito fácil de definir e orquestrar múltiplos containers.
- `Docker Swarm`:  ferramenta para colocar múltiplos Dockers Host`s para trabalharem juntos em cluster.
- `Docker Hub`: repositório com mais 250 mil imagens diferentes para containers.
- `Docker Machine`: ferramenta que nos permite instalar e configurar em host virtuais.

## Começando a trabalhar com o Docker - comandos

##### docker version
Mostra a versão do docker que estamoa utilizando

##### Docker run hello-world
-Exibe uma mensagem mostrando o que o docker fez para a imagem ser executada.
1. `Docker cliente` Contacta o `Docker daemon`
2. `Docker daemon` faz o download da imagem `hello-world` do `Docker Hub`
3. `Docker daemon` cria um novo container com a imagem e a executa
4. `Docker daemon` exibe a imagem para o `Docker cliente` no terminal

## Começando a trabalhar com Docker

