# Arquitetura do Projeto FeioDiesel

## Visão geral

O projeto FeioDiesel será desenvolvido utilizando uma arquitetura modular, com responsabilidades separadas entre as diferentes camadas da aplicação.

A organização tem como objetivo facilitar a manutenção, evolução e testes do sistema.

## Estrutura

```text
FeioDiesel
│
├── API
├── Application
├── Domain
└── Infrastructure
```

## Camadas

### API

Responsável pela comunicação externa da aplicação.

Principais responsabilidades:

* Receber requisições HTTP.
* Expor os endpoints da aplicação.
* Validar dados de entrada.
* Retornar respostas para o cliente.

### Application

Responsável pelos casos de uso e pela lógica de aplicação.

Principais responsabilidades:

* Orquestrar as operações do sistema.
* Trabalhar com DTOs.
* Coordenar serviços e casos de uso.
* Definir contratos utilizados pela aplicação.

### Domain

Representa o núcleo do sistema e suas regras de negócio.

Principais responsabilidades:

* Entidades.
* Regras de negócio.
* Objetos de domínio.
* Interfaces relacionadas ao domínio.

A camada de domínio deve permanecer independente das demais camadas.

### Infrastructure

Responsável pelas implementações externas necessárias para o funcionamento da aplicação.

Principais responsabilidades:

* Acesso ao banco de dados.
* Entity Framework Core.
* Repositórios.
* Migrations.
* Implementações de serviços externos.

## Fluxo da aplicação

```text
Cliente
   │
   ▼
  API
   │
   ▼
Application
   │
   ▼
 Domain
   ▲
   │
Infrastructure
   │
   ▼
Database
```

A comunicação entre as camadas será organizada de forma a manter o domínio independente de detalhes externos da aplicação.

## Objetivo da arquitetura

A arquitetura foi definida para permitir que o projeto seja desenvolvido de forma modular, facilitando a manutenção, os testes e a adição de novas funcionalidades ao longo do desenvolvimento.
