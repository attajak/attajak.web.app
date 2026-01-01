# Project Context: Attajak Web App

## Overview
This project is a static website built with [Hugo](https://gohugo.io/), utilizing the [FixIt](https://github.com/hugo-fixit/FixIt) theme via the [fixit-bundle](https://github.com/hugo-fixit/fixit-bundle). It is hosted on **Firebase Hosting** and deployed via GitHub Actions.

## Tech Stack
*   **Static Site Generator:** Hugo (Extended version required)
*   **Theme:** FixIt (managed via Go Modules)
*   **Language:** Go (for Hugo Modules), Markdown (for content)
*   **Scripting:** Node.js/npm (used for build/server shortcuts)
*   **Hosting:** Google Firebase Hosting
*   **CI/CD:** GitHub Actions

## Key Directories and Files
*   `config/`: Hugo configuration files, split by environment (`_default`, `development`, `production`).
    *   `_default/hugo.toml`: Main configuration file.
*   `content/`: Website content in Markdown format.
    *   `posts/`: Blog posts.
    *   `projects/`: Project showcase.
*   `layouts/`: Custom HTML layouts overriding the theme.
*   `assets/`: SCSS, JavaScript, and images.
*   `static/`: Static assets served as-is (e.g., `robots.txt`, `favicon`).
*   `go.mod` & `go.sum`: Manages Hugo Module dependencies (theme components).
*   `package.json`: NPM scripts for common tasks.
*   `.github/workflows/deploy.yml`: Workflow to build and deploy to Firebase.

## Development Workflow

### Prerequisites
*   **Hugo (Extended):** Ensure `hugo version` shows `extended`.
*   **Go:** Required for Hugo Modules.
*   **Node.js:** Optional, but useful for running predefined scripts.

### Common Commands (via npm)
The `package.json` file provides convenient shortcuts:

| Command | Description | Equivalent Hugo Command |
| :--- | :--- | :--- |
| `npm run server` | Start local dev server | `hugo server -D -E ... --bind 0.0.0.0` |
| `npm run build` | Build for production | `hugo --gc --minify` |
| `npm run clean` | Clean build artifacts | `rm -rf .hugo_build.log resource public ...` |
| `npm run update` | Update Hugo modules | `hugo mod get -u && hugo mod tidy ...` |
| `npm run create` | Create new content | `hugo new content` |

### Manual Commands
*   **Run Server:** `hugo server`
*   **Build:** `hugo --gc --minify`

## Configuration
Configuration is organized in the `config/` directory. 
*   Global settings are in `config/_default/`.
*   Environment-specific overrides are in `config/development/` and `config/production/`.

## Deployment
Deployment is automated using GitHub Actions (`.github/workflows/deploy.yml`).
*   **Trigger:** Pushes to the `main` branch.
*   **Process:**
    1.  Checks out code (with submodules).
    2.  Sets up Go and Hugo.
    3.  Builds the site (`hugo --gc --minify`).
    4.  Deploys to Firebase Hosting.

## Theme & Modules
The site uses `github.com/hugo-fixit/fixit-bundle` which includes:
*   Core FixIt theme
*   Various components (Flyfish animation, DevTools, etc.)
See `go.mod` for the full list of required modules.
