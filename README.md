# Workout API - Desafio de Projeto DIO

## 📄 Descrição do Projeto

Este projeto é uma API para gestão de academias, desenvolvida como parte do desafio de projeto da [Digital Innovation One (DIO)](https://www.dio.me/). A API base, fornecida pela DIO, foi aprimorada com novas funcionalidades para atender aos requisitos específicos do desafio, focando em boas práticas de desenvolvimento de APIs REST com Python e FastAPI.

O objetivo principal foi aplicar e aprofundar os conhecimentos em desenvolvimento backend, manipulação de banco de dados com SQLAlchemy, e a implementação de funcionalidades avançadas em uma API.

## 🎯 Sobre o Desafio

O projeto original (`https://github.com/digitalinnovationone/workout_api`) foi o ponto de partida. As seguintes funcionalidades foram implementadas para completar o desafio:

  - **✅ Adição de Query Parameters:** Implementação de filtros no endpoint de consulta de atletas para permitir buscas por `nome` e `CPF`.
  - **✅ Customização de Resposta:** Otimização do endpoint `GET /atletas` para retornar uma lista simplificada, contendo apenas `nome`, `categoria` e `centro_treinamento` de cada atleta.
  - **✅ Tratamento de Exceções de Integridade:** Manipulação específica do erro `sqlalchemy.exc.IntegrityError` ao tentar cadastrar um atleta com um CPF já existente. A API agora retorna uma mensagem clara (`"Já existe um atleta cadastrado com o cpf: X"`) com o `status_code 303 See Other`.
  - **✅ Paginação:** Implementação de paginação nos endpoints de listagem utilizando a biblioteca `fastapi-pagination`, permitindo o controle dos resultados com `limit` e `offset`.

## 🚀 Tecnologias Utilizadas

  - **Python 3.10+**
  - **FastAPI:** Framework web para a construção da API.
  - **SQLAlchemy:** ORM para interação com o banco de dados.
  - **PostgreSQL:** Sistema de gerenciamento de banco de dados relacional.
  - **Alembic:** Ferramenta para controle de migrações do banco de dados.
  - **Pydantic:** Para validação e serialização de dados.
  - **fastapi-pagination:** Biblioteca para adicionar paginação de forma simples.
  - **Uvicorn:** Servidor ASGI para rodar a aplicação.

## 🕹️ Exemplos de Uso da API

### Listar atletas com paginação e campos customizados

`GET /atletas?limit=10&offset=0`

**Resposta esperada:**

```json
{
  "items": [
    {
      "nome": "Joao",
      "categoria": {
        "nome": "Scale"
      },
      "centro_treinamento": {
        "nome": "CT King"
      }
    },
    {
      "nome": "Maria",
      "categoria": {
        "nome": "RX"
      },
      "centro_treinamento": {
        "nome": "CT Bodybuilding"
      }
    }
  ],
  "total": 2,
  "page": 1,
  "size": 10
}
```

### Filtrar atleta por CPF

`GET /atletas?cpf=12345678900`

### Tentativa de criar um atleta com CPF duplicado

`POST /atletas`

**Payload:**

```json
{
  "nome": "Fulano de Tal",
  "cpf": "12345678900",  // CPF que já existe no banco
  "idade": 30,
  "peso": 85.5,
  "altura": 1.80,
  "sexo": "M",
  "categoria": { "nome": "Scale" },
  "centro_treinamento": { "nome": "CT King" }
}
```

**Resposta esperada:**

  - **Status Code:** `303 See Other`
  - **Body:**

<!-- end list -->

```json
{
  "detail": "Já existe um atleta cadastrado com o cpf: 12345678900"
}
```

## 👨‍💻 Autor

[](https://www.google.com/search?q=https://www.linkedin.com/in/emmanuelmonteiro/)
[](https://www.google.com/search?q=https://github.com/EmmanuelGBL)

## 🙏 Agradecimentos

Agradeço à [Digital Innovation One](https://www.dio.me/) pela oportunidade de aprendizado e pelo desafio proposto.


