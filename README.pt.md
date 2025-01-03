# Projeto de Autenticação em Java com Spring Boot

Este projeto implementa um sistema de autenticação básico utilizando Java e Spring Boot. O sistema permite o registro de usuários, login e acesso a informações do usuário através de uma API RESTful.

## Tecnologias Utilizadas

- Java 21
- Spring Boot
- IntelliJ IDEA
- Maven
- JPA (Hibernate)
- Banco de Dados H2 (para desenvolvimento)

## Estrutura do Projeto

```
/src
   /main
      /java
         /com
            /exemplo
               /autenticacao
                  - AuthController.java
                  - UserController.java
                  - UserService.java
                  - AuthService.java
                  - User.java
                  - UserRepository.java
                  - JwtUtil.java
      /resources
         - application.properties
```

## Rotas da API

### 1. Registro de Usuário

- **Método:** `POST`
- **Rota:** `/auth/register`
- **Descrição:** Registra um novo usuário no sistema.
- **Corpo da Requisição:**
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
- **Resposta de Sucesso (201):**
    ```json
    {
        "message": "Usuário registrado com sucesso."
    }
    ```

### 2. Login de Usuário

- **Método:** `POST`
- **Rota:** `/auth/login`
- **Descrição:** Realiza o login de um usuário e gera um token JWT.
- **Corpo da Requisição:**
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
- **Resposta de Sucesso (200):**
    ```json
    {
        "token": "string"
    }
    ```

### 3. Acesso às Informações do Usuário

- **Método:** `GET`
- **Rota:** `/user`
- **Descrição:** Retorna as informações do usuário autenticado.
- **Autenticação:** Este endpoint exige um token JWT no cabeçalho da requisição.
- **Cabeçalho da Requisição:**
    ```
    Authorization: Bearer <token>
    ```
- **Resposta de Sucesso (200):**
    ```json
    {
        "username": "string"
    }
    ```

## Executando o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd seu-repositorio
   ```

3. Execute o projeto através do IntelliJ IDEA.

## Configurações do Banco de Dados

Por padrão, o projeto utiliza o banco de dados H2 para desenvolvimento. As configurações podem ser encontradas no arquivo `application.properties`.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma `issue` ou `pull request`.

## Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para mais detalhes.
