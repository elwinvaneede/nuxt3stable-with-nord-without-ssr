# Nuxt 3 with Nord without SSR

POC for [Nuxt 3 stable](https://nuxt.com/) together with Nord using client-side rendering (CSR).

It still uses the Nuxt 3 server for API routes which makes a [BFF](https://blog.bitsrc.io/bff-pattern-backend-for-frontend-an-introduction-e4fa965128bf) possible.

Later on we might want to use [hybrid rendering](https://nuxt.com/docs/guide/concepts/rendering#hybrid-rendering) to start using SSR on some specific routes that might benefit from it (when our Web Components support SSR).

Integrated [vue-i18n](https://vue-i18n.intlify.dev/) through a plugin since the Nuxt 3 module is still under development.
Linked it with `useHead()` to set the correct `lang` and `dir` attributes on the `<html>` element.

## Setup

Make sure to install the dependencies:

```bash
# yarn
yarn install

# npm
npm install

# pnpm
pnpm install --shamefully-hoist
```

## Development Server

Start the development server on http://localhost:3000

```bash
npm run dev
```

## Production

Build the application for production:

```bash
npm run build
```

Locally preview production build:

```bash
npm run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
