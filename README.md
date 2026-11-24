# DevFlix — Netflix de Cursos

Aplicação web para divulgação de cursos de tecnologia, com experiência visual inspirada em plataformas de streaming. O projeto combina um frontend React com uma API NestJS e persistência de dados no PostgreSQL.

## Sobre o projeto

O DevFlix apresenta um catálogo organizado por categorias e permite buscar cursos, consultar informações, salvar favoritos durante a sessão e reproduzir conteúdos em vídeo.

No frontend, os dados do catálogo podem ser definidos localmente. No backend, uma API REST consulta categorias, cursos e aulas armazenados no banco de dados.

## Funcionalidades

- Catálogo de cursos organizado por categoria;
- Busca por título;
- Navegação por seções;
- Sistema de favoritos;
- Reprodução de vídeos;
- Layout responsivo;
- Consulta de categorias;
- Consulta de cursos e aulas;
- Persistência com PostgreSQL;
- Testes automatizados no backend.

## Tecnologias

- React e Vite;
- JavaScript e CSS;
- NestJS e TypeScript;
- Prisma ORM;
- PostgreSQL;
- Docker Compose;
- Vitest;
- Git e GitHub.

## Estrutura

```text
src/
├── assets/
├── components/
├── data/
├── App.jsx
├── App.css
└── main.jsx

backend/
├── prisma/
├── src/
│   ├── categories/
│   ├── courses/
│   ├── health/
│   ├── prisma/
│   ├── app.module.ts
│   └── main.ts
└── package.json

docker-compose.yml
package.json
README.md
```

## Pré-requisitos

- Node.js;
- npm;
- Git;
- Docker Compose.

## Instalação

Clone o repositório:

```bash
git clone https://github.com/matheus-ribeiro021/api-react.git
cd api-react
```

Instale as dependências do frontend:

```bash
npm install
```

Instale as dependências do backend:

```bash
cd backend
npm install --legacy-peer-deps
```

## Configuração do banco de dados

Na raiz do projeto, inicie o PostgreSQL:

```bash
docker compose up -d
```

Crie o arquivo `backend/.env`:

```env
DATABASE_URL="postgresql://devflix:devflix123@localhost:5434/devflix_db?schema=public"
```

Aplique as migrations e gere o Prisma Client:

```bash
cd backend
npx prisma migrate deploy
npx prisma db seed
npx prisma generate
```

## Executando o projeto

Inicie o backend:

```bash
cd backend
npm run start:dev
```

A API ficará disponível em `http://localhost:3000`.

Em outro terminal, na raiz do projeto, inicie o frontend:

```bash
npm run dev
```

O frontend ficará disponível em `http://localhost:5173`.

## Endpoints

| Método | Endpoint | Descrição |
| --- | --- | --- |
| GET | `/health` | Verifica o estado da API e a conexão com o banco |
| GET | `/categories` | Lista as categorias |
| GET | `/courses` | Lista os cursos e suas aulas |
| GET | `/courses/:id` | Consulta um curso pelo identificador |

## Testes e build

Frontend:

```bash
npm run build
```

Backend:

```bash
cd backend
npm run test
npm run build
```

## Repositório

[matheus-ribeiro021/api-react](https://github.com/matheus-ribeiro021/api-react)

## Autor

Matheus Ribeiro Saraiva

Projeto acadêmico desenvolvido na Unidade Curricular de Programação Web 2 do Senac RJ.

## Uso acadêmico

Projeto destinado ao estudo, desenvolvimento e avaliação acadêmica da disciplina.
