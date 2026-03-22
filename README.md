# claude-plugin-hello

A minimal Claude Code plugin example, distributed **directly from GitHub** — no npm publish, no registry auth.

## Structure

```
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest (name, version, description)
├── skills/
│   └── hello-world/
│       └── SKILL.md         # Skill definition (frontmatter + instructions)
├── marketplace.json          # Marketplace registry — points to this GitHub repo
└── package.json              # npm package metadata (no publishConfig needed)
```

## How it works

1. **Plugin manifest** — `.claude-plugin/plugin.json` identifies the plugin to Claude Code.
2. **Skill discovery** — Claude Code auto-discovers any `skills/*/SKILL.md` in the installed package.
3. **Distribution** — `marketplace.json` uses `"package": "github:moshfeu/claude-plugin-hello"`, which tells npm to install directly from this repo. No registry, no publish step needed.

## Install via marketplace

```bash
# Add this marketplace (raw GitHub URL of marketplace.json)
claude marketplace add https://raw.githubusercontent.com/moshfeu/claude-plugin-hello/main/marketplace.json

# Install the plugin
claude marketplace install claude-plugin-hello
```

No tokens or authentication required — public GitHub repo = anyone can install.

## Publish a new version

Just push to GitHub. To pin to a specific commit or tag:

```json
"package": "github:moshfeu/claude-plugin-hello#v1.1.0"
```

## Use the skill

After installing, type `/hello <your name>` in Claude Code.
