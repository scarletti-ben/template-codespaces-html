# Quick Start
1. Clone the repository, see [Cloning](#cloning-this-template)
2. Run `npm install` to install all dependencies in `package.json`
3. Open the server via one of the methods below
    - **Live Server Extension**: Click the button in the bottom right that says "Go Live" or right-click `index.html` and choose "Open with Live Server" and then navigate to `http://localhost:5500`
    - **HTTP Server**: Run `npm start` or `npx http-server docs -p 8080` in terminal to serve the `docs` directory, or `npx http-server -p 8080` for the current directory, and then navigate to `http://localhost:8080`
3. Make changes and you should see them update via the `localhost` address

If there is an issue with setup, the best method is to install `http-server` manually via `npm` using `npm install -g http-server`, and then you can run `npx http-server docs -p 8080` or `npx http-server -p 8080` as above.

> [!NOTE]
> Using `npx` in `npx http-server -p 8080` is the simplest way to avoid situations where `http-server` is only accessible locally rather than globally. `Node Package Execute` / `npx` should search locally, then globally, and then 

# Cloning this Template
As this repository is a template repository it has a button on the right of its page that says "use this template", which gives two options, "create a new repository" and "open in a codespace".

Choosing the first option will allow you to clone the repository locally, and the files within the `.devcontainer/` and `.vscode/` directories will influence the project configuration and extensions that are installed in your local environment.

Choosing the second option is much the same as the first, except that it will create a cloud-based development environment within your web browser that is hosted by `GitHub` and runs an instance of `VSCode` online, with its own `virtual machine`. The files within the `.devcontainer/` and `.vscode/` directories will also influence the project configuration and extensions that are installed within this environment. The `Codespace` you create from the template is not connected to the template itself once cloned. The `Codespace` that is created is esentially a temporary repository, linked to a `virtual machine`, which is deleted after 30 days of inactivity. However, `Codespaces` you wish to keep open can be "pinned" to remain open forever. Managing your `Codespaces` is done [here](https://github.com/codespaces).

> [!NOTE]
> Normally when you open a repository in a `codespace` it will open that exact repository, and changes / pushes will affect the repository. When using the "use this template" button, the `codespace` that is created is a temporary repository, and does not affect the original.

# Repository Structure
The general structure of the repository can be found below, it may not be exact but should give an idea.
```text
template-codespaces-html/
  ├─ .devcontainer/
  │   └─ devcontainer.json
  │
  ├─ .vscode/
  │   ├─ extensions.json
  │   └─ settings.json
  │
  ├─ docs/
  │   ├─ index.html
  │   ├─ script.js
  │   └─ style.css
  │
  ├─ .gitignore
  ├─ package.json
  └─ README.md
```

## `package.json`
Specifies dependencies for the project, you can install them via `npm install` in the directory that contains `package.json`. These dependencies will be installed locally, which means that you will need to use the `npx` prefix in order to run them. The "scripts" section of `package.json` allows to to specify commands that can be called via `npm {command}`. In this project `npm run start` will start a server on `port 8080`, just make sure that `npm install` has been called first.

## `.devcontainer/`
Contains configuration for `GitHub Codespaces` and `VSCode Dev Containers`

### `devcontainer.json`
- Defines container image via `"image"`
    - Currently uses `Node.js 18`
- Defines automatically installed extensions via `customizations/vscode/extensions`
    - Automatically installs `ritwickdey.LiveServer`
- Automatically forwards ports for use as local development server
    - Automatically forwards `port 5500` which is the default for `LiveServer`

## `.vscode/`
Contains project/workspace-specific `VSCode` settings that take precedence over current settings and work when the project is cloned locally or within `GitHub Codespaces`

### `extensions.json`
- Recommends extensions to install
    - Shows a popup when opening the project

### `settings.json`
- Configuration for the project / workspace and its extensions
    - Currently ensures `LiveServer` uses `port 5500` which matches the forwarded port specified in `devcontainer.json`
- Settings apply to this workspace only, not your global `VSCode` settings

## `docs/`
This folder contains all of the files for the site itself. The structure of this folder can be manipulated as needed, as long as an `HTML` file is accessed via `localhost`, and it has the correct paths to the files it is looking to access, eg. `script.js` / `style.css`

> [!NOTE]
> In `.devcontainer.json`, the line `"forwardPorts": [5500]` is not about the `Live Server` extension settings, but about telling `Codespaces` or `VSCode` to forward that port so the browser can access it, and `port 5500` is the default port for `Live Server`. Just to make sure, `.vscode/settings.json` manually configures `Live Server` to use `port 5500`

# Miscellaneous

## Project Information
As this is for quick development and testing, the template files will be a little more dense, simply to reduce the number of steps needed to do certain tasks. One example of this would be the file `style.css` which is considerably longer than my usual testing stylesheet, but aims to offer colour presets, and other features, in order to speed up development.

## Other
- Does not make use of a `Dockerfile`
- `VSCode` will prompt you to open the project in a container if it detects the `.devcontainer` folder
- Under the green `Code` button on `GitHub` you can see all `codespaces` that are linked to a given repository, and turn them into real repositories if you want
- Opening this repository as a `codespace` is different from clicking the button "use this template" and selecting "open in a codesapce" as it will open the exact repository, not a clone

## Issues

> [!WARNING]
> There is an issue with the current implementation of the `postCreateCommand` and `postStartCommand`. It was intended to install `http-server`, as an alternative to `LiveServer`. But this is now best done via `npm install http-server` or simply `npm install` which will use `package.json` for install information

# Repository Metadata

```yaml
---
metadata:
  author: "Ben Scarletti"
  date-created: "2025-06-12"
  date-modified: "2025-06-12"
  description: "Template for web development with vanilla HTML / CSS / JavaScript using GitHub Codespaces"
  tags: [
    "dev", "webdev", "programming", "coding", "html", "css", "javascript", "github", "codespaces", "template"
  ]
---
```