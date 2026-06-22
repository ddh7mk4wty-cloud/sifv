# 🧾 Sistema Inteligente de Faturação e Controle de Vendas

Backend profissional desenvolvido com **NestJS**, seguindo rigorosamente os princípios de **Clean Architecture** e **Domain-Driven Design (DDD)**. O sistema é ideal para **pequenos negócios e cibercafés**, oferecendo controle completo de usuários, clientes, produtos, vendas e faturação.

---

## 📌 Visão Geral

Este projeto foi concebido com foco em **escalabilidade**, **manutenibilidade** e **segurança**, separando claramente regras de negócio de detalhes técnicos. Ele pode ser facilmente estendido para novos domínios, integrações ou interfaces (web/mobile).

---

## 🚀 Principais Funcionalidades

### 🔐 Autenticação & Autorização (RBAC)

* Autenticação segura com **JWT**
* Controle de acesso baseado em perfis:

  * `ADMIN`
  * `VENDEDOR`

### 👤 Gestão de Usuários *(ADMIN)*

* CRUD completo de usuários
* Atribuição de perfis e permissões

### 👥 Gestão de Clientes

* Cadastro e atualização de clientes
* Histórico de compras

### 📦 Gestão de Produtos

* Controle de estoque
* Preços configuráveis
* Alertas de estoque mínimo

### 🛒 Vendas

* Fluxo completo de venda
* Atualização automática de estoque
* Operações realizadas em **transações atômicas**

### 🧾 Faturação

* Geração automática de faturas
* Numeração sequencial
* Faturas vinculadas às vendas

### 📊 Dashboard

* Total de vendas
* Receita gerada
* Produtos mais vendidos

---

## 🧱 Arquitetura do Projeto

O projeto segue **Clean Architecture**, promovendo baixo acoplamento e alta coesão:

```
src/
├── domain/          # Núcleo do domínio (entidades, enums, contratos, usecases)
├── application/     # Casos de uso e validações (DTOS)
├── infrastructure/  # Prisma, mappers, JWT, banco de dados
├── presentation/    # Controllers, guards, decorators
```

### 📂 Camadas

#### **Domain (Núcleo)**

* Entidades de negócio
* Regras de domínio
* Interfaces de repositórios
* Independente de frameworks

#### **Application**

* Casos de uso (Use Cases)
* Orquestração da lógica de negócio
* Schemas de validação com **Zod**

#### **Infrastructure**

* Implementação dos repositórios (Prisma)
* Configuração de banco de dados
* Autenticação JWT
* Mappers (Domain ↔ Persistence)

#### **Presentation**

* Controllers REST
* Guards e decorators
* Integração com Swagger e Scalar

---

## 🛠️ Tecnologias Utilizadas

* **Framework:** NestJS
* **Linguagem:** TypeScript
* **ORM:** Prisma
* **Banco de Dados:** PostgreSQL
* **Validação:** Zod (nestjs-zod)
* **Autenticação:** JWT (JSON Web Token)
* **Documentação:** Swagger & Scalar
* **Containerização:** Docker & Docker Compose

---

## ⚙️ Como Executar o Projeto

### 📋 Pré-requisitos

* Docker e Docker Compose
* Node.js **v18+**

---

### 📥 Instalação

Clone o repositório e instale as dependências:

```bash
npm install
```

---

### Subir o Banco de Dados

```bash
docker-compose up -d
```

> O arquivo `.env` já vem pré-configurado para ambiente Docker local.

---

### 📦 Executar Migrações

```bash
npx prisma migrate dev
```

---

### 🌱 Executar Seed (Usuário ADMIN)

```bash
npm run prisma:seed
```

**Credenciais padrão:**

* Email: `Tatiano@gmail.com`
* Senha: `123456789`

---

### ▶️ Iniciar a Aplicação

```bash
npm run start:dev
```

O servidor estará disponível em:

```
http://localhost:3000
```

---

## 📖 Documentação da API

Após iniciar o servidor, acesse:

* **Swagger UI:**

  * [http://localhost:3000/api/docs](http://localhost:3000/api/docs)

* **Scalar API Reference:**

  * [http://localhost:3000/reference](http://localhost:3000/reference)

---

## Segurança

* Autenticação baseada em JWT
* Proteção de rotas com Guards
* Controle de acesso por perfil (RBAC)

---

## Escalabilidade e Boas Práticas

* Clean Architecture
* Domain-Driven Design (DDD)
* Separação de responsabilidades
* Código testável e extensível
* Fácil adaptação para microsserviços no futuro

---

## Contribuição

Contribuições são bem-vindas!

1. Faça um fork do projeto
2. Crie uma branch (`feature/nova-feature`)
3. Commit suas alterações
4. Abra um Pull Request

---

## 📄 Licença

Este projeto está sob a licença **MIT**.

---

*Desenvolvido com foco em código limpo, qualidade e evolução contínua.*

