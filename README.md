# Microsserviços com Docker Compose

Este repositório contém a configuração de um ambiente baseado em microsserviços utilizando Docker Compose. Cada microsserviço está executando um servidor Nginx e conectado a um banco de dados separado.

## Estrutura do Projeto

O projeto é composto por:

- **microsservico1**: Servidor Nginx conectado ao banco de dados PostgreSQL `db1`.
- **microsservico2**: Servidor Nginx conectado ao banco de dados PostgreSQL `db2`.
- **microsservico3**: Servidor Nginx conectado ao banco de dados MySQL `db3`.
- **Adminer**: Interface web para gerenciar os bancos de dados.

Cada microsserviço e banco de dados estão isolados em redes diferentes para maior segurança e modularização.

## Requisitos

Antes de rodar o projeto, certifique-se de ter instalado:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Como Executar

1. Clone este repositório:
   ```sh
   git clone https://github.com/Kainak/microsservicos-docker.git
   cd microsservicos-docker
   ```
2. Inicie os contêineres:
   ```sh
   docker-compose up -d
   ```
3. Acesse os microsserviços nos navegadores:
   - Microsserviço 1: [http://localhost:8001](http://localhost:8001)
   - Microsserviço 2: [http://localhost:8002](http://localhost:8002)
   - Microsserviço 3: [http://localhost:8003](http://localhost:8003)
   - Adminer: [http://localhost:8080](http://localhost:8080) (para acessar os bancos de dados)

## Credenciais de Acesso ao Adminer

### PostgreSQL (`db1` e `db2`):

- **Servidor:** `db1` ou `db2`
- **Usuário:** `user`
- **Senha:** `pass`
- **Banco de Dados:** `db1` ou `db2`

### MySQL (`db3`):

- **Servidor:** `db3`
- **Usuário:** `user`
- **Senha:** `pass`
- **Banco de Dados:** `db3`

## Como Parar os Contêineres

Para parar e remover os contêineres e volumes, use:

```sh
docker-compose down -v
```

Se desejar remover os volumes também:

```sh
docker-compose down -v
```

## Estrutura do `docker-compose.yml`

- Cada microsserviço usa uma instância do Nginx para servir arquivos estáticos.
- Os bancos de dados estão isolados em redes diferentes e possuem volumes persistentes.
- O Adminer permite acessar e gerenciar os bancos de dados de forma visual.
