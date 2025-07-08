# NLW Agents - Web (Frontend)

Este é o frontend do projeto **NLW Agents**, desenvolvido durante a edição de 2024 do evento Next Level Week da [Rocketseat](https://www.rocketseat.com.br/).

## 🚀 Tecnologias Utilizadas

A interface foi construída com um ecossistema moderno de desenvolvimento para React:

- **Framework:** [React](https://react.dev/) com [Vite](https://vitejs.dev/) como bundler para uma experiência de desenvolvimento rápida.
- **Linguagem:** [TypeScript](https://www.typescriptlang.org/) para um código mais robusto e seguro.
- **Estilização:**
    - [Tailwind CSS](https://tailwindcss.com/) para uma abordagem utility-first.
    - [shadcn/ui](https://ui.shadcn.com/) para componentes de UI componentizados e customizáveis.
- **Roteamento:** [React Router DOM](https://reactrouter.com/) para navegação e gerenciamento de rotas.
- **Gerenciamento de Estado de Servidor:** [TanStack Query (React Query)](https://tanstack.com/query) para data fetching, cache e sincronização de estado com o backend.
- **Ícones:** [Lucide React](https://lucide.dev/) para uma biblioteca de ícones leve e consistente.

## 🏛️ Arquitetura e Padrões

- **Arquitetura baseada em Componentes:** O projeto é estruturado em componentes React reutilizáveis, seguindo as melhores práticas do ecossistema.
- **Comunicação com API:** A aplicação consome uma API REST para buscar e enviar dados, com o TanStack Query gerenciando o estado assíncrono.
- **Estilização Atômica:** O uso de Tailwind CSS promove a criação de interfaces de forma rápida e consistente através de classes de utilidade.

## ⚙️ Configuração do Ambiente

Siga os passos abaixo para configurar e executar o projeto localmente.

### Pré-requisitos

- Node.js (versão 20 ou superior)
- Um gerenciador de pacotes como npm, yarn ou pnpm.
- O **servidor backend** do projeto NLW Agents deve estar em execução.

### 1. Instalação

Clone o repositório e, dentro da pasta `web`, instale as dependências:

```bash
npm install
```

### 2. Configuração de Ambiente

Crie um arquivo `.env` na raiz da pasta `web`. A principal variável a ser configurada é a URL da API:

```env
VITE_API_URL=http://localhost:3333
```

*Este valor já é o padrão e deve funcionar se você estiver executando o backend localmente na porta `3333`.*

## 🚀 Executando o Projeto

Com o ambiente configurado, execute o seguinte comando para iniciar o servidor de desenvolvimento:

```bash
npm run dev
```

A aplicação estará disponível em `http://localhost:5173` (ou outra porta indicada pelo Vite).

### Build para Produção

Para gerar a versão de produção do projeto, execute:

```bash
npm run build
```

Os arquivos otimizados serão gerados na pasta `dist`.