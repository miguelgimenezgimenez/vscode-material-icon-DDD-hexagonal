# DDD HexaDog Icons

A dog-inspired icon theme for Visual Studio Code, tailored for Domain-Driven Design and Hexagonal Architecture projects.

DDD HexaDog Icons is based on the Material Icon Theme ecosystem and keeps the same powerful customization model while adding a playful visual identity for layered, ports-and-adapters style codebases.

## Features

- Dog-inspired icon style for files and folders
- Works with DDD and Hexagonal Architecture naming conventions
- Configurable file, folder, and root folder colors
- Folder theme switching (specific, classic, none)
- Opacity and saturation controls, including grayscale mode
- Custom associations for files, folders, root folders, and language ids
- Custom icon clones for files, folders, and languages
- Optional icon packs for framework-focused variants

## Install

1. Open Extensions in VS Code.
2. Search for DDD HexaDog Icons.
3. Install and activate the icon theme.

- [DDD HexaDog Icons on Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=miguelgimenez.hexadog-icons)

## Activate Theme

Run this command from the Command Palette:

- Material Icons: Activate Icon Theme

## Commands

The extension contributes these commands:

- Material Icons: Activate Icon Theme
- Material Icons: Configure Icon Packs
- Material Icons: Change Folder Theme
- Material Icons: Change Folder Color
- Material Icons: Change Root Folder Color
- Material Icons: Change File Color
- Material Icons: Restore Default Configuration
- Material Icons: Toggle Explorer Arrows
- Material Icons: Change Opacity
- Material Icons: Toggle Grayscale
- Material Icons: Change Saturation

## Configuration

You can configure the theme using VS Code settings.

```json
{
  "material-icon-theme.activeIconPack": "none",
  "material-icon-theme.folders.theme": "specific",
  "material-icon-theme.folders.color": "#ef5350",
  "material-icon-theme.rootFolders.color": "#ef5350",
  "material-icon-theme.files.color": "#42a5f5",
  "material-icon-theme.opacity": 1,
  "material-icon-theme.saturation": 1,
  "material-icon-theme.hidesExplorerArrows": false,
  "material-icon-theme.files.associations": {
    "*.aggregate.ts": "class",
    "*.value-object.ts": "class"
  },
  "material-icon-theme.folders.associations": {
    "domain": "rules",
    "application": "services",
    "infrastructure": "tools",
    "adapters": "plugin"
  },
  "material-icon-theme.rootFolders.associations": {
    "backend": "server"
  }
}
```

### Custom Clones

You can clone existing icons and recolor them without creating new SVG files.

```json
{
  "material-icon-theme.files.customClones": [
    {
      "name": "ddd-aggregate",
      "base": "class",
      "color": "blue-400",
      "fileNames": ["aggregate.ts"],
      "fileExtensions": ["aggregate.ts"]
    }
  ],
  "material-icon-theme.folders.customClones": [
    {
      "name": "hexa-adapter-folder",
      "base": "plugin",
      "color": "light-green-500",
      "folderNames": ["adapters"],
      "rootFolderNames": ["services"]
    }
  ]
}
```

## Local Development

This project uses Bun and TypeScript.

### Prerequisites

- Bun
- Node.js (for tooling compatibility in some environments)

### Setup

```bash
bun install
```

### Build

```bash
bun run build
```

### Test

```bash
bun run test
```

### Lint

```bash
bun run lint
```

### Useful Scripts

- `bun run watch`: Rebuild in watch mode
- `bun run verify`: Enforce module dependency rules (Sheriff)
- `bun run check`: Run icon checks
- `bun run check-colors`: Validate icon colors
- `bun run preview`: Generate icon previews
- `bun run generateJson`: Generate icon manifest
- `bun run generateClones`: Generate clone definitions

## Architecture

The codebase follows a clear separation between core icon generation logic and VS Code extension runtime logic.

```text
src/
  core/       icon definitions, manifest generation, translation logic
  extension/  VS Code integration, commands, configuration interaction
  module/     npm-facing exports for programmatic manifest generation
  scripts/    build and maintenance automation
```

For architecture rules and boundaries, see:

- [Architecture document](./src/architecture.md)

## NPM Module

This repository also publishes a module entry point so icon manifests can be generated programmatically.

- [Module documentation](./src/module/README.md)

## Contributing

Contributions are welcome.

Before opening a pull request:

- Read the contribution guide
- Follow the Material Design color palette constraints
- Keep icons pixel-perfect on a 16x16 grid
- Prefer cloning existing icons when only color or associations change

See:

- [Contributing guide](./CONTRIBUTING.md)

## Credits

- Material Design icon ecosystem and community resources
- Original Material Icon Theme maintainers and contributors

## License

MIT
