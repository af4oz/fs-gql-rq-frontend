# Blogger site + User Authentication & Session Management(Frontend)
It includes user authentication flow based on [synchronizer-token-pattern](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html#synchronizer-token-pattern) (per session tokens) + fingerprint [cookie](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#cookies)(sameSite,secure,httpOnly) , tab synchronization using broadcast channel. It uses React, Graphql, Apollo server, Express, Nexus, React-query, jest, vite, vitest (improved testing for vite).

## Here's [Backend repo](https://github.com/af4oz/fs-gql-rq-backend)

## Requirements

1. `node>=14` for `vitest`

## Available Scripts

### Init

```sh
# setup MSW (app)
yarn app msw:init
```

### [web app](./packages/web)

```sh

# download the published GraphQL schema from apollo studio (Need to setup rover auth)
# follow docs: https://www.apollographql.com/docs/rover/configuring/#2-provide-the-api-key-to-rover
npx rover config auth
npx rover graph fetch [your_graph_id]@[variant] > src/__generated__/schema.graphql

# download the GraphQL schema from a local development server (eg:http://localhost:4000)
yarn app download:schema:local

# Generate static types for GraphQL queries. Use the downloaded schema
yarn app gql:codegen

yarn app dev
yarn app test
yarn app coverage
yarn app preview
yarn app build

```

## Future

1. Add e2e tests
2. ~~improve token synchronization between tabs~~ ✅️

## Troubleshoot

<details>
<summary>
Cannot find module '/[redacted]/starter/.yarn/releases/yarn-berry.cjs
</summary>

```sh
rm .yarnrc.yml
yarn set version berry

# and add below line to `.yarnrc.yml`
nodeLinker: node-modules

```

</details>
