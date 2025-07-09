# NLW Agents

Projeto full-stack desenvolvido durante o evento NLW da Rocketseat, demonstrando o uso de agentes inteligentes com um backend robusto construído com Node.js e uma interface web moderna com React.

## 🚀 Tecnologias

### **Back-end (server)**

-   **Node.js** com TypeScript nativo (`--experimental-strip-types`)
-   **Fastify** - Framework web rápido e eficiente
-   **PostgreSQL** com extensão `pgvector` para vetores
-   **Drizzle ORM** - Operações de banco de dados type-safe
-   **Zod** - Validação de schemas
-   **Docker** - Containerização do banco de dados
-   **Biome** - Linting e formatação de código

### **Front-end (web)**

-   **React 19.1** - Biblioteca para interfaces de usuário
-   **TypeScript 5.8** - Superset JavaScript com tipagem estática
-   **Vite 7.0** - Build tool e servidor de desenvolvimento
-   **TailwindCSS 4.1** - Framework CSS utility-first
-   **React Router Dom 7.6** - Biblioteca de roteamento
-   **TanStack React Query 5.8** - Gerenciamento de estado do servidor e cache
-   **Radix UI** - Componentes primitivos acessíveis
-   **Shadcn/ui** - Sistema de componentes
-   **Lucide React** - Biblioteca de ícones

## 🏗️ Arquitetura e Padrões de Projeto

### **Back-end**

O projeto segue uma arquitetura modular com:
-   **Separação de responsabilidades** entre rotas, schemas e conexão com banco
-   **Validação de schemas** com Zod para type safety
-   **ORM type-safe** com Drizzle para operações de banco de dados
-   **Validação de variáveis de ambiente** centralizadas

### **Front-end**

-   **Component-based Architecture** - Arquitetura baseada em componentes React
-   **File-based Routing** - Roteamento baseado em arquivos com React Router
-   **Server State Management** - Gerenciamento de estado do servidor com React Query
-   **Variant-based Components** - Componentes com variantes usando CVA
-   **Composition Pattern** - Padrão de composição com Radix Slot
-   **Path Aliasing** - Alias de caminhos (`@/` aponta para `src/`)

## ⚙️ Setup e Configuração do Projeto Completo

**Pré-requisitos:**
* Node.js (versão 18+ com suporte a `--experimental-strip-types`)
* Docker e Docker Compose
* `npm` ou `yarn`

### **1. Clone o repositório**

```bash
git clone <url-do-repositorio>
cd <nome-do-repositorio>
```

### **2. Configurando o Back-end (server)**

Primeiro, vamos configurar o ambiente do servidor.

**a. Navegue para a pasta do servidor**
```bash
cd server
```

**b. Inicie o banco de dados**
```bash
docker-compose up -d
```

**c. Configure as variáveis de ambiente**
Crie um arquivo `.env` na raiz da pasta `server` com o seguinte conteúdo:
```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

**d. Instale as dependências do back-end**
```bash
npm install
```

**e. Execute as migrações do banco**
```bash
npx drizzle-kit migrate
```

**f. (Opcional) Popule o banco com dados de exemplo**
```bash
npm run db:seed
```

### **3. Configurando o Front-end (web)**

Agora, vamos configurar a interface do usuário.

**a. Navegue para a pasta do front-end**
(Se você estiver na pasta `server`, volte para a raiz com `cd ..` primeiro)
```bash
cd web
```

**b. Instale as dependências do front-end**
```bash
npm install
```

## 🏃‍♀️ Executando a Aplicação

Para executar o projeto, você precisará de dois terminais abertos, um para o back-end e outro para o front-end.

**1. Inicie o Back-end:**
Em um terminal, navegue até a pasta `server` e execute:
```bash
# Dentro da pasta 'server'
npm run dev
```
O servidor da API estará disponível em `http://localhost:3333`.

**2. Inicie o Front-end:**
Em outro terminal, navegue até a pasta `web` e execute:
```bash
# Dentro da pasta 'web'
npm run dev
```
A aplicação web estará acessível em `http://localhost:5173`.

## 📚 Scripts Disponíveis

### **Back-end (server)**
-   `npm run dev` - Executa o servidor em modo de desenvolvimento com hot reload.
-   `npm start` - Executa o servidor em modo de produção.
-   `npm run db:seed` - Popula o banco de dados com dados de exemplo.

### **Front-end (web)**
-   `npm run dev` - Inicia o servidor de desenvolvimento.
-   `npm run build` - Gera a build de produção.
-   `npm run preview` - Pré-visualiza a build de produção.

## 🌐 Endpoints da API

-   `GET /health` - Health check da aplicação.
-   `GET /rooms` - Lista as salas disponíveis.

## 📂 Estrutura do Projeto

```
/
├── server/       # Código do Back-end (Node.js, Fastify)
└── web/          # Código do Front-end (React, Vite)
    ├── src/
    │   ├── components/ui/
    │   ├── pages/
    │   ├── lib/
    │   └── app.tsx
    └── ...
```

---
Desenvolvido com ❤️ durante o NLW da Rocketseat
