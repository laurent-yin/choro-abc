# choro-abc

A collection of Choro themes notated using the ABC music notation.

## How abctools is used in this repository

This repository uses [`abctools`](https://github.com/laurent-yin/abctools) to automate the export of `.raw.abc` files (with configuration from `.abcconfig` files) into standard `.abc` files.

### Workflow

- **Source files:**  
  All original music notation files are stored as `.raw.abc` files in the `source/` directory.  
  Each folder may contain a `.abcconfig` file with ABC directives (such as `%%pagewidth`), which are applied to all `.raw.abc` files in that folder and its subfolders.  
  Directives in child folders override those in parent folders, allowing for hierarchical configuration.

- **Exporting:**  
  The build process uses the `abctools export` command to generate `.abc` files from the `.raw.abc` and `.abcconfig` files.  
  The output `.abc` files are written to the `abc/` directory, preserving the folder structure of `source/`.

### Usage

To export all `.raw.abc` files to `.abc` files, run:

```sh
npm run build
```

This runs the following command (see `package.json`):

```sh
abctools export source/ abc/
```

- `source/`: Directory containing `.raw.abc` and `.abcconfig` files.
- `abc/`: Output directory for the generated `.abc` files.

### Editing and Visualization

You can use the [vscode-abc-music-editor](https://marketplace.visualstudio.com/items?itemName=laurent-yin.abc-to-svg) extension in VS Code to edit, visualize, and play the Raw ABC files or the ABC files directly. This extension also supports `.abcconfig` files.

---

For more details on `abctools`, see the [abctools documentation](https://github.com/laurent-yin/abctools).