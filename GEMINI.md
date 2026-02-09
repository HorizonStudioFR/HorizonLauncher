# HorizonLauncher Project Context

HorizonLauncher is a specialized Minecraft launcher built with Electron, derived from the [Helios Launcher](https://github.com/dscalzi/HeliosLauncher). It automates the management of game assets, Java runtimes, and server-specific configurations (mods, forge, etc.) based on a remote distribution index.

## Project Overview

- **Core Technologies:** Electron, Node.js, EJS (templating), `helios-core`.
- **Primary Function:** Provides a user-friendly interface for players to join modded Minecraft servers without manual installation of dependencies.
- **Key Features:**
    - **Authentication:** Supports both Mojang (Yggdrasil) and Microsoft (OAuth 2.0) accounts.
    - **Distribution System:** Fetches server metadata, mods, and assets from a remote `distribution.json`.
    - **Asset Management:** Validates and downloads necessary files (Java, Forge, Fabric, Mods) before launch.
    - **Auto-Updates:** Integrated `electron-updater` for seamless launcher updates.

## Architecture

- **Main Process (`index.js`):** Entry point for Electron. Manages application lifecycle, window creation, auto-updates, and handles complex IPC tasks like Microsoft OAuth flows.
- **Renderer Process (`app/app.ejs`):** Uses EJS for dynamic UI rendering. Logic is modularized in `app/assets/js/`.
- **Key Modules:**
    - `ConfigManager` (`app/assets/js/configmanager.js`): Persists user settings and account data in `config.json`.
    - `AuthManager` (`app/assets/js/authmanager.js`): Abstracts authentication logic for different account types.
    - `DistroManager` (`app/assets/js/distromanager.js`): Interfaces with the remote distribution API (`https://horizon-rp.fr/distribution.json`).
    - `UIBinder` (`app/assets/js/scripts/uibinder.js`): Connects background logic to the frontend views.
    - `ProcessBuilder` (`app/assets/js/processbuilder.js`): Constructs the Minecraft launch command with appropriate arguments.

## Development Workflows

### Prerequisites
- **Node.js:** v22.x.x (specified in `package.json`).
- **Package Manager:** `npm`.

### Key Commands
- **Install Dependencies:** `npm install`
- **Development Mode:** `npm start` (Runs Electron in the current directory).
- **Linting:** `npm run lint` (Uses ESLint with `@stylistic` plugins).
- **Building Installers:**
    - Current Platform: `npm run dist`
    - Windows: `npm run dist:win`
    - macOS: `npm run dist:mac`
    - Linux: `npm run dist:linux`

### Configuration
- **Launcher Data Directory:** Typically stored in `%APPDATA%/.horizonlauncher` (Windows) or `~/Library/Application Support/.horizonlauncher` (macOS).
- **Distribution URL:** Configured in `app/assets/js/distromanager.js`.

## Development Conventions

- **IPC Usage:** IPC constants are centralized in `app/assets/js/ipcconstants.js`. Use these for all communication between Main and Renderer processes.
- **Styling:** CSS is located in `app/assets/css/launcher.css`. UI icons and assets are in `app/assets/images/`.
- **Localization:** Language strings are stored in TOML files under `app/assets/lang/` (e.g., `en_US.toml`). Use `LangLoader` to retrieve them.
- **Error Handling:** Use `LoggerUtil` from `helios-core` for consistent logging across the application.
