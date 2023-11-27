# Sumário

1. [Projeto Docker com Nginx, PHP e MySQL](#projeto)
2. Pré-requisitos
3. Como usar
4. Iniciando o composer dentro do projeto PHP se necessário
5. Configuração
6. Persistência de dados
7. Conclusão
8. Comandos Básicos do Docker
9. Comandos Básicos do Docker Compose
10. Comandos Básicos do Docker
11. Comandos Básicos do Docker Compose

# <a name="projeto" />Projeto Docker com Nginx, PHP e MySQL

Este projeto é um exemplo de como usar Docker para criar um ambiente de desenvolvimento com Nginx, PHP e MySQL.

## Pré-requisitos
- WSL (Opcional)
- Docker
- Docker Compose

## Como usar

1. Clone este repositório
2. Navegue até o diretório do projeto
3. Execute o comando `docker-compose up -d --build` para que o docker monte o container. Após a montagem
4. Execute o comando `docker-compose down` ira derrubar o container
5. Execute o comando `docker-compose up -d` para iniciar o container novamente

## Sertifique-se que o seu projeto esteja na pasta 'application'. Caso a pasta app não existe, crie a pasta.
  A listagem de pastas do projeto deve ficar:

    application/
    cocker-compose/
    docker/
    .gitignore
    docker-compose.yml
    Dockerfile
    readme.md
    
- Isso iniciará três contêineres Docker:
- `nginx`: Este contêiner executa o servidor Nginx, que está configurado para servir o aplicativo PHP.
- `php`: Este contêiner executa o interpretador PHP.
- `mysql`: Este contêiner executa o servidor MySQL.

7. Ececute o comando `docker-compose exec app composer install` para instalar as dependencias do projeto caso já tenha o arquivo composer.json na raiz do projeto

## Iniciando o composer dentro do projeto PHP se necessário
1. Para inicializar o composer dentro do seu projeto PHP, caso seja necessário execute o comando `docker-compose exec app composer init`, onde app faz referencia a pasta do projeto que sera executado.
2. Para gerar o dump do composer `docker-compose exec app composer dump-autoload -o`
3. Para instalar as dependencias do composer `docker-compose exec app composer install`

## Configuração

As configurações para Nginx, PHP e MySQL estão localizadas nos respectivos diretórios dentro do diretório `config`:

- `docker-compose/nginx`: Aqui você encontrará a configuração do servidor Nginx.
- `docker-compose/php`: Aqui você encontrará a configuração do PHP.
- `docker-compose/mysql`: Aqui você encontrará a configuração do MySQL.

## Persistência de dados

Os dados do MySQL são persistidos em um volume Docker chamado `mysql-data`.

## Conclusão

Este é apenas um exemplo básico de como você pode usar Docker, Nginx, PHP e MySQL juntos. Sinta-se à vontade para modificar e expandir este exemplo para se adequar às suas necessidades.

----------------------------------------------------------------------------

# Comandos Básicos do Docker

Aqui estão alguns comandos básicos do Docker que você pode achar úteis ao trabalhar com contêineres Docker.

- `docker run`: Este comando é usado para iniciar um novo contêiner Docker.
- `docker start`: Este comando inicia um contêiner que foi parado.
- `docker stop`: Este comando para um contêiner em execução.
- `docker build`: Este comando é usado para construir uma imagem Docker a partir de um Dockerfile.
- `docker pull`: Este comando é usado para puxar uma imagem Docker de um registro.
- `docker push`: Este comando é usado para enviar uma imagem Docker para um registro.
- `docker rm`: Este comando remove um contêiner Docker.
- `docker rmi`: Este comando remove uma imagem Docker.
- `docker ps`: Este comando lista todos os contêineres Docker em execução.
- `docker inspect`: Este comando retorna informações detalhadas sobre um contêiner ou imagem Docker.

---------------------------------------------------------------------------

# Comandos Básicos do Docker Compose

Aqui estão alguns comandos básicos do Docker Compose e suas funções:

- `docker-compose up`: Este comando é usado para iniciar todos os serviços definidos em seu arquivo `docker-compose.yml`. Se os serviços ainda não existirem, o Docker Compose os criará.
- `docker-compose down`: Este comando para e remove todos os serviços que estão sendo executados.
- `docker-compose build`: Este comando é usado para construir ou reconstruir serviços. Ele construirá imagens Docker para qualquer serviço que tenha uma opção de `build` em seu arquivo `docker-compose.yml`.
- `docker-compose pull`: Este comando é usado para puxar todas as imagens necessárias para os serviços definidos em seu arquivo `docker-compose.yml`.
- `docker-compose start`: Este comando inicia serviços que foram previamente criados, mas que foram parados.
- `docker-compose stop`: Este comando para serviços em execução sem removê-los.
- `docker-compose restart`: Este comando reinicia todos os serviços em execução.
- `docker-compose ps`: Este comando lista todos os serviços em execução.
