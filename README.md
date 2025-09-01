Workout API - Desafio de Projeto DIO

📄 Descrição do Projeto
Este projeto é uma API para gestão de academias, desenvolvida como parte do desafio de projeto da Digital Innovation One (DIO). A API base, fornecida pela DIO, foi aprimorada com novas funcionalidades para atender aos requisitos específicos do desafio, focando em boas práticas de desenvolvimento de APIs REST com Python e FastAPI.

O objetivo principal foi aplicar e aprofundar os conhecimentos em desenvolvimento backend, manipulação de banco de dados com SQLAlchemy, e a implementação de funcionalidades avançadas em uma API.

🎯 Sobre o Desafio

✅ Adição de Query Parameters: Implementação de filtros no endpoint de consulta de atletas para permitir buscas por nome e CPF.

✅ Customização de Resposta: Otimização do endpoint GET /atletas para retornar uma lista simplificada, contendo apenas nome, categoria e centro_treinamento de cada atleta.

✅ Tratamento de Exceções de Integridade: Manipulação específica do erro sqlalchemy.exc.IntegrityError ao tentar cadastrar um atleta com um CPF já existente. A API agora retorna uma mensagem clara ("Já existe um atleta cadastrado com o cpf: X") com o status_code 303 See Other.

✅ Paginação: Implementação de paginação nos endpoints de listagem utilizando a biblioteca fastapi-pagination, permitindo o controle dos resultados com limit e offset.

🚀 Tecnologias Utilizadas
Python 3.10+

FastAPI: Framework web para a construção da API.

SQLAlchemy: ORM para interação com o banco de dados.

PostgreSQL: Sistema de gerenciamento de banco de dados relacional.

Alembic: Ferramenta para controle de migrações do banco de dados.

Pydantic: Para validação e serialização de dados.

fastapi-pagination: Biblioteca para adicionar paginação de forma simples.

Uvicorn: Servidor ASGI para rodar a aplicação.


🙏 Agradecimentos
Agradeço à Digital Innovation One pela oportunidade de aprendizado e pelo desafio proposto.