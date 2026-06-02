# 📚 Recursos de Estudo por Semana
> Materiais separados para cada fase do projeto

---

## 🗓️ Semana 1 — Fundação (Etapas 1–4)
**Spring Initializr, Estrutura, Entidade, Enum**

### Documentação oficial
- 🔗 [Spring Initializr](https://start.spring.io) — gerar o projeto
- 🔗 [Spring Boot — Getting Started](https://spring.io/guides/gs/spring-boot/) — guia oficial
- 🔗 [Spring Boot Reference Docs](https://docs.spring.io/spring-boot/docs/current/reference/html/)

### Conceitos para estudar
- **O que é Spring Boot** e por que ele facilita o Spring clássico
- **Maven** — o que é `pom.xml`, como adicionar dependências
- **Anotações JPA básicas** — `@Entity`, `@Id`, `@GeneratedValue`, `@Column`
- **Enums em Java** e como usar com JPA (`@Enumerated`)
- **Lombok** — `@Data`, `@Builder`, `@NoArgsConstructor`, `@AllArgsConstructor`

### Vídeos sugeridos (buscar no YouTube)
- `"Spring Boot do zero em português"`
- `"JPA Entity Java explicado"`
- `"O que é Maven para iniciantes"`

---

## 🗓️ Semana 2 — Persistência (Etapas 5–6 e 8)
**Repository, Service, H2**

### Documentação oficial
- 🔗 [Spring Data JPA](https://spring.io/guides/gs/accessing-data-jpa/) — guia oficial
- 🔗 [H2 Database Console](https://www.h2database.com/html/quickstart.html)

### Conceitos para estudar
- **JpaRepository** — métodos prontos: `save()`, `findAll()`, `findById()`, `deleteById()`
- **@Service** e separação de responsabilidades
- **@Transactional** — quando e por que usar
- **application.properties** — configurações do Spring Boot
- **H2 Console** — banco em memória para desenvolvimento

### Configuração H2 (copie no `application.properties`):
```properties
spring.datasource.url=jdbc:h2:mem:financedb
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
spring.jpa.show-sql=true
```

### Vídeos sugeridos
- `"Spring Data JPA tutorial português"`
- `"H2 Database Spring Boot configuração"`

---

## 🗓️ Semana 3 — Controller + Postman (Etapas 7, 9, 10)
**Endpoints REST e testes**

### Documentação oficial
- 🔗 [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/) — guia oficial Spring
- 🔗 [Postman — Learning Center](https://learning.postman.com/docs/getting-started/introduction/)

### Conceitos para estudar
- **@RestController** e **@RequestMapping**
- **@GetMapping, @PostMapping, @PutMapping, @DeleteMapping**
- **@PathVariable** e **@RequestBody**
- **ResponseEntity** — retornar status HTTP correto (200, 201, 404...)
- **Verbos HTTP** — GET (buscar), POST (criar), PUT (atualizar), DELETE (remover)

### Anotações do Controller — referência rápida:
```java
@RestController
@RequestMapping("/transacoes")
public class TransactionController {

    @GetMapping          // GET /transacoes
    @PostMapping         // POST /transacoes
    @PutMapping("/{id}") // PUT /transacoes/{id}
    @DeleteMapping("/{id}") // DELETE /transacoes/{id}
}
```

### Vídeos sugeridos
- `"Spring Boot REST API completa tutorial"`
- `"Postman como usar para testar API"`
- `"@PathVariable @RequestBody Spring Boot"`

---

## 🗓️ Semana 4 — Polimento e GitHub (Etapas 11–12)
**DTOs, Erros, Validações, GitHub**

### Documentação oficial
- 🔗 [Bean Validation com Spring Boot](https://spring.io/guides/gs/validating-form-input/)
- 🔗 [Exception Handling in Spring MVC](https://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc)
- 🔗 [GitHub Docs — Criar um repositório](https://docs.github.com/pt/repositories/creating-and-managing-repositories/creating-a-new-repository)

### Conceitos para estudar
- **DTO (Data Transfer Object)** — separar o que entra/sai da API do modelo do banco
- **@Valid e @NotNull, @NotBlank, @Positive** — validar dados de entrada
- **@ExceptionHandler / @ControllerAdvice** — tratar erros globalmente
- **ResponseEntity com status correto** — 404 quando não encontrado, 400 quando inválido
- **Git** — `git init`, `git add`, `git commit`, `git push`

### Checklist do README do GitHub:
```markdown
## ✅ Itens do README profissional
- [ ] Descrição do projeto
- [ ] Tecnologias usadas (badges)
- [ ] Como executar localmente
- [ ] Lista de endpoints com método e rota
- [ ] Exemplo de JSON para o POST
- [ ] Print do Postman testando os endpoints
- [ ] Autor e LinkedIn
```

### Vídeos sugeridos
- `"DTO Spring Boot o que é"`
- `"tratamento de exceções Spring Boot @ControllerAdvice"`
- `"como subir projeto Java no GitHub"`

---

## 🔧 Ferramentas Essenciais

| Ferramenta | Link | Para quê |
|---|---|---|
| **IntelliJ IDEA Community** | [jetbrains.com/idea](https://www.jetbrains.com/idea/download/) | IDE principal |
| **Postman** | [postman.com/downloads](https://www.postman.com/downloads/) | Testar a API |
| **Git** | [git-scm.com](https://git-scm.com/downloads) | Versionamento |
| **Java 17+** | [adoptium.net](https://adoptium.net/) | Linguagem |
| **Maven** | Vem com o IntelliJ | Build e dependências |

---

## 📖 Referências Rápidas

### Estrutura de pacotes esperada ao final:
```
src/main/java/com/helio/financeapi/
├── controller/
│   └── TransactionController.java
├── model/
│   ├── Transaction.java
│   └── TipoTransacao.java  (enum)
├── repository/
│   └── TransactionRepository.java
└── service/
    └── TransactionService.java
```

### Campos da entidade Transaction:
```java
Long id           // gerado automaticamente
String descricao  // ex: "Salário"
Double valor      // ex: 2500.00
TipoTransacao tipo // RECEITA ou DESPESA
LocalDate data    // ex: 2026-06-02
```
