This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

**Iniciar** 
npx create-next-app --typescript

**Name Folder**
projeto-prisma-graphql-nextjs

**Ferramentas usada no Projeto**
- Nextjs - Framework de React
- GraphQL - Grapqh Query Language
-- backend
-- frontend
- Prisma - ORM

**API FAKE**
jsonplaceholder.typicode.com/posts

**Instalação dos pacotes**
`` npm i -D prisma ``  A Letra D não vai para o build final apenas desenvovivelmento
`` npm i @prisma/client `` 

- Rodar 
`` npx prisma init ``

**Após criar o banco iremos inserir os dados via comando**
`` npx prisma db push ``
- O inverso vc usa pull quando tem o banco de dados pronto e trazer para o projeto

- Após colocar os dados no banco de dados manual, rodamos outro comando para integrar com os dados e integrar com o prisma client

`` npx prisma generate ``


**Configurando o GraphQL**
- Temos o apollo para consumir client e criar o servidor.
`` npm i graphql apollo-server-micro micro micro-cors`` 
`` npm i -D @types/micro-cors `` adicionado para dá suporte ao TS

- Depois criaremos uma pasta graphql( dentro: definição do servidor e cliente )
-- criaremos o typesDefs.ts ou schema.ts
-- resolvers.ts
-- context.ts

(1) passso
- No arquivo [ typesDefs.ts ] iremos configurar o que podemos acessar, fazer uma consulta Query em links e escolher qual tipo de dados acessar.

(2) passo
- No arquivo [ resolvers.ts ] iremos dar continuidade, ele vai no prisma pegas as informações( links ), depois alimentei o arquivo context.ts / pasta libs com arquivo prisma.ts

(3) passo 
- instalar a libs para ajustar os types do projeto
`` npm i @graphql-codegen/cli`` 
- onde está o codigo e o start
`` npx graphql-codegen init ``

- Seguir a sequencia abaixo:
backend
./graphql/typeDefs.ts
enter
escolher apenas 1 => typescript(required by other typescript plugins)
./graphql/resolvers-types.ts
no
yes
codegen


- Criado um arquivo chamado codegen.yml
Nele vc tira a parte da documents e inclui no plugins
- "typescript-resolvers"

- Depois npm install
- Por fim o comando abaixo
`` npm install -D @graphql-codegen/typescript-resolvers ``

- Iremos rodar o comando para ele criar o arquivo types
`` npm run codegen ``
- Após ele criar iremos importar no arquivo que está precisando dele o resolvers.ts

**FINALIZAMOS A PARTE DO BACKEND COM GRAPHQL**

**INICIANDO A CRIAÇÃO DA API**
Dentro da pasta pages/api criaremos o arquivo graphql.ts
Depois de definir  path: '/api/graphql'
Iremos rodar npm run dev e acessar localhost:3000/api/graphql e clicar BTN query your server

Na coluna Operation podemos fazer a consulta 
query ConsultarLinks {
  links {
    id
    title
  }
}

Dando o nome ConsultarLinks ou apenas com o query

- Iremos instalar o apolloClient
`` npm i @apollo/client ``

- Criar o arquivo apollo-client.ts dentro da pasta graphql











