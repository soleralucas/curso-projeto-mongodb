
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/devsuperior/sds1-wmazoni/blob/master/LICENSE) 

# Sobre o projeto

API desenvolvida utilizando Java com Spring Boot, JPA e Hibernate durante a realização de um curso de programação Java. O projeto consiste em uma API com banco de dados H2, contendo entidades como Produto, Item do Pedido, Pedido e Usuário, além de diferentes tipos de relacionamentos entre elas, adaptados para o paradigma de orientação a objetos.

A aplicação segue o padrão de arquitetura MVC, contendo as camadas Model, Controller, Service e Repository para cada entidade do sistema. Além disso, o Postman foi utilizado para realizar os testes das requisições da API.

## Modelo conceitual
![Modelo Conceitual](https://github.com/soleralucas/assets/blob/main/workshop-springboot4-jpa/Captura%20de%20tela%202026-05-28%20183836.png)
![Modelo Conceitual](https://github.com/soleralucas/assets/blob/main/workshop-springboot4-jpa/Captura%20de%20tela%202026-05-28%20182005.png)

# Tecnologias utilizadas
## Back end
- Java
- Spring Boot
- JPA / Hibernate
- Maven

## Testes de API
- Postman

## Implantação em produção
- Banco de dados: H2

# Como executar o projeto

## Pré-requisitos

- Java 25
- Maven
- Spring Tools Suite (STS), Eclipse ou IntelliJ

O projeto utiliza o banco de dados H2 em memória, não sendo necessária a instalação de um banco de dados externo.

## Clonar o repositório

```bash
git clone git@github.com:soleralucas/workshop-springboot4-jpa.git

cd workshop-springboot4-jpa
```

## Executar a aplicação

Importe o projeto na IDE como um projeto Maven.

Em seguida, localize a classe principal da aplicação e execute:

```text
Run As → Spring Boot App
```

A aplicação será iniciada localmente na porta:

```text
http://localhost:8080
```

Após a inicialização, o servidor permanecerá em execução aguardando requisições da API.

## Console H2

O console do banco de dados pode ser acessado em:

```text
http://localhost:8080/h2-console
```

Utilize as seguintes credenciais:

```text
JDBC URL: jdbc:h2:mem:testdb
Usuário: sa
Senha:
```

Por meio do console H2 é possível visualizar as tabelas e acompanhar as alterações realizadas pela aplicação.

## Testes da API

As requisições da API podem ser testadas utilizando o Postman, permitindo validar os endpoints e verificar o funcionamento da aplicação.

Além disso, as alterações realizadas podem ser acompanhadas pelo console H2 através do navegador.

### Exemplo de requisição

Endpoint:

```http
GET /users
```

Resposta obtida através do Postman:

![Exemplo de Requisição](https://github.com/soleralucas/assets/blob/main/workshop-springboot4-jpa/Captura%20de%20tela%202026-05-29%20211547.png)

# Autor

Lucas Pereira Solera

https://www.linkedin.com/in/lucas-pereira-solera/
