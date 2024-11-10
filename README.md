# BookNow-Microservices

Este é o repositório principal do projeto **BookNow**, que utiliza uma arquitetura de microserviços para gerenciar diferentes serviços de um sistema de compra com pontos e avaliações de livros. Cada serviço é gerenciado como um repositório separado, e todos eles são integrados aqui usando submódulos Git.

## Serviços

O repositório contém os seguintes microserviços:

1. **book-now_servico_registra**: Serviço de registro (Eureka Server).
2. **book-now_servico_apigateway**: API Gateway para roteamento de requisições.
3. **Microservico-livro**: Serviço para gerenciar livros.
4. **booknow_avaliacao**: Serviço para avaliações de livros.
5. **BookNow_Usuarios**: Serviço de gerenciamento de usuários.
6. **book-now_servico_pontos**: Serviço para gerenciamento de pontos.


O **booknow_database** tem que importar no MySQL.

## Como Clonar o Repositório com Submódulos

Para clonar este repositório principal junto com todos os submódulos, execute o seguinte comando:

```bash
git clone --recurse-submodules https://github.com/rafael-fxs/BookNow-Microservices.git
```
Esse comando fará o clone do repositório principal e de todos os submódulos definidos.

Caso já tenha clonado o repositório principal sem os submódulos
Se você já clonou o repositório principal e deseja atualizar os submódulos, execute os seguintes comandos para inicializá-los

```bash
git submodule update --init --recursive
```

## Build dos Microserviços
Antes de executar o projeto no Docker, você precisa fazer o build de cada um dos microserviços.

No menu Maven (normalmente localizado na barra lateral direita), expanda o submódulo e clique em Lifecycle > package. Isso executará o clean e package, gerando o .jar para cada serviço.

Repita o passo para cada um dos submódulos que precisa ser empacotado.

## Configuração e Execução com Docker
Este projeto está configurado para ser executado com Docker Compose. Certifique-se de ter o Docker e o Docker Compose instalados na sua máquina antes de prosseguir.

Passo a Passo para Executar o Projeto
1. Build dos Containers:
   
No diretório principal do projeto, execute o seguinte comando para construir e iniciar todos os contêineres:

```bash
docker-compose up --build
```

3. Acessar os Serviços:

Após a inicialização, os serviços estarão disponíveis nas seguintes portas locais:

Eureka Server: http://localhost:8761
API Gateway: http://localhost:8080
Outros serviços estarão disponíveis através do Gateway.

## Comandos Úteis
1. Atualizar Submódulos
   
Para atualizar todos os submódulos para as versões mais recentes, use:

```bash
git submodule update --remote
```

2. Parar os Contêineres
   
Para parar e remover os contêineres criados, execute:


```bash
docker-compose down
```
