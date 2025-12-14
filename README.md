# Svelte DevContainer for DevPods

This repository provides a pre-configured development container for building Svelte applications using DevPods.

## What's Included

- **Base Image**: `ghcr.io/devcontainers/templates/javascript-node:4.0.2`
- **Node.js**: Latest LTS version
- **Package Manager**: npm (auto-updated on container creation)
- **Degit**: Pre-installed for scaffolding Svelte projects

### VS Code Extensions

The devcontainer automatically installs:

- **Svelte for VS Code** - Syntax highlighting, intellisense, and formatting for Svelte
- **ESLint** - JavaScript/TypeScript linting
- **Prettier** - Code formatting

### Editor Settings

- Format on save enabled
- Svelte files use the Svelte formatter

## Getting Started

### Using with DevPods

1. Open this repository in DevPods
2. DevPods will automatically build and start the devcontainer
3. Wait for the container to initialize and install dependencies

### Creating a New Svelte App

Once inside the devcontainer, you can create a new Svelte app using one of these methods:

#### Option 1: Using Vite (Recommended)

```bash
npm create vite@latest my-app -- --template svelte
cd my-app
npm install
npm run dev
```

#### Option 2: Using SvelteKit

```bash
npm create svelte@latest my-app
cd my-app
npm install
npm run dev
```

#### Option 3: Using Degit

```bash
degit sveltejs/template my-app
cd my-app
npm install
npm run dev
```

### Accessing Your App

The devcontainer forwards port **5173** (Vite's default dev server port). Once your dev server is running, you can access your app at `http://localhost:5173`.

## Devcontainer Configuration

The devcontainer configuration consists of:

- **[.devcontainer/devcontainer.json](.devcontainer/devcontainer.json)** - Container settings, VS Code extensions, and editor configuration
- **[.devcontainer/Dockerfile](.devcontainer/Dockerfile)** - Docker image definition based on the official Node.js devcontainer template

## Customization

### Adding More Extensions

Edit [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) and add extension IDs to the `extensions` array:

```json
"extensions": [
  "svelte.svelte-vscode",
  "dbaeumer.vscode-eslint",
  "esbenp.prettier-vscode",
  "your.extension-id"
]
```

### Adding Node Packages Globally

Edit [.devcontainer/Dockerfile](.devcontainer/Dockerfile) and add `RUN` commands:

```dockerfile
RUN npm install -g your-package-name
```

### Forwarding Additional Ports

Edit [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) and add ports to the `forwardPorts` array:

```json
"forwardPorts": [5173, 3000, 8080]
```

## Troubleshooting

### Port Already in Use

If port 5173 is already in use, you can specify a different port when starting the dev server:

```bash
npm run dev -- --port 3000
```

Make sure to add the new port to `forwardPorts` in devcontainer.json.

### Extensions Not Loading

If VS Code extensions don't load automatically, rebuild the container:

1. Open the command palette (Cmd/Ctrl + Shift + P)
2. Select "Dev Containers: Rebuild Container"

## License

This devcontainer configuration is provided as-is for development purposes.
