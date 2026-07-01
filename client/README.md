# PHP Codeigniter 3.X Intellisense

Lightweight IntelliSense for CodeIgniter 3 projects in VS Code.

This extension is designed for CodeIgniter 3.x projects. It does not support CodeIgniter 4.x.

The extension starts when you open a PHP file in a workspace that contains a CodeIgniter `system` folder. It parses your configured application folders and provides completions, symbols, hover information, and navigation for common CodeIgniter patterns.

## Features

### Code Completion

- Completes models, libraries, and selected CodeIgniter system classes.
- Supports `$this->`, `$CI->`, and `$this->CI->db` style access.
- Supports method chaining for the `db` class.
- Completes constants and static variables after `ClassName::`.
- Supports variables declared in models, such as `$this->mymodel->some_variable`.
- Refreshes model discovery with the `CI: refresh Model` command.

Library files are parsed when you open a file that loads them, such as:

```php
$this->load->library('foo');
```

### Document Symbols

Use VS Code document symbols to list methods in the current PHP file. If another PHP extension already provides symbols and you see duplicates, set `CI.ignoreSymbols` to `true`.

### Go To Definition

Go to definitions for models, libraries, methods, constants, and linked view files.

View-file navigation works for patterns such as:

```php
$this->load->view('path');
```

### Hover

Hover over supported methods to see parsed documentation.

## Requirements

- VS Code `1.90.0` or newer.
- A CodeIgniter 3 workspace with a `system` folder.
- PHP files opened with VS Code's PHP language mode.

## Extension Settings

- `CI.ignoreSymbols`: Disable this extension's document symbols when another PHP extension already provides them.
- `CI.model`: Auto-loaded models.
- `CI.library`: Auto-loaded libraries.
- `CI.other`: Extra PHP files to parse, such as `system/core/Common.php`.
- `CI.system`: Path to the CodeIgniter `system` folder.
- `CI.app`: Path to the CodeIgniter `application` folder.
- `CI.viewFilesFormat`: View file extension, such as `php`, `tpl`, or `twig`.

<!--
## Build and Install Locally (if needed)

From the repository root:

```bash
pnpm install --no-frozen-lockfile
pnpm run compile
```

Package the extension as a VSIX:

```bash
cd client
pnpm dlx @vscode/vsce package --no-dependencies
```

Install the generated VSIX into VS Code:

```bash
code --install-extension php-ci3x-intellisense-0.1.0.vsix --force
```

Reload VS Code after installing. To uninstall it later:

```bash
code --uninstall-extension code2business.php-ci3x-intellisense
```
-->

## Known Limitations

- The parser is based on regular expressions, so unusual PHP structure may not be recognized.
- Multiple classes in one file may not work reliably.
- If a library and model share the same name, the model may take precedence.
- For duplicate symbols with PHP IntelliSense or Intelephense, set `CI.ignoreSymbols` to `true`.

## Attribution

This extension is based on the original `PHP intellisense for codeigniter` VS Code extension by Small, originally published at [smallp/vscode-ci](https://github.com/smallp/vscode-ci).

This version modernizes the build and runtime dependencies for newer VS Code versions while preserving the original CodeIgniter 3 language features.

## License

MIT
