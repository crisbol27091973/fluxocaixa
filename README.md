# API - Fluxo de Caixa
Um comerciante precisa controlar o seu fluxo de caixa diário com os lançamentos(débitos e créditos), também precisa de um relatório que disponibilize o saldo diário consolidado.

# Arquitetura 
![FluxoCaixa drawio](https://github.com/crisbol27091973/fluxocaixa/assets/48601776/3e3367df-e07c-4af5-8815-036d9f94cef6)

# Padrões de microserviço usados

Separação em camadas (Controller, Service e Repository)

Injeção de dependências com Spring

Uso de DTOs para transferência de dados entre a API e o banco de dados

# Padrões de projetos utilizados

Strategy: utilizado para implementar diferentes formas de cálculo do saldo diário.

Repository: utilizado para abstrair a camada de acesso ao banco de dados.

DTO: utilizado para transferência de dados entre as camadas.

# Tecnologias e Bibliotecas utilizadas no Projeto

Java 17

Spring Boot 3

Spring Data JPA

Spring Security

Spring Boot Actuator

JWT

H2 Database

Swagger 3

Lombok

JUnit 5

Mockito

ModelMapper

# Endpoints do projeto

- `POST /login`: endpoint para realizar a autenticação de um usuário e gerar um token JWT.
- `POST /lancamentos`: endpoint para adicionar um novo lançamento.
- `GET /lancamentos/{id}`: endpoint para buscar um lançamento por id.
- `GET /lancamentos`: endpoint para listar todos os lançamentos.
- `GET /lancamentos?data={data}`: endpoint para listar todos os lançamentos de uma determinada data.
- `GET /saldo-consolidado/{data}`: endpoint para calcular o saldo diário de uma determinada data.

# Como executar o projeto

Para executar o projeto, deve se ter instalado o Java 17 e o Maven.

# Como utilizar a API

É necessário ter o Docker e o Docker Compose instalados para utilizar a API.

# Como fazer um clone do repositório:
```
git clone https://github.com/crisbol27091973/fluxocaixa.git
```

# Comom entrar na pasta do projeto:
```
cd controle-fluxo-caixa
```

# Como rodar o comando que segue abaixo para compilar e empacotar o projeto:

```
mvn clean package
```

# Como executar o docker-compose que segue abaixo:
```
docker-compose up --build
```
A API estará disponível em http://localhost:8080.

# Como autenticar o token

Para usar as funcionalidades da API, é necessário realizar a autenticação e criar um token JWT.

Endpoint de autenticação: POST /login

Body:
{

    "login": "Cristiano",
    "password": "1234"
    
}

A resposta será um token JWT, que deve ser incluído no header das requisições que exigem autenticação, no formato "Bearer {token}".

# Como realizar os testes unitários

Segue abaixo o comandp para executar os testes unitários:

```
mvn test
```


