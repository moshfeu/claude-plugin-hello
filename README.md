# claude-plugin-hello

A minimal Claude Code plugin example, distributed via **GitHub Packages** as a private marketplace.

## Structure

```
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest (name, version, description)
├── skills/
│   └── hello-world/
│       └── SKILL.md         # Skill definition (frontmatter + instructions)
├── marketplace.json          # Marketplace registry pointing to GitHub Packages
└── package.json              # npm package (scoped to GitHub Packages)
```

## How it works

1. **Plugin manifest** — `.claude-plugin/plugin.json` identifies the plugin to Claude Code.
2. **Skill discovery** — Claude Code auto-discovers any `skills/*/SKILL.md` file in the installed package.
3. **Marketplace** — `marketplace.json` is the registry file. Host it as a raw GitHub URL and users add it once.

## Publish to GitHub Packages

```bash
# Authenticate (once)
npm login --registry=https://npm.pkg.github.com

# Publish
npm publish
```

## Install via marketplace

```bash
# Add this marketplace (raw GitHub URL of marketplace.json)
claude marketplace add https://raw.githubusercontent.com/moshfeu/claude-plugin-hello/main/marketplace.json

# Install the plugin
claude marketplace install claude-plugin-hello
```

> **Note:** GitHub Packages requires a GitHub token for read access. Users need an `~/.npmrc` entry:
> ```
> //npm.pkg.github.com/:_authToken=<your-github-token>
> ```
> For a fully public/unauthenticated setup, publish to the public npm registry and change the `registry` field in `marketplace.json`.

## Use the skill

After installing, type `/hello <your name>` in Claude Code.
