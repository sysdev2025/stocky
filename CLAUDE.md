# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository layout

The git repo root (`stocky/`) is only a wrapper. The actual application lives in `StockyApp/`, and all npm commands must be run from there. The root `package-lock.json` is an empty stub (no root `package.json`); ignore it.

`StockyApp/` is currently an unmodified `create-vue` scaffold (Vue 3 + Vite, plain JavaScript, no TypeScript). `App.vue`, `HelloWorld.vue`, `TheWelcome.vue`, `WelcomeItem.vue`, and `components/icons/` are template placeholders, not app code.

## Commands (run in `StockyApp/`)

```sh
npm install        # requires Node ^22.18.0 or >=24.12.0
npm run dev        # Vite dev server with HMR
npm run build      # production build to dist/
npm run preview    # serve the built dist/
npm run format     # Prettier over src/ (no semicolons, single quotes, printWidth 100)
```

There is no test runner, linter, or type checker configured.

## Notable setup details

- **Vue is pinned to the release candidate channel** (`"vue": "rc"`), with `overrides` forcing every `@vue/*` package (including `compiler-vapor` / `runtime-vapor`) to `rc`. Expect pre-release Vue 3.x behavior; check this before assuming stable-release APIs or docs apply.
- `@` is aliased to `StockyApp/src` (in both `vite.config.js` and `jsconfig.json`).
- `vite-plugin-vue-devtools` is enabled in the Vite config, so the in-browser Vue DevTools overlay is available during `npm run dev`.
- Components use `<script setup>` SFCs. Global styles come from `src/assets/main.css` (which imports `base.css`) and are loaded in `src/main.js`.
