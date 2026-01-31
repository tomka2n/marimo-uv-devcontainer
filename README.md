# marimo-uv-devcontainer

A modern, high-performance Python development environment for **marimo** notebooks, powered by **uv**, **Ruff**, and **ty**.

## 🚀 Key Features

- **marimo**: A reactive notebook for Python.
- **uv**: Extremely fast Python package and version management.
- **Ruff & ty**: High-speed linting, formatting, and static type checking to keep your code clean.
- **Hardware Access**: Pre-configured with `dialout` group permissions to access USB serial devices for sensor data processing.
- **Learning-Oriented**: Auto-fix on save is disabled for Ruff (`source.fixAll.ruff: never`) to encourage manual correction and learning.

## 📂 Directory Structure

```text
.
├── .devcontainer/     # Configuration for Dev Container
├── projects/          # Your project directories (independent Git repos)
└── .gitignore         # Configured to keep your host clean
```

## 🛠️ Getting Started

1. Open this folder in VS Code.
1. Click **"Reopen in Container"** when prompted.
1. Move to the projects folder: `cd projects`.
1. Create a new project: `mkdir my-project && cd my-project`.
1. Initialize with uv: `uv init`.
1. Start marimo: `marimo edit`.

## ⚙️ Customization

You can change tool versions (e.g., Python, uv, marimo) by modifying the `args` section in `.devcontainer/devcontainer.json` and rebuilding the container.