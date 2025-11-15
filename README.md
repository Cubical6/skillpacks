# Axiom System Archaeologist

**Deep architectural analysis of existing codebases through autonomous subagent-driven exploration**

A Claude Code plugin that produces comprehensive architecture documentation, C4 diagrams, and subsystem catalogs for any codebase.

---

## What It Does

System Archaeologist coordinates autonomous subagents to systematically explore and document existing codebases, producing professional architecture documentation including:

- **C4 Diagrams** - Context, Container, and Component level architecture
- **Subsystem Catalogs** - Detailed component inventories with dependencies
- **Architecture Documentation** - Stakeholder-ready design documentation
- **Validation Gates** - Quality checks ensure complete, accurate analysis

---

## Installation

### Direct Installation

```bash
# Clone this repository
git clone https://github.com/Cubical6/skillpacks
cd skillpacks

# Install the plugin
/plugin add .
```

---

## Usage

### Start Analysis

Use the slash command to begin codebase analysis:

```bash
/system-archaeologist
```

Claude will guide you through:

1. **Workspace Creation** - Organized analysis directory structure
2. **Subagent Coordination** - Autonomous exploration agents
3. **Documentation Generation** - C4 diagrams and subsystem catalogs
4. **Validation** - Quality gates ensure completeness

### Direct Skill Invocation

You can also directly invoke specific skills:

```plaintext
I'm using axiom/system-archaeologist/analyzing-unknown-codebases
```

---

## Available Skills

This plugin includes 5 specialized skills:

1. **using-system-archaeologist** (Router) - Main coordination skill with validation gates
2. **analyzing-unknown-codebases** - Systematic codebase exploration
3. **generating-architecture-diagrams** - C4 diagram generation (Context, Container, Component)
4. **documenting-system-architecture** - Stakeholder-ready architecture docs
5. **validating-architecture-analysis** - Quality gates and completeness checks

---

## Features

### Subagent-Driven Exploration
- Autonomous agents systematically explore codebase sections
- Parallel analysis for faster results
- Coordinated handoffs via shared documents

### Professional Documentation
- C4 diagrams at Context, Container, and Component levels
- Mermaid diagram format for easy rendering
- Subsystem catalogs with dependency tracking
- Architecture decision records (ADRs)

### Quality Validation
- Mandatory validation gates prevent incomplete analysis
- Checklist-driven quality assurance
- Pressure-resistant workflow prevents rushed results

### Workspace Organization
- Timestamped analysis directories
- Organized artifact storage
- Audit trail of decisions

---

## Example Workflow

```bash
# Start analysis
/system-archaeologist

# Claude creates workspace:
# docs/arch-analysis-2025-11-15-1430/
#   ├── 00-coordination.md
#   ├── 01-subsystem-catalog.md
#   ├── 02-c4-context.md
#   ├── 03-c4-container.md
#   ├── 04-c4-component.md
#   └── temp/

# Subagents explore codebase sections
# Documentation generated automatically
# Validation gates ensure completeness
```

---

## Repository Structure

```
skillpacks/
├── .claude/
│   └── commands/
│       └── system-archaeologist.md    # Slash command
├── plugins/
│   └── axiom-system-archaeologist/
│       ├── .claude-plugin/
│       │   └── plugin.json            # Plugin metadata
│       └── skills/
│           └── using-system-archaeologist/
│               ├── SKILL.md           # Main router skill
│               ├── analyzing-unknown-codebases.md
│               ├── generating-architecture-diagrams.md
│               ├── documenting-system-architecture.md
│               └── validating-architecture-analysis.md
├── LICENSE
├── LICENSE_ADDENDUM.md
└── README.md
```

---

## License

CC BY-SA 4.0 (Creative Commons Attribution-ShareAlike 4.0 International) - See [LICENSE](LICENSE) for details.

**Note**: The "Axiom" faction name from Altered TCG is NOT covered by this license - see [LICENSE_ADDENDUM.md](LICENSE_ADDENDUM.md) for details.

---

## About

Built by [@tachyon-beep](https://github.com/tachyon-beep), adapted for standalone use by [@Cubical6](https://github.com/Cubical6).

**Axiom System Archaeologist** provides systematic, pressure-resistant codebase analysis with professional architecture documentation output. Perfect for understanding unfamiliar codebases, documenting legacy systems, or creating design docs for existing projects.
