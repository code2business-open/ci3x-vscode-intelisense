# PHP Codeigniter 3.X Intellisense

VS Code extension that adds lightweight IntelliSense support for CodeIgniter 3 projects.

This repository contains the modernized source for the extension. The packaged extension lives in the `client` workspace, and the language server lives in the `server` workspace.

## What It Does

- Completes CodeIgniter models, libraries, and selected system classes.
- Supports `$this->`, `$CI->`, and common CodeIgniter chaining patterns.
- Provides document symbols, hover text, go to definition, and view-file links.
- Activates for PHP files when the workspace contains a CodeIgniter `system` folder.

<!-- ## Build and Install Locally

From the repository root:

```bash
pnpm install --no-frozen-lockfile
pnpm run compile
cd client
pnpm dlx @vscode/vsce package --no-dependencies
code --install-extension php-ci3x-intellisense-0.1.0.vsix --force
```

Reload VS Code after installing. To uninstall it later:

```bash
code --uninstall-extension code2business.php-ci3x-intellisense
``` -->

## Attribution

This project is based on the original `PHP intellisense for codeigniter` VS Code extension by Small, originally published at [smallp/vscode-ci](https://github.com/smallp/vscode-ci).

This version modernizes the build and runtime dependencies for newer VS Code versions while preserving the original CodeIgniter 3 language features.

## License

MIT
