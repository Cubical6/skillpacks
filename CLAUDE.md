# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with the Axiom System Archaeologist plugin.

## Repository Overview

This is the **Axiom System Archaeologist** - a Claude Code plugin for deep architectural analysis of existing codebases through autonomous subagent-driven exploration.

**Purpose**: Systematically analyze codebases to generate C4 diagrams, subsystem catalogs, and architecture documentation

## Plugin Structure

```plaintext
skillpacks/
├── .claude/
│   └── commands/
│       └── system-archaeologist.md    # Slash command for easy invocation
├── plugins/
│   └── axiom-system-archaeologist/
│       ├── .claude-plugin/
│       │   └── plugin.json            # Plugin metadata
│       └── skills/
│           └── using-system-archaeologist/
│               ├── SKILL.md           # Router skill (main entry point)
│               ├── analyzing-unknown-codebases.md
│               ├── generating-architecture-diagrams.md
│               ├── documenting-system-architecture.md
│               └── validating-architecture-analysis.md
```

## Skills Overview

### 1. using-system-archaeologist (Router)
**Main entry point** - Coordinates subagent-driven codebase analysis with mandatory workspace structure and validation gates.

**Key Features:**
- Mandatory workspace creation: `docs/arch-analysis-YYYY-MM-DD-HHMM/`
- Coordination plan documentation
- Quality validation gates
- Pressure-resistant workflow

### 2. analyzing-unknown-codebases
Systematic exploration strategies for unfamiliar codebases of any size.

### 3. generating-architecture-diagrams
C4 diagram generation (Context, Container, Component levels) in Mermaid format.

### 4. documenting-system-architecture
Stakeholder-ready architecture documentation with ADRs.

### 5. validating-architecture-analysis
Quality gates and completeness checklists.

## Installation & Usage

### Install Plugin

```bash
# From this repository root
/plugin add .
```

### Use Plugin

**Via Slash Command (Recommended):**
```bash
/system-archaeologist
```

**Via Direct Skill Invocation:**
```plaintext
I'm using axiom/system-archaeologist/analyzing-unknown-codebases
```

## Working With This Repository

### Testing Changes

When modifying skills:

1. Edit skill files in `plugins/axiom-system-archaeologist/skills/using-system-archaeologist/`
2. If plugin is installed, changes take effect immediately
3. Test by invoking the slash command: `/system-archaeologist`

### Skill File Format

Each skill follows this structure:

```markdown
---
name: skill-name
description: Brief description for skill discovery
mode: true  # Optional - indicates router skill
---

# Skill Title

[Skill content with examples, patterns, anti-patterns...]
```

## Key Design Principles

### Mandatory Workflow Structure
- **Workspace creation is non-negotiable** - prevents file scatter
- Coordination plan must be written before analysis begins
- Validation gates ensure quality output

### Subagent Coordination
- Uses Task tool with subagent_type=Explore for thorough analysis
- Parallel subagents for faster results on large codebases
- Sequential subagents for smaller codebases or dependency analysis
- Handoffs via shared documents in workspace

### Pressure Resistance
- Skills explicitly warn against common shortcuts under pressure
- Validation checklists prevent incomplete analysis
- Quality gates are mandatory, not optional

### Professional Output
- C4 diagrams in Mermaid format
- Subsystem catalogs with dependency tracking
- Architecture Decision Records (ADRs)
- Stakeholder-ready documentation

## Common Operations

### Test the Plugin

```bash
# Install plugin
/plugin add .

# Test slash command
/system-archaeologist

# Claude will guide through analysis workflow
```

### Verify Plugin Structure

```bash
# Check plugin metadata
cat plugins/axiom-system-archaeologist/.claude-plugin/plugin.json

# List all skills
ls plugins/axiom-system-archaeologist/skills/using-system-archaeologist/

# Verify slash command exists
ls .claude/commands/system-archaeologist.md
```

### Update a Skill

```bash
# Edit skill content
vim plugins/axiom-system-archaeologist/skills/using-system-archaeologist/SKILL.md

# Changes take effect immediately if plugin is installed
# Test with: /system-archaeologist
```

## Git Workflow

### Branches

- `main` - Production-ready code only
- Feature branches for improvements

### Commits

Use conventional commits:

- `feat:` - New features or skills
- `fix:` - Skill corrections or improvements
- `docs:` - Documentation updates
- `chore:` - Repository maintenance

## Important Notes

### Plugin Version

Current version: **1.0.2** (see `plugins/axiom-system-archaeologist/.claude-plugin/plugin.json`)

### Skill Characteristics

- **Router skill** (`using-system-archaeologist/SKILL.md`) coordinates analysis workflow
- **4 specialist skills** handle specific analysis tasks
- All skills validated through systematic testing
- Production-ready, expert-level guidance

### License

CC BY-SA 4.0 (Creative Commons Attribution-ShareAlike 4.0 International)

**Important**: The "Axiom" faction name from Altered TCG is NOT covered by this license - see LICENSE_ADDENDUM.md

## Quick Reference

```bash
# Install plugin
/plugin add .

# Use via slash command
/system-archaeologist

# Check plugin version
grep version plugins/axiom-system-archaeologist/.claude-plugin/plugin.json

# List skills
find plugins/axiom-system-archaeologist/skills -name "*.md" -type f
```

## Workflow Example

When a user requests codebase analysis:

1. Invoke via `/system-archaeologist`
2. Router skill loads with mandatory workflow
3. Workspace created: `docs/arch-analysis-YYYY-MM-DD-HHMM/`
4. Coordination plan written: `00-coordination.md`
5. Subagents launched for exploration
6. Documentation generated: subsystem catalogs, C4 diagrams
7. Validation gates ensure completeness
8. Deliverables ready for stakeholders

## Anti-Patterns to Avoid

❌ **Skipping workspace creation** - "I'll just create files in project root"
- Results in scattered files, lost context, incomplete analysis

❌ **Rushing validation** - "I'll skip the checklist, looks good enough"
- Results in missing components, incomplete diagrams, stakeholder questions

❌ **Direct file exploration instead of subagents** - "I'll just read a few files"
- Results in sampling bias, missed subsystems, inaccurate architecture

✅ **Correct approach**: Follow mandatory workflow, use subagents, validate output
