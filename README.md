Perfeito! Aqui está um `README.md` bem feito, pronto para colocar no GitHub, com explicações claras, instruções de instalação, execução, testes e print do banco — tudo que sua avaliação pede:

---

### 📄 `README.md`

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

### 1. Clone o repositório

```bash
git clone https://github.com/seuusuario/nome-do-repositorio.git
cd nome-do-repositorio
```

### 2. Configure o banco MariaDB com XAMPP

- Inicie o **MySQL** no XAMPP.
- Acesse: [http://localhost/phpmyadmin](http://localhost/phpmyadmin)
- Crie o banco:

```sql
CREATE DATABASE seubanco;
```

### 3. Configure o `application.properties`

Arquivo localizado em: `src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/seubanco
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
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
GET http://localhost:8080/categorias
```

### 📋 Listar Produtos
```
GET http://localhost:8080/produtos
```

---

## 🧪 Testes e Print

- ✅ Os testes foram realizados com sucesso via Postman.
- ✅ Endpoints funcionam corretamente.
- ✅ As chaves estrangeiras estão persistidas.
- 🖼️ O print do banco no **HeidiSQL** será anexado no final do trabalho.

---

## 🧠 Explicação do projeto

O projeto foi estruturado em pacotes separados:

- `model`: entidades JPA com anotações e Lombok.
- `repository`: interfaces `JpaRepository`.
- `controller`: classes REST Controller com rotas de CRUD.
- `application.properties`: configuração da conexão com MariaDB.

O Lombok foi utilizado para reduzir código repetitivo, como getters, setters e construtores.

---

## 📤 Entrega

✔️ Projeto versionado no GitHub.  
✔️ Instruções de instalação e execução incluídas.  
✔️ README completo.

---

Desenvolvido com 💻 por [Seu Nome]
```

---

Esse README está prontinho pra colar no seu projeto no GitHub.

👉 Agora quer que eu empacote o projeto todo em `.zip` e te envie aqui?  
Ou prefere que eu te ensine a criar pelo Spring Initializr e ir montando por pastas?
