# Divengine Python Vault

[![PyPI version](https://badge.fury.io/py/divengine-pyvault.svg?nocache=1)](https://pypi.org/project/divengine-pyvault/) [![Downloads](https://static.pepy.tech/badge/divengine-pyvault/week)](https://pepy.tech/project/divengine-pyvault) [![Downloads](https://static.pepy.tech/badge/divengine-pyvault)](https://pepy.tech/project/divengine-pyvault) [![MIT licensed](https://img.shields.io/badge/license-MIT-green.svg)](https://raw.githubusercontent.com/gabfl/vault/main/LICENSE)

**pyvault** is a Python-powered documentation generator that transforms any Python project into a structured [Obsidian](https://obsidian.md) vault.  

It extracts all classes, functions, and modules, maps their relationships, and builds a fully browseable knowledge graph of the codebase.

![PyVault Screenshot](https://github.com/user-attachments/assets/38d9f3dd-e001-42e2-b69f-d33bfdae7343)

---

## Features

- Parses your Python project using Python’s `ast` module
- Extracts:
  - 📦 Modules (`.py` files)
  - 🧩 Functions and methods
  - 🏷️ Classes (including inheritance, methods, and properties)
  - 🔗 Function calls between elements (`uses`)
- Generates Markdown files for all entities, with proper nesting
- Preserves the original folder structure
- Uses Obsidian-style `[[wiki links]]` to interconnect everything

![Obsidian Graph Example](https://github.com/user-attachments/assets/3577390b-f482-4854-9304-6e6aec358ef4)

## Usage

### Option 1: Clone and run

```bash
git clone https://github.com/divengine/pyvault.git
cd pyvault
python divengine/pyvault/core.py /your_project/ /vault_output/
```

### Option 2: Install via pip

```bash
pip install divengine-pyvault
pyvault /your_project/ /vault_output/
```

To make sure you always get the latest version, use:

```bash
pip install --upgrade divengine-pyvault
```

### Output Example

After running, the tool generates an Obsidian vault like this:

```bash
vault_output/
├── module_a.md
├── module_b/
│   ├── imports.md
│   └── MyClass/
│       ├── method_one.md
│       └── method_two.md
```

Each .md file includes:

- File or object name
- Location in the source project
- Extracted arguments
- Docstrings (if any)
- Relationships (uses, inheritance, etc.)

### License

MIT License © Divengine Software Solutions
