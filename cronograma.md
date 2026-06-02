# 📅 Cronograma — API de Controle Financeiro Pessoal

> Roteiro de 4 semanas · ~1–2 horas por dia · do zero ao GitHub

---

## 🗓️ Semana 1 — Fundação do Projeto
**Foco:** Criar e entender a estrutura do projeto Spring Boot

| Dia | O que fazer | Etapa |
|---|---|---|
| **Seg** | Acessar [start.spring.io](https://start.spring.io), configurar e baixar o projeto (Maven, Java, H2, Web, JPA, Lombok) | Etapa 1 |
| **Ter** | Abrir no IntelliJ, entender a estrutura gerada, rodar pela primeira vez (`mvn spring-boot:run`) | Etapa 1 |
| **Qua** | Criar os 4 pacotes: `controller`, `model`, `repository`, `service` | Etapa 2 |
| **Qui** | Criar a entidade `Transaction` com todos os campos (`id`, `descricao`, `valor`, `tipo`, `data`) e anotações JPA | Etapa 3 |
| **Sex** | Criar o enum `TipoTransacao` com os valores `RECEITA` e `DESPESA` | Etapa 4 |
| **Sáb** | Revisão: consegue explicar o que cada arquivo faz? Anote dúvidas em `anotacoes/semana-01.md` | — |

**✅ Entregável da semana:** Projeto rodando no IntelliJ sem erros, com pacotes e entidade criados.

---

## 🗓️ Semana 2 — Lógica e Persistência
**Foco:** Repository, Service e conexão com banco H2

| Dia | O que fazer | Etapa |
|---|---|---|
| **Seg** | Criar `TransactionRepository` extendendo `JpaRepository<Transaction, Long>` | Etapa 5 |
| **Ter** | Estudar o que é JPA, o que `JpaRepository` oferece de graça (save, findAll, findById, delete) | Etapa 5 |
| **Qua** | Criar `TransactionService` com método `criarTransacao()` e `listarTransacoes()` | Etapa 6 |
| **Qui** | Adicionar métodos `buscarPorId()`, `deletar()` e `atualizar()` no Service | Etapa 6 |
| **Sex** | Configurar H2 no `application.properties`, acessar o console em `http://localhost:8080/h2-console` | Etapa 8 |
| **Sáb** | Explorar o console H2: ver as tabelas criadas automaticamente pelo JPA. Anotar observações. | — |

**✅ Entregável da semana:** Service completo com 5 métodos, banco H2 visível no browser.

---

## 🗓️ Semana 3 — Expondo a API (Controller + Postman)
**Foco:** Criar os endpoints REST e testá-los

| Dia | O que fazer | Etapa |
|---|---|---|
| **Seg** | Criar `TransactionController` com rota `GET /transacoes` (listar todas) | Etapa 7 |
| **Ter** | Adicionar rota `POST /transacoes` (criar nova transação) | Etapa 7 |
| **Qua** | Adicionar rotas `PUT /transacoes/{id}` e `DELETE /transacoes/{id}` | Etapa 7 |
| **Qui** | Instalar e configurar Postman. Testar `GET`, `POST`, `PUT` e `DELETE` | Etapa 9 |
| **Sex** | Criar o endpoint especial `GET /saldo` — somar receitas e subtrair despesas | Etapa 10 |
| **Sáb** | Testar `/saldo` no Postman. Criar pelo menos 5 transações de teste. Tirar prints. | — |

**✅ Entregável da semana:** API com 5 endpoints funcionando e testados no Postman com prints.

---

## 🗓️ Semana 4 — Polimento e GitHub
**Foco:** Melhorar o código e publicar profissionalmente

| Dia | O que fazer | Etapa |
|---|---|---|
| **Seg** | Adicionar DTOs para separar a camada de entrada da entidade do banco | Etapa 11 |
| **Ter** | Adicionar tratamento de erros (ex: transação não encontrada → retornar 404) | Etapa 11 |
| **Qua** | Adicionar validações básicas (ex: valor não pode ser negativo) e mensagens amigáveis | Etapa 11 |
| **Qui** | Criar o `README.md` do GitHub: descrição, stack, endpoints documentados, prints do Postman | Etapa 12 |
| **Sex** | Subir o projeto no GitHub. Revisar o README. Compartilhar o link! | Etapa 12 |
| **Sáb** | Retrospectiva: preencher `anotacoes/semana-04.md` com o que aprendeu e próximos passos | — |

**✅ Entregável da semana:** Projeto publicado no GitHub com README profissional. 🎉

---

## 📊 Visão Geral das 4 Semanas

```
Semana 1: [Projeto] → [Estrutura] → [Entidade] → [Enum]
Semana 2: [Repository] → [Service] → [H2 Console]
Semana 3: [Controller] → [Postman] → [/saldo]
Semana 4: [DTOs] → [Erros] → [Validação] → [GitHub]
```

---

> 💡 **Dica:** Se um dia você travar, não pule — anote a dúvida e pesquise antes de avançar. Compreensão > velocidade.
