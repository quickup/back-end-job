### Desafio Técnico: Implementação de API de Cadastros de Funcionários

Prezado Candidato,

Estamos entusiasmados por tê-lo no nosso processo seletivo para a vaga de Programador Backend Python. Como parte da avaliação técnica, solicitamos que você implemente uma API de cadastros de funcionários utilizando Python, SQLAlchemy e PostgreSQL. A seguir estão os detalhes e requisitos do desafio.

#### Objetivo:
Implementar uma API RESTful para gerenciar cadastros de funcionários com funcionalidades de listagem, criação e edição. Além disso, será necessário manipular e formatar informações para exibição na API de forma diferente das quais estão sendo salvas no banco de dados.

#### Requisitos:

##### Tecnologias:
- **Linguagem:** Python
- **ORM:** SQLAlchemy
- **Banco de Dados:** PostgreSQL
- **Framework:** Flask

##### Funcionalidades da API:
1. **Listar Funcionários**
2. **Criar Funcionário**
3. **Editar Funcionário**

##### Especificações da API:

###### Entidade Funcionário:
- `id` (Integer, Primary Key)
- `name` (String, até 100 caracteres)
- `birth_date` (Date)
- `address` (String, até 200 caracteres)
- `phone` (String, até 15 caracteres)
- `email` (String, até 100 caracteres)
- `job_title` (String, até 50 caracteres)
- `department` (String, até 50 caracteres)

###### Endpoints:
1. **Listar Funcionários**
   - **Endpoint:** `GET /employees`
   - **Descrição:** Retorna uma lista de todos os funcionários cadastrados.
   - **Resposta:** 
     ```json
     [
       {
         "id": 1,
         "name": "John Doe",
         "age": 30,
         "phone": "(11) 98765-4321",
         "email": "john.doe@example.com",
         "job_title": "Software Engineer",
         "department": "Engineering",
         "last_review_summary": "Review on 2023-01-15: Exceeded expectations, promoted to senior level."
       },
       ...
     ]
     ```
   - **Nota:** 
     - A idade deve ser calculada com base na `birth_date`.
     - O resumo da última avaliação deve ser construído a partir de um histórico de avaliações, contendo a data da última avaliação e uma breve descrição (assumindo que o histórico de avaliações está armazenado em outra tabela).

2. **Criar Funcionário**
   - **Endpoint:** `POST /employees`
   - **Descrição:** Cria um novo cadastro de funcionário.
   - **Requisição:** 
     ```json
     {
       "name": "Jane Smith",
       "birth_date": "1990-05-15",
       "address": "123 Flower Street",
       "phone": "(11) 91234-5678",
       "email": "jane.smith@example.com",
       "job_title": "Product Manager",
       "department": "Product"
     }
     ```
   - **Resposta:** 
     ```json
     {
       "id": 2,
       "name": "Jane Smith",
       "birth_date": "1990-05-15",
       "address": "123 Flower Street",
       "phone": "(11) 91234-5678",
       "email": "jane.smith@example.com",
       "job_title": "Product Manager",
       "department": "Product"
     }
     ```

3. **Editar Funcionário**
   - **Endpoint:** `PUT /employees/{id}`
   - **Descrição:** Edita as informações de um funcionário existente.
   - **Requisição:** 
     ```json
     {
       "name": "Jane Smith",
       "birth_date": "1990-05-15",
       "address": "456 Rose Street",
       "phone": "(11) 91234-5678",
       "email": "jane.smith@example.com",
       "job_title": "Product Manager",
       "department": "Product"
     }
     ```
   - **Resposta:** 
     ```json
     {
       "id": 2,
       "name": "Jane Smith",
       "birth_date": "1990-05-15",
       "address": "456 Rose Street",
       "phone": "(11) 91234-5678",
       "email": "jane.smith@example.com",
       "job_title": "Product Manager",
       "department": "Product"
     }
     ```

###### Tabela de Avaliações:
- **Entidade Avaliação:**
  - `id` (Integer, Primary Key)
  - `employee_id` (Integer, Foreign Key para `employees.id`)
  - `review_date` (Date)
  - `summary` (Text)

- **Exemplo de Registro:**
  ```json
  {
    "id": 1,
    "employee_id": 1,
    "review_date": "2023-01-15",
    "summary": "Exceeded expectations, promoted to senior level."
  }
  ```

##### Requisitos Adicionais:
- **Formatação de Dados:** Na listagem de funcionários, exibir a idade calculada a partir da data de nascimento.
- **Manipulação de Dados:** Na listagem de funcionários, incluir um resumo da última avaliação, composto pela data da última avaliação e uma breve descrição.
- **Organização do Projeto:** O projeto deve ser organizado de maneira clara, seguindo boas práticas de desenvolvimento e estrutura de diretórios.
- **Documentação:** Fornecer um README com instruções sobre como configurar e executar o projeto, bem como exemplos de uso da API.

#### Critérios de Avaliação:
- **Corretude e Funcionalidade:** A API deve atender a todos os requisitos funcionais descritos.
- **Qualidade do Código:** O código deve ser limpo, bem documentado e seguir boas práticas de desenvolvimento.
- **Estrutura do Projeto:** A organização do projeto deve ser clara e modular.
- **Tratamento de Erros:** A API deve lidar adequadamente com possíveis erros e exceções.
- **Performance:** A API deve ser eficiente no processamento das requisições.

#### Submissão:
- Envie o link para o repositório do GitHub com o código do projeto.
- Inclua instruções claras sobre como configurar e executar a aplicação.

Estamos ansiosos para ver sua solução e discutir os resultados na próxima etapa.
