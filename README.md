
```markdown
# 📦 Projeto de Persistência de Dados com Spring Boot e MariaDB

Avaliação prática da disciplina de **Persistência de Dados**, com foco em mapeamento de entidades, uso de Spring Boot, JPA, MariaDB e Lombok.

---

## 🚀 Tecnologias usadas

- Java 17
- Spring Boot 3
- Spring Data JPA
- MariaDB (via XAMPP)
- Lombok
- Postman ou Bruno (para testes de endpoints)

---

## 📁 Estrutura das Entidades

O projeto contém duas entidades relacionadas:

- **Categoria** (`id`, `nome`, `descricao`)
- **Produto** (`id`, `nome`, `preco`, `descricao`, `categoria`)

Relacionamento:
- Um(a) **Categoria** possui vários **Produtos**.
- Cada **Produto** pertence a uma única **Categoria**.
- (Relacionamento @ManyToOne com @JoinColumn).

---

## ⚙️ Como rodar o projeto localmente

### ✅ Pré-requisitos

- Java 17 instalado
- XAMPP ou MariaDB instalado localmente
- IDE (Spring Tool Suite, Eclipse ou VS Code)
- Git instalado

```

### 2. Configure o banco MariaDB com XAMPP

- Inicie o **MySQL** no XAMPP.
- Acesse: [http://localhost/phpmyadmin](http://localhost/phpmyadmin)
- Crie o banco:

```sql
CREATE DATABASE kidbuu;
```

### 3. Configure o `application.properties`

Arquivo localizado em: `src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/seubanco
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
server.port=8081
```

### 4. Rode o projeto

Abra a classe `ProjetoApplication.java` e clique em "Run".

---

## 🔎 Testando os Endpoints (CRUD)

Use Postman ou Bruno para testar os endpoints:

### ➕ Criar Categoria
```
POST http://localhost:8080/categorias
Content-Type: application/json
```
```json
{
  "nome": "Eletrônicos",
  "descricao": "Produtos tecnológicos"
}
```

### ➕ Criar Produto
```
POST http://localhost:8080/produtos
Content-Type: application/json
```
```json
{
  "nome": "Celular",
  "preco": 1999.99,
  "descricao": "Smartphone 5G",
  "categoria": {
    "id": 1
  }
}
```

### 📋 Listar Categorias
```
GET http://localhost:8081/categorias
```

### 📋 Listar Produtos
```
GET http://localhost:8081/produtos
```

---

## 🧪 Testes e Print

- ✅ Os testes foram realizados com sucesso via Postman.
- ✅ Endpoints funcionam corretamente.
---

## 🧠 Explicação do projeto

O projeto foi estruturado em pacotes separados:

- `model`: entidades JPA com anotações e Lombok.
- `repository`: interfaces `JpaRepository`.
- `controller`: classes REST Controller com rotas de CRUD.
- `application.properties`: configuração da conexão com MariaDB.

O Lombok foi utilizado para reduzir código repetitivo, como getters, setters e construtores.

---

![image](https://github.com/user-attachments/assets/2a734c92-2e72-4bbd-9320-f5a44df80209)
![image](https://github.com/user-attachments/assets/d42d2281-6feb-429d-8aca-120acefac898)
![image](https://github.com/user-attachments/assets/570ba84b-b4cd-45c0-bd87-1cba1d872eaa)





Desenvolvido com 💻 por [Miguel]
```



