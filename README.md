<h2 align="center">📝 To-Do List API</h2>
<p align="center">
  API RESTful para gerenciamento de tarefas, construída com Java e Spring Boot.
</p>

<p align="center">
  <img alt="Java" src="https://img.shields.io/badge/Java-21-2E3849?style=for-the-badge&logo=java&logoColor=white&color=2E3849&labelColor=2E3849" />
  <img alt="Spring Boot" src="https://img.shields.io/badge/Spring_Boot-3.3.13-2E3849?style=for-the-badge&logo=spring-boot&logoColor=white&color=2E3849&labelColor=2E3849" />
  <img alt="Maven" src="https://img.shields.io/badge/Maven-2E3849?style=for-the-badge&logo=apachemaven&logoColor=white&color=2E3849&labelColor=2E3849" />
</p>

## Descrição

Esta é uma API back-end para gerenciamento de tarefas (to-do list), que permite a autenticação de usuários e o controle de suas tarefas de forma segura.

Os usuários podem:
- Cadastrar-se e autenticar-se
- Criar, visualizar e atualizar tarefas
- Apenas acessar suas próprias tarefas (controle de acesso)


## Tecnologias utilizadas

- Java 21
- Spring Boot
- Spring Web, Spring Data JPA
- Maven
- Docker
- (Futuramente) Banco de dados relacional como PostgreSQL

## Como executar localmente

### Com Maven:
```bash
./mvnw spring-boot:run
```
A aplicação estará disponível em:
📍 http://localhost:8080

### Docker:
```bash
docker build -t todolist .
docker run -p 8080:8080 todolist
```
## Endpoints

| Método | Rota         | Descrição                 | Body (exemplo)                             | Requer Autenticação |
|--------|--------------|---------------------------|--------------------------------------------|----------------------|
| POST   | `/user`      | Cadastra novo usuário     | `{ "username": "julia", "password": "123" }` | False                 |
| GET    | `/task`      | Lista todas as tarefas    | –                                          | True                   |
| POST   | `/task`      | Cria nova tarefa          | `{ "title": "Estudar", "description": "..." }` | True               |
| PUT    | `/task/{id}` | Atualiza uma tarefa       | `{ "title": "...", "description": "..." }` | True                   |

## Estrutura do Código
```bash
src/
├── main/
│   ├── java/br/com/julia16bit/todolist/
│   │   ├── task/         # CRUD de tarefas
│   │   ├── user/         # CRUD de usuários e autenticação
│   │   ├── filter/       # Filtro de autenticação
│   │   ├── errors/       # Tratamento de exceções
│   │   ├── utils/        # Classes utilitárias
│   │   └── TodolistApplication.java
│   └── resources/
│       └── application.properties
```
