As this is for quick development and testing, the template files will be a little more dense, simply to reduce the number of steps needed to do certain tasks. One example of this would be the file `style.css` which is considerably longer than my usual testing stylesheet, but aims to offer colour presets, and other features, in order to speed up development.

# The `.vscode` Folder
# The `.devcontainer` Folder

# Miscellaneous
- Does not make use of a `Dockerfile`
- `VSCode` will prompt you to open the project in a container if it detects the `.devcontainer` folder
- Both `.vscode` and `.devcontainer` folders are read in a web-based `codespace`
  - In `.devcontainer.json`, "forwardPorts": [5500] is not about Live Server settings, but about telling Codespaces or `VSCode` to forward that container port to your local/machine UI so the browser can access it. `.vscode/settings.json` configures `Live Server` to use port 5500
- Remember to change settings to make repository a template
- Use this template, open in a codespace

# Repository Structure
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
  └─ README.md
```




# Repository Metadata
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