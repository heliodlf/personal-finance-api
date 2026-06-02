# 🚀 Projeto: API de Controle Financeiro Pessoal

> Plano de estudos prático — do zero ao projeto no GitHub em 4 semanas.

---

## 🎯 Objetivo do Projeto

Construir uma **API REST** simples para controle financeiro pessoal, praticando na prática:

- APIs REST com Spring Boot
- Estrutura back-end profissional (controller / service / repository / model)
- Persistência com JPA e banco de dados H2
- Testes manuais com Postman
- Organização de projeto para o GitHub

> **Objetivo REAL:** Não estou construindo "um sistema financeiro completo". Estou praticando a estrutura de um back-end Java profissional — com organização, boas práticas e um resultado concreto para demonstrar.

---

## 🛠️ Stack Tecnológica

| Tecnologia | Papel |
|---|---|
| **Java** | Linguagem principal |
| **Spring Boot** | Framework web (REST) |
| **Maven** | Gerenciamento de dependências |
| **H2 Database** | Banco de dados em memória para desenvolvimento |
| **Postman** | Teste manual dos endpoints |
| **IntelliJ IDEA** | IDE recomendada |

---

## 📋 As 12 Etapas do Projeto

| # | Etapa | Descrição |
|---|---|---|
| 1 | **Criar projeto Spring Boot** | Via [start.spring.io](https://start.spring.io) — Maven, Java, H2, Web, JPA, Lombok |
| 2 | **Estrutura inicial** | Criar pacotes: `controller`, `model`, `repository`, `service` |
| 3 | **Entidade Transaction** | Campos: `id`, `descricao`, `valor`, `tipo`, `data` |
| 4 | **Enum TipoTransacao** | Valores: `RECEITA` e `DESPESA` |
| 5 | **Repository** | `TransactionRepository` extendendo `JpaRepository<Transaction, Long>` |
| 6 | **Service** | Métodos: `criarTransacao()`, `listarTransacoes()`, `buscarPorId()`, `deletar()`, `atualizar()` |
| 7 | **Controller (rotas REST)** | `GET`, `POST`, `PUT`, `DELETE` em `/transacoes` |
| 8 | **Configurar H2** | Console em `http://localhost:8080/h2-console` |
| 9 | **Testar no Postman** | Testar todos os verbos HTTP com JSON |
| 10 | **Endpoint `/saldo`** | Soma receitas, subtrai despesas, retorna saldo final ⭐ |
| 11 | **Melhorar organização** | DTOs, tratamento de erros, validações, mensagens amigáveis |
| 12 | **README do GitHub** | Descrição, tecnologias, endpoints, prints do Postman |

---

## 🗂️ Estrutura de Pacotes

```
src/main/java/com/helio/financeapi
├── controller/
├── model/
├── repository/
└── service/
```

---

## 🔌 Endpoints da API

| Método | Rota | Descrição |
|---|---|---|
| `GET` | `/transacoes` | Lista todas as transações |
| `POST` | `/transacoes` | Cria uma nova transação |
| `PUT` | `/transacoes/{id}` | Atualiza uma transação |
| `DELETE` | `/transacoes/{id}` | Remove uma transação |
| `GET` | `/saldo` | Retorna saldo atual (receitas − despesas) |

### Exemplo de JSON (POST):
```json
{
  "descricao": "Freelance",
  "valor": 500,
  "tipo": "RECEITA"
}
```

---

## 📁 Arquivos deste repositório

| Arquivo | Descrição |
|---|---|
| `README.md` | Este arquivo — visão geral do projeto |
| `cronograma.md` | Roteiro semanal detalhado (4 semanas) |
| `recursos.md` | Materiais de estudo por semana |
| `anotacoes/semana-XX.md` | Suas anotações de cada semana |

---

## ✅ Critério de Sucesso

Ao final das 4 semanas, você terá:
- [ ] API funcionando com todos os 5 endpoints
- [ ] Testes realizados no Postman
- [ ] Projeto publicado no GitHub com README profissional
- [ ] Entendimento sólido de Spring Boot, JPA e REST
