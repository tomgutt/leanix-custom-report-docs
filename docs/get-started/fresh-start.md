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

If you are unsure which template to choose, select the vanilla TypeScript preset. In the prompts, choose:
- Framework: Vanilla
- Variant: TypeScript

### Run the scaffolding (interactive)

Run the CLI and follow the prompts. A terminal UI will open; fill in the requested fields. The tool scaffolds a Vite-based project with the LeanIX Vite plugin and npm scripts (dev/build/upload) preconfigured.

```bash
npm init lxr@latest
```

Example of the interactive prompts (for reference):

```
LeanIX Custom Report Scaffolding Tool v1.1.4

✔ Project name: … leanix-custom-report
✔ Select a framework: › Vanilla
✔ Select a variant: › TypeScript
✔ Unique id for this report in Java package notation (e.g. net.leanix.barcharts) … my.unique.id
✔ Who is the author of this report (e.g. LeanIX GmbH) … John Doe
✔ A title to be shown in LeanIX when report is installed … Custom Report Title
✔ Description of your project … Custom Report Description
✔ Which host do you want to work with? … demo-eu-1.leanix.net
✔ API-Token for Authentication (see: https://dev.leanix.net/docs/authentication#section-generate-api-tokens) … F235...
✔ Are you behind a proxy? … No / Yes
```

Note: An AI coding assistant cannot answer these organization-specific prompts automatically, but this shows exactly what will be asked so you can prepare the values.

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