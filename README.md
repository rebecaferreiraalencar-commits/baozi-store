# Baozi Store - API REST

API REST simples para controle de clientes, produtos e pedidos da Baozi Store (pao chines).

**Tecnologias:** Java 17, Spring Boot 3, Spring Data JPA, MySQL, Postman

## Como rodar
1. Tenha o **MySQL** rodando em `localhost:3306`.
2. Em `src/main/resources/application.properties`, adicione a linha `spring.datasource.password=SUA_SENHA` com a senha do seu MySQL, ou defina a variavel de ambiente `SPRING_DATASOURCE_PASSWORD`. O banco `baozi_store` e criado sozinho.
3. Execute: `mvn spring-boot:run` (ou rode a classe `BaoziStoreApplication` na IDE).
4. A API sobe em `http://localhost:8080`.

## Endpoints
| Metodo | Rota | Descricao |
|--------|------|-----------|
| POST | /clientes, /produtos, /pedidos | Criar |
| GET | /clientes, /produtos, /pedidos | Listar todos |
| GET | /clientes/{id}, /produtos/{id}, /pedidos/{id} | Consultar por ID |
| PUT | /clientes/{id}, /produtos/{id}, /pedidos/{id} | Atualizar (opcional) |
| DELETE | /clientes/{id}, /produtos/{id}, /pedidos/{id} | Apagar |

## Exemplos de JSON
**Cliente** (POST /clientes)
```json
{ "nome": "Rebeca5498481", "clienteDesde": "2026-10-05" }
```
**Produto** (POST /produtos)
```json
{ "nome": "Baozi de Carne", "preco": 8.50, "estoque": true }
```
**Pedido** (POST /pedidos)
```json
{ "clienteId": 1, "produtoId": 1, "quantidade": 3 }
```
