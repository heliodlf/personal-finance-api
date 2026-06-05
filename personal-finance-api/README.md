# Personal Finance API

API REST para controle de finanças pessoais, desenvolvida com Java e Spring Boot. Permite registrar receitas e despesas, consultar o saldo e gerenciar transações financeiras.

## Tecnologias

- Java 17
- Spring Boot 4
- Spring Data JPA
- H2 Database (in-memory)
- Maven
- Lombok

## Como rodar localmente

**Pré-requisitos:** Java 17+ e Maven instalados.

```bash
# Clonar o repositório
git clone https://github.com/HelioDLima/personal-finance-api.git
cd personal-finance-api

# Rodar o projeto
./mvnw spring-boot:run
```

A API estará disponível em `http://localhost:8080`.

O console do banco H2 pode ser acessado em `http://localhost:8080/h2-console` com:
- **JDBC URL:** `jdbc:h2:mem:financedb`
- **User:** `sa`
- **Password:** _(em branco)_

## Endpoints

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/` | Verifica se a API está no ar |
| GET | `/transacoes` | Lista todas as transações |
| GET | `/transacoes/{id}` | Busca uma transação por ID |
| POST | `/transacoes` | Cria uma nova transação |
| PUT | `/transacoes/{id}` | Atualiza uma transação |
| DELETE | `/transacoes/{id}` | Remove uma transação |
| GET | `/saldo` | Retorna o saldo atual (receitas − despesas) |

## Exemplo de requisição

**POST** `/transacoes`

```json
{
  "description": "Salário",
  "amount": 3500.00,
  "type": "RECEITA",
  "category": "Trabalho",
  "date": "2026-06-01"
}
```

**Valores aceitos para `type`:** `RECEITA` ou `DESPESA`

## Estrutura do projeto

```
src/main/java/com/heliodlf/personal_finance_api/
├── controller/     # Endpoints REST
├── model/          # Entidades JPA e enums
├── repository/     # Acesso ao banco de dados
└── service/        # Regras de negócio
```

## Status do projeto

Em desenvolvimento — funcionalidades planejadas:

- [x] Estrutura base do projeto
- [x] Entidade `Transaction` com JPA
- [ ] CRUD completo de transações
- [ ] Endpoint `/saldo`
- [ ] DTOs e validações
- [ ] Tratamento de erros (respostas 404/400)

## Autor

**Helio Lima** — [github.com/HelioDLima](https://github.com/HelioDLima)
