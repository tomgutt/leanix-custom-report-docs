# Fresh start with create-lxr

## Scaffolding Your First LeanIX Custom Report

> **Compatibility Note:**
> Requires [Node.js](https://nodejs.org/en/) 18+ (LTS).

With NPM:

```bash
$ npm init lxr@latest
```

With Yarn:

```bash
$ yarn create lxr
```

With PNPM:

```bash
$ pnpx create-lxr
```

Then follow the prompts!

### Template contents and cleanup

The scaffolder includes template artifacts (e.g., a hello‑world page/component, demo styles, and example code/tests) to verify the setup. After creating your project, remove these artifacts so you start from a clean slate before implementing your report logic.

Common items to delete after scaffolding:
- Demo pages/components and placeholder styles
- Example utilities/tests that are only there to showcase the template

### Recommended golden path

If you are unsure which template to choose, select the vanilla TypeScript preset (`vanilla-ts`). It provides the smallest, framework‑agnostic starting point with TypeScript enabled, making it easy to integrate LeanIX reporting APIs and add any UI library later as needed.

You can also directly specify the project name and the template you want to use via additional command line options. For example, to scaffold a LeanIX Custom Report using the recommended vanilla TypeScript template, run:

```bash
# npm 6.x
npm init lxr@latest my-custom-report --template vanilla-ts

# npm 7+, extra double-dash is needed:
npm init lxr@latest my-custom-report -- --template vanilla-ts

# yarn
yarn create lxr my-custom-report --template vanilla-ts

# pnpm
pnpx create-lxr my-custom-report --template vanilla-ts
```

### After scaffolding: common commands

The scaffolding includes the Vite plugin and scripts. Use these commands:

```bash
# Start the local dev server
npm run dev

# Build for production
npm run build

# Build and upload the report to your LeanIX workspace
npm run upload
```

Workspace access required:
- Your LeanIX workspace domain (e.g., `demo-eu.leanix.net`)
- A LeanIX API Token or Technical User token

Configure these using the CLI tool.

Currently supported template presets include:

- `vanilla`
- `vanilla-ts`
- `vue`
- `vue-ts`
- `react`
- `react-ts`
- `preact`
- `preact-ts`
- `svelte`
- `svelte-ts`


[← Back to README](../../README.md)