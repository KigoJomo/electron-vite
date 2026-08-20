# Electron + Vite starter

My desktop app starting point for Electron, React, TypeScript, Tailwind CSS, and shadcn/ui.

It keeps Electron's main process, preload code, and React renderer in separate TypeScript projects. Context isolation stays enabled, and the renderer imports app code through the `@` alias.

## Included setup

- Electron and electron-vite for local development
- React 19 and Vite 7 for the renderer
- Tailwind CSS 4 and shadcn/ui
- ESLint, Prettier, and separate Node and web type checks
- electron-builder targets for Windows, macOS, and Linux
- electron-updater configuration for packaged builds

## Start a project

```bash
git clone https://github.com/KigoJomo/electron-vite.git my-desktop-app
cd my-desktop-app
pnpm install
pnpm dev
```

The useful source directories are:

| Path | Runs in |
| --- | --- |
| `src/main` | Electron main process |
| `src/preload` | Isolated bridge exposed to the renderer |
| `src/renderer` | React app inside Chromium |

## Checks

```bash
pnpm lint
pnpm typecheck
pnpm build
```

`pnpm build` compiles the app but does not create an installer. Use one of the packaging commands when you need an artifact.

```bash
pnpm build:win
pnpm build:mac
pnpm build:linux
```

Those targets still need to be tested on their respective operating systems. Cross-platform packaging is not the same as running the finished app there.
