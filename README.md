# Finhay Claude Plugins

Official plugin marketplace for Finhay's internal Claude Code extensions. This repository provides shared plugins to help the team maintain consistency and boost productivity when working with Claude Code.

## Available Plugins

| Plugin | Description | Command |
|--------|-------------|---------|
| `finhay-brand-guidelines` | Finhay brand identity system including colors, typography, logos, voice, and design guidelines | `/brand-guidelines` |

## Installation

### 1. Add the Marketplace

```
/plugin marketplace add finhay-pro/finhay-claude-plugins
```

### 2. Install a Plugin

```
/plugin install <plugin-name>@finhay-plugins
```

For example:
```
/plugin install finhay-brand-guidelines@finhay-plugins
```

### 3. Use the Plugin

Once installed, use the plugin's command:
```
/brand-guidelines
```

## Updating Plugins

To get the latest updates:

```
/plugin marketplace update finhay-plugins
```

## Contributing

We welcome contributions from the team. Here's how to add a new plugin:

### Plugin Structure

Each plugin should follow this structure:

```
plugins/
└── your-plugin-name/
    ├── .claude-plugin/
    │   └── plugin.json        # Plugin manifest (required)
    ├── commands/              # Slash commands
    │   └── your-command.md
    ├── agents/                # Custom agents (optional)
    ├── hooks/                 # Lifecycle hooks (optional)
    └── ... other files
```

### Step 1: Create the Plugin Directory

```bash
mkdir -p plugins/your-plugin-name/.claude-plugin
mkdir -p plugins/your-plugin-name/commands
```

### Step 2: Create the Plugin Manifest

Create `plugins/your-plugin-name/.claude-plugin/plugin.json`:

```json
{
  "name": "your-plugin-name",
  "description": "Brief description of what your plugin does",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "email": "your.email@finhay.com.vn"
  },
  "keywords": ["relevant", "keywords"],
  "commands": ["./commands"]
}
```

### Step 3: Create Commands

Create markdown files in the `commands/` directory. Each file becomes a slash command.

Example `commands/your-command.md`:

```markdown
---
name: your-command
description: What this command does
---

# Your Command

Instructions for Claude when this command is invoked.

## What to do

- Step 1
- Step 2
- Step 3
```

The filename (without `.md`) becomes the command name: `/your-command`

### Step 4: Register in Marketplace

Add your plugin to `.claude-plugin/marketplace.json`:

```json
{
  "plugins": [
    // ... existing plugins
    {
      "name": "your-plugin-name",
      "source": "./plugins/your-plugin-name",
      "description": "Brief description of your plugin",
      "version": "1.0.0",
      "author": {
        "name": "Your Name"
      },
      "keywords": ["relevant", "keywords"],
      "category": "your-category"
    }
  ]
}
```

### Step 5: Submit a Pull Request

1. Create a new branch:
   ```bash
   git checkout -b feat/add-your-plugin-name
   ```

2. Commit your changes:
   ```bash
   git add .
   git commit -m "feat(plugins): add your-plugin-name plugin"
   ```

3. Push and create a PR:
   ```bash
   git push -u origin feat/add-your-plugin-name
   ```

### Plugin Guidelines

- **Naming**: Use kebab-case for plugin and command names
- **Documentation**: Include clear descriptions and usage examples
- **Testing**: Test your plugin locally before submitting
- **Versioning**: Use semantic versioning (MAJOR.MINOR.PATCH)
- **Assets**: Keep assets minimal and optimized

### Testing Locally

Before submitting, test your plugin:

```bash
# Add local marketplace
/plugin marketplace add ./path/to/finhay-claude-plugins

# Install your plugin
/plugin install your-plugin-name@finhay-plugins

# Test your command
/your-command
```

## Plugin Types Reference

### Commands
Slash commands that inject prompts or instructions into the conversation.

### Agents
Custom agents with specific capabilities and tools access.

### Hooks
Lifecycle hooks that run at specific events (e.g., after file writes).

### MCP Servers
Model Context Protocol servers for external integrations.

For detailed documentation, see [Claude Code Plugins Documentation](https://docs.anthropic.com/en/docs/claude-code/plugins).

## Support

For questions or issues:
- Create an issue in this repository
- Contact the Tech team on Slack

## License

Internal use only. All rights reserved by Finhay Vietnam.
