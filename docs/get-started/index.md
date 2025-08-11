# LeanIX Custom Reports – Start here

Choose the path that matches your situation to build and run a LeanIX Custom Report.

## Prerequisites

- Node.js 18+ (LTS) and a package manager (npm, Yarn, or PNPM)
- A LeanIX workspace (credentials and local dev details are covered in the linked guides)

## Pick your path

- I’m starting from scratch (recommended for newcomers)
  - Use the official scaffolder to generate a ready-to-hack project.
  - Go to: [Fresh start with create-lxr](./fresh-start.md)

- I already have a Vite project
  - Add our Vite plugin to enable local development and upload flows.
  - Go to: [Vite plugin guide](./vite-plugin.md)

- I have an existing web app that does not use Vite (e.g., webpack, CRA, Angular CLI, Next.js, etc.)
  - Add the LeanIX reporting runtime to integrate with LeanIX without changing your bundler.
  - Go to: [Existing web app (non‑Vite) guide](./existing-web-app.md)

## What each option gives you

- Fresh start
  - Scaffolds a project with your chosen framework (Vanilla, React, Vue, Svelte, etc.).
  - Sets up sensible defaults and dependency wiring so you can focus on your report logic.

- Vite plugin
  - Adds `vite-plugin-lxr` to your Vite project for local dev, build, and upload flows.
  - Covers the minimal configuration (`leanixReport` metadata, `lxr.json`, dev/build/upload scripts).

- Existing webapp without Vite
  - Add `@leanix/reporting` to your current toolchain and initialize it in your app entry.
  - Keep your existing bundler and project structure; only the reporting runtime is needed.

## Docs map

- [Fresh start with create-lxr](./fresh-start.md)
- [Vite plugin guide](./vite-plugin.md)
- [Existing web app (non‑Vite) guide](./existing-web-app.md)
