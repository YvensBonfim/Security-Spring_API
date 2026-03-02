# 🔐 Security Spring API

Esta é uma API de autenticação e autorização desenvolvida com **Java 17** e **Spring Boot 3**, focada em proteger endpoints usando **Spring Security** e **JWT**.
O projeto também utiliza **Flyway** para versionamento do banco de dados **PostgreSQL**, garantindo controle e rastreabilidade das alterações no schema.

---

## 🚀 Tecnologias Utilizadas

O projeto foi construído utilizando Java 17 (definido no *pom.xml*) e Spring Boot 3.1.1 como framework principal.
A segurança é implementada com Spring Security e autenticação via JWT (java-jwt 4.4.0), com controle de perfis **USER** e **ADMIN**.
O banco de dados utilizado é o PostgreSQL, com migrações automatizadas via Flyway e apoio do Lombok para reduzir código boilerplate.

---

## 🛠️ Passo a passo para configuração

Para executar o projeto, é necessário ter o **JDK 17 ou superior**, **PostgreSQL em execução** (local ou via Docker) e **Git** instalados.

---

### 📥 Clonar o repositório

```bash
git clone https://github.com/YvensBonfim/Security-Spring-API.git
cd Security-Spring-API
```

---

### 🗄️ Configurar o banco de dados

Crie um banco no PostgreSQL com o nome **auth_api** (ou outro de sua preferência).
Em seguida, edite o arquivo:

```
src/main/resources/application.properties
```

E ajuste as credenciais:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/nome_do_seu_banco
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha

# Configuração para o Flyway rodar as migrations automaticamente
spring.flyway.enabled=true
```

---

### ▶️ Compilar e executar

O projeto utiliza **Maven Wrapper**, portanto não é necessário ter o Maven instalado globalmente.

No Linux ou Mac:

```bash
./mvnw clean install
./mvnw spring-boot:run
```

No Windows:

```bash
mvnw.cmd clean install
mvnw.cmd spring-boot:run
```

---

## 🔐 Endpoints da API

| Método | Endpoint       | Acesso      | Descrição                                 |
| ------ | -------------- | ----------- | ----------------------------------------- |
| POST   | /auth/login    | Público     | Autentica o usuário e retorna o token JWT |
| POST   | /auth/register | Público     | Cria um novo usuário                      |
| GET    | /product       | Autenticado | Lista todos os produtos                   |
| POST   | /product       | ADMIN       | Cadastra um novo produto                  |

---

## 📂 Estrutura de arquivos importantes

O arquivo **pom.xml** é responsável pelo gerenciamento das dependências do projeto.
O **.gitignore** já está configurado para ignorar pastas de IDEs e a pasta *target*.
Os scripts de migração do banco devem ser criados no diretório:

```
src/main/resources/db/migration
```

---

## 🤝 Contribuição

Para contribuir com o projeto, faça um fork do repositório, crie uma nova branch para sua funcionalidade e realize seus commits normalmente.
Após subir a branch, abra um Pull Request para que sua contribuição possa ser avaliada e integrada ao projeto.

```bash
git checkout -b feature/NovaFeature
git commit -m "Add: Nova Feature"
git push origin feature/NovaFeature
```





