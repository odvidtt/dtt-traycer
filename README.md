# DTT Community Plugins - Claude Code Marketplace

A custom Claude Code Plugin Marketplace containing the `dtt-traycer` plugin for Spec-Driven Development.

## Overview

This marketplace provides the **dtt-traycer** plugin with a skill called `vertical-slices` that orchestrates a strict 6-phase Spec-Driven Development pipeline.

### 6-Phase Workflow

1. **🟢 Phase 1: Product Manager** - Clarify requirements and create Epic Brief
2. **🟡 Phase 2: UX/Product Designer** - Design user flows and core experiences
3. **🔵 Phase 3: Architect** - Design technical approach and data model
4. **🟣 Phase 4: Lead Engineer** - Break down into story-sized tickets
5. **🟠 Phase 5: Slicer** - Create razor-thin vertical slices with TDD
6. **🟢 Phase 6: Execution Engineer** - Build and test implementation slices

## Directory Structure

```
my-marketplace/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace configuration
├── plugins/
│   └── dtt-traycer/
│       ├── .claude-plugin/
│       │   └── plugin.json       # Plugin metadata
│       └── skills/
│           └── vertical-slices/
│               ├── SKILL.md      # Main orchestrator skill
│               └── prompts/      # Persona prompt files
│                   ├── prompt-pm.md
│                   ├── prompt-flows.md
│                   ├── prompt-architect.md
│                   ├── prompt-lead.md
│                   ├── prompt-slicer.md
│                   ├── elephant-carpaccio.md
│                   └── prompt-builder.md
└── README.md
```

## Installation in Claude Code

### Method 1: Local Path (Recommended for Development)

1. **Install the plugin in Claude Code:**
   ```bash
   claude plugins add /absolute/path/to/my-marketplace/plugins/dtt-traycer
   ```

2. **Verify installation:**
   ```bash
   claude plugins list
   ```

3. **Use the skill:**
   ```
   /dtt-traycer:vertical-slices TICKET-123 "Create a user authentication system"
   ```

### Method 2: GitHub Repository

1. **Push this repository to GitHub** (see commands below)
2. **Install directly from GitHub:**
   ```bash
   claude plugins add https://github.com/YOUR_USERNAME/dtt-traycer-marketplace/plugins/dtt-traycer
   ```

## Usage

Once installed, invoke the skill with:

```
/dtt-traycer:vertical-slices <ticket_number> <description>
```

**Example:**
```
/dtt-traycer:vertical-slices AUTH-001 "Implement OAuth2 authentication with Google and GitHub providers"
```

Claude will then guide you through the 6-phase workflow, creating documentation in `docs/tickets/<ticket_number>/`.

## Files Generated

The skill creates the following files in your project:

- `docs/tickets/<ticket_number>/1-epic-brief.md` - Product requirements (PM)
- `docs/tickets/<ticket_number>/2-core-flows.md` - User flows and UX design
- `docs/tickets/<ticket_number>/3-tech-plan.md` - Technical architecture
- `docs/tickets/<ticket_number>/4-ticket-breakdown.md` - Story-sized tickets
- `docs/tickets/<ticket_number>/5-vertical-slices.md` - Implementation slices with TDD
- `docs/tickets/<ticket_number>/6-implementation-tracker.md` - Build progress tracker

## Git Commands to Push to GitHub

### First Time Setup

```bash
# 1. Create a new repository on GitHub (via web interface)
#    Go to https://github.com/new and create "dtt-traycer-marketplace"

# 2. Add the remote URL
cd my-marketplace
git remote add origin https://github.com/YOUR_USERNAME/dtt-traycer-marketplace.git

# 3. Commit and push
git add .
git commit -m "Initial commit: DTT Traycer plugin marketplace"
git branch -M main
git push -u origin main
```

### After Making Changes

```bash
cd my-marketplace

# Check status
git status

# Stage changes
git add .

# Commit
git commit -m "Your descriptive commit message"

# Push
git push origin main
```

## Manual Configuration

### For Plugin Developers

To add more skills to the `dtt-traycer` plugin:

1. Create a new folder under `plugins/dtt-traycer/skills/<skill-name>/`
2. Add a `SKILL.md` file with proper frontmatter
3. Update `plugins/dtt-traycer/.claude-plugin/plugin.json` if needed
4. Test locally before pushing

### For Marketplace Admins

To add more plugins to this marketplace:

1. Create plugin folder: `plugins/<new-plugin>/`
2. Add required files (`.claude-plugin/plugin.json`, skills/)
3. Update `.claude-plugin/marketplace.json`:
   ```json
   {
     "plugins": [
       {
         "name": "dtt-traycer",
         "source": "./plugins/dtt-traycer",
         "description": "Traycer.ai spec-driven development orchestrator."
       },
       {
         "name": "new-plugin",
         "source": "./plugins/new-plugin",
         "description": "Description of new plugin."
       }
     ]
   }
   ```

## Updating the Plugin

After making changes to any skill files:

```bash
cd my-marketplace

# Reinstall in Claude Code (uninstall first, then reinstall)
claude plugins remove dtt-traycer
claude plugins add /absolute/path/to/my-marketplace/plugins/dtt-traycer
```

## Troubleshooting

### Plugin Not Found
- Ensure the path to the plugin folder is absolute
- Verify the `.claude-plugin/plugin.json` file exists and is valid JSON

### Skill Not Working
- Check that `SKILL.md` has proper frontmatter with `description`
- Verify all prompt files exist in the `prompts/` directory
- Ensure file permissions allow reading

### Claude Code Integration
- Restart Claude Code after installing plugins
- Run `claude plugins list` to verify installation
- Check Claude Code documentation for latest plugin API changes

## Development Workflow

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/dtt-traycer-marketplace.git
cd dtt-traycer-marketplace

# 2. Make changes to skill files
# Edit files in plugins/dtt-traycer/skills/vertical-slices/

# 3. Test locally
claude plugins add $(pwd)/plugins/dtt-traycer

# 4. Commit and push
git add .
git commit -m "Update: description of changes"
git push origin main
```

## License

MIT License - Feel free to use and modify for your own Claude Code plugins.

## Support

For issues or questions:
- Check the Claude Code documentation
- Review the skill files in `prompts/` for detailed persona instructions
- Examine the generated files in `docs/tickets/` for workflow examples
