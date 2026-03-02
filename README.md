# Divengine PyVault

[![PyPI version](https://badge.fury.io/py/divengine-pyvault.svg?nocache=1)](https://pypi.org/project/divengine-pyvault/)
[![Downloads](https://static.pepy.tech/badge/divengine-pyvault/week)](https://pepy.tech/project/divengine-pyvault)
[![Downloads](https://static.pepy.tech/badge/divengine-pyvault)](https://pepy.tech/project/divengine-pyvault)
[![MIT licensed](https://img.shields.io/badge/license-MIT-green.svg)](https://raw.githubusercontent.com/divengine/pyvault/main/LICENSE)

PyVault is a Python documentation generator that transforms a Python codebase
into an Obsidian vault. It parses the AST, extracts modules, classes, functions,
imports, and call relationships, and writes a navigable knowledge graph using
Obsidian wiki links.

![PyVault Screenshot](https://github.com/user-attachments/assets/38d9f3dd-e001-42e2-b69f-d33bfdae7343)

---

## Features

- Parses Python projects with the built-in `ast` module (no runtime execution).
- Extracts modules, classes, functions, methods, and attributes.
- Tracks inheritance, imports, and `uses` relationships between elements.
- Generates Markdown notes with Obsidian-style `[[wiki links]]`.
- Preserves the original folder structure.
- Emits tags like `#module`, `#class`, `#function`, `#method`, and `#imports`.

![Obsidian Graph Example](https://github.com/user-attachments/assets/3577390b-f482-4854-9304-6e6aec358ef4)

## Requirements

- Python 3.9 or higher

## Install

```bash
pip install divengine-pyvault
```

Upgrade when needed:

```bash
pip install --upgrade divengine-pyvault
```

## Usage

```bash
pyvault /path/to/project /path/to/vault_output
```

From source:

```bash
git clone https://github.com/divengine/pyvault.git
cd pyvault
python divengine/pyvault/core.py /path/to/project /path/to/vault_output
```

## Output structure

Example layout:

```text
vault_output/
  module_a.md
  package_b/
    imports.md
    MyClass/
      method_one.md
      method_two.md
```

Each note includes:

- Source file location
- Docstrings (if any)
- Arguments and properties
- Relationships (uses, inheritance, etc.)

## Obsidian workflow

1) Install Obsidian: https://obsidian.md/download  
2) Open the generated output folder as a vault.  
3) Use Graph view to explore module and class relationships.

Recommended plugins:

- Graph Analysis
- Backlinks / Outgoing
- Dataview (optional)

## Tips

- Add docstrings to enrich the generated notes.
- Use Obsidian tags to filter `#class`, `#function`, and `#module` entries.
- Keep your output vault inside a separate folder to avoid mixing with code.

## License

MIT License. Copyright (c) Divengine Software Solutions.
