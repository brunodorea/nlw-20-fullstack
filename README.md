# NLW Agents - Fullstack

Este é o projeto fullstack **NLW Agents**, desenvolvido durante a edição de 2024 do evento Next Level Week da [Rocketseat](https://www.rocketseat.com.br/).

## 🚀 Tecnologias Utilizadas

### Frontend

A interface foi construída com um ecossistema moderno de desenvolvimento para React:

- **Framework:** [React](https://react.dev/) com [Vite](https://vitejs.dev/) como bundler para uma experiência de desenvolvimento rápida.
- **Linguagem:** [TypeScript](https://www.typescriptlang.org/) para um código mais robusto e seguro.
- **Estilização:**
    - [Tailwind CSS](https://tailwindcss.com/) para uma abordagem utility-first.
    - [shadcn/ui](https://ui.shadcn.com/) para componentes de UI componentizados e customizáveis.
- **Roteamento:** [React Router DOM](https://reactrouter.com/) para navegação e gerenciamento de rotas.
- **Gerenciamento de Estado de Servidor:** [TanStack Query (React Query)](https://tanstack.com/query) para data fetching, cache e sincronização de estado com o backend.
- **Ícones:** [Lucide React](https://lucide.dev/) para uma biblioteca de ícones leve e consistente.

### Backend

O backend foi construído com um conjunto de tecnologias modernas para criar uma API robusta e eficiente:

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

### Frontend

- **Arquitetura baseada em Componentes:** O projeto é estruturado em componentes React reutilizáveis, seguindo as melhores práticas do ecossistema.
- **Comunicação com API:** A aplicação consome uma API REST para buscar e enviar dados, com o TanStack Query gerenciando o estado assíncrono.
- **Estilização Atômica:** O uso de Tailwind CSS promove a criação de interfaces de forma rápida e consistente através de classes de utilidade.

### Backend

- **API-first:** O uso de Fastify com Zod para validação de entrada e a possibilidade de gerar documentação com Swagger facilitam uma abordagem focada no contrato da API.
- **Separação de Responsabilidades:** A estrutura do projeto busca separar a lógica de rotas, a lógica de negócios e o acesso a dados.
- **Gerenciamento de Configuração:** As configurações sensíveis e de ambiente são gerenciadas através de variáveis de ambiente com o auxílio de um arquivo `.env`, seguindo as melhores práticas de segurança.

## ⚙️ Configuração do Ambiente

### Frontend

Siga os passos abaixo para configurar e executar o projeto localmente.

#### Pré-requisitos

- Node.js (versão 20 ou superior)
- Um gerenciador de pacotes como npm, yarn ou pnpm.
- O **servidor backend** do projeto NLW Agents deve estar em execução.

#### 1. Instalação

Clone o repositório e, dentro da pasta `web`, instale as dependências:

```bash
npm install
```

#### 2. Configuração de Ambiente

Crie um arquivo `.env` na raiz da pasta `web`. A principal variável a ser configurada é a URL da API:

```env
VITE_API_URL=http://localhost:3333
```

*Este valor já é o padrão e deve funcionar se você estiver executando o backend localmente na porta `3333`.*

### Backend

#### Pré-requisitos

- Node.js (versão 20 ou superior)
- Docker e Docker Compose
- Um gerenciador de pacotes como npm, yarn ou pnpm.

#### 1. Instalação das Dependências

Clone o repositório e instale as dependências do projeto:

```bash
npm install
```

#### 2. Configuração do Banco de Dados

O projeto utiliza Docker para provisionar o banco de dados PostgreSQL com a extensão `pgvector`. Para iniciar o container, execute:

```bash
docker-compose up -d
```

Isso irá iniciar o serviço `nlw-agents-pg` na porta `5432`.

#### 3. Variáveis de Ambiente

Copie o arquivo de exemplo `.env.example` para um novo arquivo chamado `.env`:

```bash
cp .env.example .env
```

As variáveis no arquivo `.env` já estão configuradas para se conectar com o banco de dados do Docker.


## 🚀 Executando o Projeto

### Frontend

Com o ambiente configurado, execute o seguinte comando para iniciar o servidor de desenvolvimento:

```bash
npm run dev
```

A aplicação estará disponível em `http://localhost:5173` (ou outra porta indicada pelo Vite).

### Backend

#### 1. Migrações do Banco de Dados

Com o banco de dados em execução, aplique as migrações do Drizzle para criar as tabelas necessárias:

```bash
npm run db:migrate
```

Para gerar novas migrações baseadas em alterações no schema, utilize:

```bash
npm run db:generate
```

#### 2. Iniciando o Servidor

Para iniciar o servidor em modo de desenvolvimento com hot-reload, execute:

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:3333`.

#### 3. Testando os Endpoints

Você pode utilizar o arquivo `client.http` com a extensão REST Client do VS Code para testar os endpoints da API.