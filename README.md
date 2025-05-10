# gs-fluir
gerenciador de docker da fluir


# Introdução

Este projeto foi desenvolvido para concentrar todos os microsserviços em um único repositório, facilitando o desenvolvimento e a execução dos serviços.

# Pré-requisitos

Para executar o projeto, é necessário ter instalado:

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

# Executando o projeto

## 1. Clonando o repositório

```bash
git clone git@ssh.dev.azure.com:v3/allcareti/Plataforma%20Solutions/ps-microservices
```

## 2. Acessando o diretório do projeto

```bash
cd ps-microservices
```

## 3. Inicializando o submódulo

Esse comando deve ser executado apenas na primeira vez que o repositório for clonado.

```bash
git submodule init
```

### 3.1 Atualizando o submódulo

Esse comando deve ser executado sempre que houver atualização no repositório do submódulo.

```bash
git submodule update --remote
```

## 4. Copiando o arquivo de variáveis de ambiente

Esse arquivo deve ser copiado apenas na primeira vez que o repositório for clonado.

```bash
cp .env.example .env
```

## 5. Inicializando o projeto

Esse comando deve ser executado sempre que o projeto for executado.

```bash
docker compose up --build -d
```

## 6. Executando os dumps do banco de dados

Esse comando deve ser executado apenas na primeira vez que o projeto for executado ou quando houver atualização no banco de dados.

```bash
docker compose exec -it postgres bash
```

```bash
psql -U admin -d all-care -f /dumps/ceps.sql
psql -U admin -d all-care -f /dumps/customers.sql
```

Observações: 
- O usuário e a senha do banco de dados estão definidos no arquivo .env
- O processo de execução do dump pode demorar alguns minutos

## 7. Acessando o projeto

Para acessar os projetos:
