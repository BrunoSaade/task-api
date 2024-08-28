# API de Controle de Tarefas

Esta é uma API REST básica para controle de tarefas utilizando Node.js, Express e MongoDB. A API permite criar, listar e excluir tarefas.
Foi desenvolvida para a atividade avaliativa da disciplina de Desenvolvimento Back-End do curso de Engenharia de Software da UTFPR - Universidade Tecnológica Federal do Paraná.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução JavaScript
- **Express**: Framework para criação de APIs em Node.js
- **Mongoose**: ODM para MongoDB
- **Docker**: Para containerização da aplicação e do banco de dados

## Estrutura do Projeto

```
task-api/
├── dockerfile
├── docker-compose.yml
├── package.json
├── server.js
├── models/
│   └── task.js
├── routes/
│   └── tasks.js
└── config/
    └── db.js
```

## Pré-requisitos

- Docker e Docker Compose instalados na sua máquina

## Como Rodar a Aplicação

1. **Clone o repositório:**

   ```bash
   git clone <URL_DO_REPOSITÓRIO>
   cd task-api
   ```

2. **Construa e inicie os contêineres Docker:**

   ```bash
   docker-compose up --build
   ```

   Isso iniciará dois contêineres: um para o MongoDB e outro para a aplicação Node.js.

3. **Acesse a API:**

   A aplicação estará disponível em `http://localhost:3000`.

## Rotas da API

### 1. Criar uma Nova Tarefa

- **Método:** `POST`
- **Endpoint:** `/tasks`
- **Corpo da Requisição (JSON):**

  ```json
  {
    "name": "Nome da Tarefa",
    "description": "Descrição da Tarefa"
  }
  ```

- **Resposta:**

  ```json
  {
    "_id": "id_da_tarefa",
    "name": "Nome da Tarefa",
    "description": "Descrição da Tarefa",
    "__v": 0
  }
  ```

### 2. Listar Todas as Tarefas

- **Método:** `GET`
- **Endpoint:** `/tasks`

- **Resposta:**

  ```json
  [
    {
      "_id": "id_da_tarefa",
      "name": "Nome da Tarefa",
      "description": "Descrição da Tarefa",
      "__v": 0
    },
    ...
  ]
  ```

### 3. Excluir uma Tarefa

- **Método:** `DELETE`
- **Endpoint:** `/tasks/:id`
- **Parâmetros de URL:**
  - `id` - ID da tarefa a ser excluída

- **Resposta:**

  ```json
  {
    "message": "Task deleted"
  }
  ```
