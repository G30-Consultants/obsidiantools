# obsidian_tools 🪨⚒️
**obsidian_tools** is a Python package for getting structured metadata about your [Obsidian.md notes](https://obsidian.md/) and analysing your vault.  Complement your Obsidian workflows by getting metrics and detail about all your notes in one place through the widely-used Python data stack.

It's incredibly easy to explore structured data on your vault through this fluent interface.  This is all you need to generate a `vault` object that stores the key data:

```python
import obsidian_tools.api as otools

vault = otools.Vault(<VAULT_DIRECTORY>).connect()
```

As this package relies upon note (file)names, it is only recommended for use on vaults where wikilinks are not formatted as paths and where note names are unique.  This should cover the vast majority of vaults that people create.

## Key features
This is how **`obsidian_tools`** can complement your workflows for note-taking:
- **Access a `networkx` graph of your vault** (`vault.graph`)
    - NetworkX is the main Python library for network analysis, enabling sophisticated analyses of your vault.
    - NetworkX also supports the ability to export your graph to other data formats.
- **Retrieve detail about your notes' links as built-in Python types and Pandas objects**
    - The various types of links:
        - Wikilinks (incl. header links, links with alt text)
        - Backlinks
        - Markdown links
    - You can access all the links in one place, or you can load them for an individual note:
        - e.g. `vault.backlinks_index` for all backlinks in the vault
        - e.g. `vault.get_backlinks(<NOTE>)` for the backlinks of an individual note

There are other API features that try to mirror the Obsidian.md app, for your convenience when working with Python, but they are no substitute for the interactivity of the app!

The text from vault notes goes through this process: markdown → HTML → ASCII plaintext.  The functions for text processing are in the `md_utils` module so they can be used to get text, e.g. for use in NLP analysis.

## Installation ⏲️
``pip install obsidian_tools``

Developed for Python 3.9 but may still work on lower versions.

## Dependencies 🖇️
- markdown
- html2text
- pandas
- networkx

## Licence ⚖️
Modified BSD (3-clause)
