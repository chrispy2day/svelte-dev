# 🚀 Svelte DevContainer Template for DevPods

A GitHub template repository providing a pre-configured development container for building Svelte applications using DevPods. This template gives you a complete, developer-ready environment with zero configuration. 🎉

## 🤔 Why Use This Template?

### ⚡ Quick Start Benefits

- **⏱️ Zero Configuration**: Start coding immediately without spending hours setting up your environment
- **🎯 Consistent Environment**: Every developer gets the same tools, versions, and settings
- **📦 Isolated Development**: Your Svelte projects run in containers, keeping your local machine clean
- **🛠️ Pre-configured Tools**: Svelte tooling, linting, formatting, and AI assistance ready out of the box
- **☁️ DevPods Ready**: Optimized for use with DevPods for seamless cloud and local development

### 💡 Perfect For

- 🏃 Starting new Svelte projects quickly
- 👥 Team projects requiring consistent development environments
- 📚 Learning Svelte without environment setup hassles
- 🧪 Prototyping and experimentation
- 🎓 Teaching and workshops

## 📋 How to Use This Template

### Option 1: Create a New Repository from Template (Recommended) ⭐

1. Click the **"Use this template"** button at the top of this repository 🖱️
2. Choose **"Create a new repository"** ➕
3. Name your repository and set visibility (public/private) 📝
4. Click **"Create repository"** ✅
5. Clone your new repository locally 💻
6. Open in DevPods or VS Code with Dev Containers extension 🎯

### Option 2: Use with DevPods Directly 🐳

If you have DevPods installed:

```bash
devpod up https://github.com/YOUR-USERNAME/YOUR-REPO-NAME
```

Replace `YOUR-USERNAME/YOUR-REPO-NAME` with your repository details after creating from the template.

### Option 3: Clone and Customize 🔧

```bash
git clone https://github.com/chrispy2day/svelte-dev.git my-svelte-project
cd my-svelte-project
rm -rf .git
git init
# Open in DevPods or VS Code
```

## 📦 What's Included

- **🐳 Base Image**: `ghcr.io/devcontainers/templates/javascript-node:4.0.2`
- **⚡ Node.js**: Latest LTS version
- **📦 Package Manager**: npm (auto-updated on container creation)
- **🎯 Degit**: Pre-installed for scaffolding Svelte projects

### 🔌 VS Code Extensions

The devcontainer automatically installs:

- **🔥 Svelte for VS Code** - Syntax highlighting, intellisense, and formatting for Svelte
- **✅ ESLint** - JavaScript/TypeScript linting
- **💅 Prettier** - Code formatting
- **🤖 Claude Code** - AI-powered coding assistant with Context7 MCP server integration

### ⚙️ Editor Settings

- ✨ Format on save enabled
- 🎨 Svelte files use the Svelte formatter
- 🧠 Claude Code pre-configured with Context7 for intelligent documentation lookup

## 🚀 Getting Started

### 🎬 First Time Setup

After creating your repository from this template:

1. **🐳 Open in DevPods** (or VS Code with Dev Containers extension)
   - DevPods will automatically detect the devcontainer configuration
   - The container will build and start automatically
   - Wait for initialization to complete ⏳

2. **✅ Verify Your Environment**

   ```bash
   node --version
   npm --version
   ```

3. **🎨 Start Building Your Svelte App** (see options below)

### 🎯 Creating a New Svelte App

Once inside the devcontainer, you can create a new Svelte app using one of these methods:

#### Option 1: Using Vite (Recommended) ⚡

```bash
npm create vite@latest my-app -- --template svelte
cd my-app
npm install
npm run dev
```

#### Option 2: Using SvelteKit 🏗️

```bash
npm create svelte@latest my-app
cd my-app
npm install
npm run dev
```

#### Option 3: Using Degit 📋

```bash
degit sveltejs/template my-app
cd my-app
npm install
npm run dev
```

### 🌐 Accessing Your App

The devcontainer forwards port **5173** (Vite's default dev server port). Once your dev server is running, you can access your app at `http://localhost:5173`. 🎉

## ⚙️ Devcontainer Configuration

The devcontainer configuration consists of:

- **📄 [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json)** - Container settings, VS Code extensions, and editor configuration
- **🐳 [.devcontainer/Dockerfile](.devcontainer/Dockerfile)** - Docker image definition based on the official Node.js devcontainer template

## 🎨 Customization

### 🔌 Adding More Extensions

Edit [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) and add extension IDs to the `extensions` array:

```json
"extensions": [
  "svelte.svelte-vscode",
  "dbaeumer.vscode-eslint",
  "esbenp.prettier-vscode",
  "your.extension-id"
]
```

### 📦 Adding Node Packages Globally

Edit [.devcontainer/Dockerfile](.devcontainer/Dockerfile) and add `RUN` commands:

```dockerfile
RUN npm install -g your-package-name
```

### 🌐 Forwarding Additional Ports

Edit [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) and add ports to the `forwardPorts` array:

```json
"forwardPorts": [5173, 3000, 8080]
```

## 🔧 Troubleshooting

### 🚫 Port Already in Use

If port 5173 is already in use, you can specify a different port when starting the dev server:

```bash
npm run dev -- --port 3000
```

Make sure to add the new port to `forwardPorts` in devcontainer.json.

### ❌ Extensions Not Loading

If VS Code extensions don't load automatically, rebuild the container:

1. Open the command palette (Cmd/Ctrl + Shift + P) ⌨️
2. Select "Dev Containers: Rebuild Container" 🔄

## 📄 License

This devcontainer configuration is provided as-is for development purposes. 💙
