# biome minimalist config

a minimalist Biome configuration i use in my projects with rather strict linting and formatting rules, as an alternative to ESLint and Prettier.

## installation

```bash
# using bun
bun add --dev --exact @c14l/biome-config @biomejs/biome
```

## usage

after installation, create a `biome.json` file in your project root and extend this configuration:

```json
{
  "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
  "extends": ["@c14l/biome-config"]
}
```

you can also override specific settings:

```json
{
  "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
  "extends": ["@c14l/biome-config"],
  "formatter": {
    "indentStyle": "tab"
  }
}
```

## editor integration

### VS Code / Cursor

for the best experience in VS Code or Cursor, add these settings to your `settings.json`:

```json
{
  "[javascript]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[typescript]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[javascriptreact]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[json]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "typescript.tsdk": "node_modules/typescript/lib",
  "editor.codeActionsOnSave": {
    "source.action.useSortedAttributes.biome": "explicit", // sorts imports on save
    "source.action.useSortedKeys.biome": "explicit", // sorts object keys on save
    "source.fixAll.biome": "explicit", // fixes all errors on save
    "source.organizeImports.biome": "explicit" // sorts imports on save
  }
}
```

make sure to install the [Biome extension](https://marketplace.cursorapi.com/items?itemName=biomejs.biome) for VS Code.

you can also enable format on save with:

```json
{
  "editor.formatOnSave": true
}
```
