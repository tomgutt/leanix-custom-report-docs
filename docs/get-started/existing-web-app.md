# Existing web app (non‑Vite) integration

Integrate LeanIX reporting into an existing project that does not use Vite (e.g., webpack, Create React App, Angular CLI, Next.js, Rollup, Parcel, etc.) by adding the LeanIX reporting runtime.

## When to use this

- You already have a build/dev setup and do not want to switch to Vite.
- You only need the LeanIX reporting runtime to run your report inside LeanIX.

If you are starting fresh or already using Vite, see:
- Fresh start: ./fresh-start.md
- Vite plugin: ./vite-plugin.md

## 1) Install the runtime

```bash
npm install @leanix/reporting
# or: yarn add @leanix/reporting
# or: pnpm add @leanix/reporting
```

## 2) Initialize in your app entry

Use one of the following approaches depending on your project.

### ES modules (recommended)

Add this to your main entry (e.g., `src/main.ts`, `src/index.tsx`, `src/main.js`, or similar):

```ts
// Ensure the library is loaded; it will expose a global `lx` object.
import '@leanix/reporting';

async function bootstrap() {
  // Wait for the LeanIX host to initialize the report context.
  const setupInfo = await lx.init();

  // Define the report configuration object.
  // Fill this with the callbacks and settings your report needs.
  // See LeanIX reporting docs/typedoc for available options.
  const config = {
    // Example placeholders:
    // getView: () => 'my-view',
    // getConfig: () => ({ /* report settings schema */ }),
    // onData: async ({ config, workspace }) => { /* fetch/process data */ },
  };

  // Signal readiness to the host with your configuration.
  lx.ready(config);
}

bootstrap();
```

### As a script tag (no bundler or legacy setups)

Include the library in your HTML and initialize:

```html
<script src="node_modules/@leanix/reporting/index.js"></script>
<script>
  lx.init().then(function (setupInfo) {
    var config = {
      // Define required callbacks and settings here.
    };
    lx.ready(config);
  });
</script>
```

## 3) Build as usual

- Keep your existing bundler configuration.
- The `import '@leanix/reporting'` side‑effect makes `lx` globally available; you do not need to `import lx`.
- If you prefer to load `@leanix/reporting` a `<script>` tag instead, mark it as external in your bundler and include the script manually.

## 4) Local development considerations

- The `lx.init()` handshake expects to run inside the LeanIX host. Opening your page directly in a browser without the host will not initialize the library.
- For a full local develop/upload loop integrated with LeanIX, consider the Vite plugin path: ./vite-plugin.md

## 5) Troubleshooting

- `lx is not defined`: ensure `@leanix/reporting` is imported (ESM) or the script tag is included before your initialization code.
- Stuck on `lx.init()`: the page is not running inside the LeanIX host. Use the official dev flow, or switch to the Vite plugin path for local iteration.