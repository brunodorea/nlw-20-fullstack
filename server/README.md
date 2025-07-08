# NLW Agents - Server

Este é o backend do projeto **NLW Agents**, desenvolvido durante a edição de 2024 do evento Next Level Week da [Rocketseat](https://www.rocketseat.com.br/).

## 🚀 Tecnologias Utilizadas

O projeto foi construído com um conjunto de tecnologias modernas para criar uma API robusta e eficiente:

- **Framework:** [Fastify](https://fastify.dev/) - Um framework web para Node.js focado em performance e baixo overhead.
- **Linguagem:** [TypeScript](https://www.typescriptlang.org/) - Para adicionar tipagem estática e segurança ao JavaScript.
- **ORM:** [Drizzle ORM](https://orm.drizzle.team/) - Um ORM "headless" para TypeScript, que oferece uma experiência de desenvolvimento próxima ao SQL.
- **Banco de Dados:** [PostgreSQL](https://www.postgresql.org/) com a extensão [pgvector](https://github.com/pgvector/pgvector) para manipulação de dados vetoriais.
- **Validação:** [Zod](https://zod.dev/) - Para validação de schemas e tipos de dados, integrado com o Fastify.
- **Containerização:** [Docker](https://www.docker.com/) - Para criar e gerenciar o ambiente do banco de dados de forma isolada e consistente.
- **Tooling:**
  - **[Biome](https://biomejs.dev/):** Utilizado como formatador e linter para garantir a qualidade e a consistência do código.
  - **[tsx](https://github.com/esbuild-kit/tsx):** Para executar o código TypeScript diretamente sem a necessidade de uma etapa de build em desenvolvimento.

## 🏛️ Arquitetura e Padrões

O backend segue padrões modernos de desenvolvimento de API, focando em clareza e manutenibilidade:

- **API-first:** O uso de Fastify com Zod para validação de entrada e a possibilidade de gerar documentação com Swagger facilitam uma abordagem focada no contrato da API.
- **Separação de Responsabilidades:** A estrutura do projeto busca separar a lógica de rotas, a lógica de negócios e o acesso a dados.
- **Gerenciamento de Configuração:** As configurações sensíveis e de ambiente são gerenciadas através de variáveis de ambiente com o auxílio de um arquivo `.env`, seguindo as melhores práticas de segurança.

## ⚙️ Configuração do Ambiente

Siga os passos abaixo para configurar e executar o projeto em seu ambiente de desenvolvimento.

### Pré-requisitos

- Node.js (versão 20 ou superior)
- Docker e Docker Compose
- Um gerenciador de pacotes como npm, yarn ou pnpm.

### 1. Instalação das Dependências

Clone o repositório e instale as dependências do projeto:

```bash
npm install
```

### 2. Configuração do Banco de Dados

O projeto utiliza Docker para provisionar o banco de dados PostgreSQL com a extensão `pgvector`. Para iniciar o container, execute:

```bash
docker-compose up -d
```

Isso irá iniciar o serviço `nlw-agents-pg` na porta `5432`.

### 3. Variáveis de Ambiente

Copie o arquivo de exemplo `.env.example` para um novo arquivo chamado `.env`:

```bash
cp .env.example .env
```

As variáveis no arquivo `.env` já estão configuradas para se conectar com o banco de dados do Docker.

## 🚀 Executando o Projeto

### 1. Migrações do Banco de Dados

Com o banco de dados em execução, aplique as migrações do Drizzle para criar as tabelas necessárias:

```bash
npm run db:migrate
```

Para gerar novas migrações baseadas em alterações no schema, utilize:

```bash
npm run db:generate
```

### 2. Iniciando o Servidor

Para iniciar o servidor em modo de desenvolvimento com hot-reload, execute:

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:3333`.

### 3. Testando os Endpoints

Você pode utilizar o arquivo `client.http` com a extensão REST Client do VS Code para testar os endpoints da API.