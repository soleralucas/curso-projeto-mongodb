
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/devsuperior/sds1-wmazoni/blob/master/LICENSE) 

# Sobre o projeto

API desenvolvida utilizando Java com Spring Boot e MongoDB durante a realização de um curso de programação Java. O projeto consiste em uma API baseada em uma rede social simplificada, contendo as entidades User, Post e Comment, além dos relacionamentos entre elas, permitindo que usuários realizem publicações e interajam por meio de comentários.

A aplicação segue o padrão de arquitetura MVC, contendo as camadas Model, Controller, Service e Repository para cada entidade do sistema. Além dos relacionamentos entre as entidades, o MongoDB permitiu utilizar estruturas aninhadas para organizar as informações retornadas pelas requisições, possibilitando uma representação dos dados mais alinhada ao paradigma orientado a objetos e facilitando a visualização das relações entre os documentos.

Também foram utilizados DTOs (Data Transfer Objects) para personalizar os dados expostos pela API, adaptando a estrutura das respostas conforme a necessidade de cada endpoint. Além disso, foram implementados tratamentos personalizados de exceções e respostas de erro padronizadas, proporcionando mensagens mais claras e consistentes para os clientes da aplicação.

Por fim, o Postman foi utilizado para realizar os testes e validações dos endpoints da API.



## Modelo conceitual
![Modelo Conceitual](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-02%20184401.png)
![Modelo Conceitual](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-02%20185736.png)

# Tecnologias utilizadas

## Back end

* Java 26
* Spring Boot
* Spring Data MongoDB
* Maven

## Banco de dados

* MongoDB

## Testes de API

* Postman

# Como executar o projeto

## Pré-requisitos

* Java 26
* Maven
* MongoDB
* MongoDB Compass
* Spring Tools Suite (STS), Eclipse ou IntelliJ

## Clonar o repositório

```bash
git clone git@github.com:soleralucas/curso-projeto-mongodb.git

cd curso-projeto-mongodb
```

## Importando o projeto

### STS / Eclipse

1. Abra a IDE.
2. Clique em:

```text
File → Import
```

3. Expanda:

```text
Maven
```

4. Selecione:

```text
Existing Maven Projects
```

5. Clique em:

```text
Next
```

6. Em:

```text
Root Directory
```

clique em:

```text
Browse
```

7. Selecione a pasta do projeto clonado.
8. Clique em:

```text
Finish
```

## Configuração do MongoDB

Instale o MongoDB e o MongoDB Compass.

Abra o MongoDB Compass e crie uma conexão utilizando a configuração padrão:

```text
Host: localhost
Port: 27017
```

## Configuração do application.properties

Verifique o arquivo:

```text
src/main/resources/application.properties
```

O projeto está configurado para utilizar:

```properties
spring.application.name=workshopmongo
spring.mongodb.uri=mongodb://localhost:27017/workshop_mongo
```

Caso esteja utilizando outra porta ou outro servidor MongoDB, ajuste a URI conforme necessário.

Ao iniciar a aplicação, o banco de dados `workshop_mongo` será criado automaticamente.

## Executando a aplicação

Localize a classe principal da aplicação e execute:

```text
Run As → Spring Boot App
```

A aplicação será iniciada localmente na porta:

```text
http://localhost:8080
```

Após a inicialização, o servidor permanecerá em execução aguardando requisições da API.

# Testes da API

As requisições da API podem ser testadas utilizando o Postman, permitindo validar os endpoints e verificar o funcionamento da aplicação.

Além disso, os dados armazenados e as alterações realizadas podem ser acompanhados através do MongoDB Compass.

### Endpoint

```http
GET /users
```

Retorna todos os usuários cadastrados na aplicação.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20170546.png)

---

### Endpoint

```http
GET /users/{id}
```

Retorna um usuário específico com base no identificador informado.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20170612.png)

---

### Endpoint

```http
GET /users/{id}/posts
```

Retorna todas as publicações de um usuário específico, incluindo o autor de cada publicação e seus respectivos comentários aninhados.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20170701.png)

---

### Endpoint

```http
POST /users
```

Cria um novo usuário.

### Corpo da requisição enviado através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20171010.png)

> **Observação:** O identificador (id) é gerado automaticamente pela aplicação. Após a criação do recurso, sua localização pode ser obtida através do cabeçalho `Location` da resposta HTTP (Status 201 - Created).

---

### Endpoint

```http
PUT /users/{id}
```

Atualiza as informações de um usuário existente.

### Corpo da requisição enviado através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20171602.png)

---

### Endpoint

```http
GET /posts/{id}
```

Retorna uma publicação específica, incluindo seu autor e os comentários associados.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20172449.png)

---

### Endpoint

```http
GET /posts/titlesearch?text={texto}
```

Realiza uma busca de publicações com base no texto informado no título.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20172927.png)

> **Observação:** Esta consulta pode ser implementada utilizando Query Methods ou consultas customizadas com `@Query`.

---

### Endpoint

```http
GET /posts/fullsearch?text={texto}&minDate={dataInicial}&maxDate={dataFinal}
```

Realiza uma busca avançada de publicações utilizando um texto de pesquisa e um intervalo de datas. A consulta retorna posts cujo título ou comentários contenham o texto informado, respeitando o período especificado.

### Resposta obtida através do Postman

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/curso-projeto-mongodb/Captura%20de%20tela%202026-06-03%20173525.png)

> **Observação:** Esta consulta foi implementada utilizando consultas customizadas com `@Query`.


# Autor

Lucas Pereira Solera

https://www.linkedin.com/in/lucas-pereira-solera/
