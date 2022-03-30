---
layout: ~/layouts/MainLayout.astro
title: TypeScript
description: Using TypeScript in Astro.
---
Astro includes built-in support for TypeScript (`*.ts`) files in your project. 

TypeScript adds additional syntax to JavaScript, helping you describe the shape of objects and functions in your code and catch errors in your editor.

> 💡 Don't forget to [configure your editor](/en/editor-setup) with the [Astro VS Code Extension](https://marketplace.visualstudio.com/items?itemName=astro-build.astro-vscode) for TypeScript Diagnostics and more!

## `tsconfig.json`

Each [Astro starter template](https://github.com/withastro/astro/tree/main/examples) includes a `tsconfig.json` file at project the root. This file specifies the compiler options required to compile the project.

```json
{
  "compilerOptions": {
    "moduleResolution": "node"
  }
}
```

## Aliases

You can add import aliases to create shortcuts for your imports.

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@components/*": ["src/components/*"],
      "@layouts/*": ["src/layouts/*"]
    }
  }
}
```

## Client Types

You can add `vite/client` to `compilerOptions.types` of your `tsconfig`:

```json
{
  "compilerOptions": {
    "types": ["vite/client"]
  }
}
```

This will provide the following type shims:

- [Asset imports](/en/guides/imports) (e.g. importing an `.svg` file)
- Types for the Vite-injected [env variables](/en/guides/environment-variables) on `import[dot]meta[dot]env
- Types for the HMR API on import[dot]meta[dot]hot



## Including/Excluding Files

Choose file paths and types to include or exclude.

```json
{
  "compilerOptions": {}
  "include": ["src/**/*.d.ts", "src/**/*.js", "src/**/*.ts"],
  "exclude": ["node_modules"]
}
```


Here are some other things you might want to configure...

📚 Read more about [`.ts` file imports](/en/guides/imports#typescript) in Astro.
📚 Read more about [TypeScript Configuration](https://www.typescriptlang.org/tsconfig)