# Projeto de API de Gestão de Produtos

<img src=".github/1.png" alt="Projeto desenvolvido e testado utilizando o Insomnia para validar as APIs." width="200" height="300"/>

Este projeto tem como objetivo fornecer uma API RESTful simples para o gerenciamento de produtos. Com o uso do Spring Boot, a aplicação oferece funcionalidades essenciais para registrar, atualizar, listar e excluir produtos. Ela foi desenvolvida para ser uma solução prática e eficiente para sistemas que necessitam de gerenciamento de inventário ou qualquer outra aplicação que precise controlar um conjunto de produtos.

### Funcionalidades Operações CRUD:

- **Criar (POST):** Permite registrar um novo produto com dados validados.  
- **Ler (GET):** Permite obter a lista de todos os produtos ativos ou buscar um produto específico pelo ID.    

- **Atualizar (PUT):** Permite atualizar as informações de um produto existente.

- **Deletar (DELETE):** Marca um produto como inativo, sem realmente removê-lo do banco de dados.   

**Validação de Dados:** Utiliza o recurso de validação do Spring para garantir que os dados enviados nas requisições atendam a certos requisitos.

**Exceções Personalizadas:** Quando um produto não é encontrado, a aplicação lança uma exceção EntityNotFoundException, que é tratada para retornar uma resposta amigável para o usuário.

**Persistência de Dados:** Utiliza um repositório para realizar operações de banco de dados, sendo que o banco de dados simula a persistência de produtos (usando Spring Data JPA).

# 💻 Requisitos
- **Java** (versão 17 ou superior)
- **Maven** (gerenciamento de dependências e construção do projeto)
- **Banco de dados PostgreSQL** (configurado e em execução)

# ⬇️ Instalação do Projeto
## Primeiro você deve clonar o repositório

```bash
## Clone o repositório
https://github.com/LeoAlves02/product-crud-api

## Acesse-o
cd product-crud-api
```
Para instalar as dependências, execute o seguinte comando:

```bash
mvn install
```

## ⚙️ Configuração do Banco de Dados com Flyway

Se você clonou o repositório, o Flyway já está configurado e pronto para ser usado. Ele irá aplicar automaticamente os scripts de migração ao banco de dados na primeira vez que o projeto for iniciado.

### Passos para configurar o banco de dados:

1. **Criação do Banco de Dados**: Crie um banco de dados vazio no PostgreSQL. Você pode fazer isso via linha de comando ou utilizando uma ferramenta como pgAdmin.

2. **Configuração no `application.properties`**: O arquivo `src/main/resources/application.properties` já está configurado para o Flyway. Verifique ou altere as seguintes linhas para garantir que as credenciais de acesso ao banco estejam corretas:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/seu_banco_de_dados
   spring.datasource.username=seu_usuario
   spring.datasource.password=sua_senha
