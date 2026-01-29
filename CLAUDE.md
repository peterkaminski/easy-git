# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Easy Git is a Claude Code skill that translates natural language into git operations for non-technical users. It enables users to perform version control operations using everyday phrases like "save my progress", "backup to cloud", or "what changed?" instead of learning git commands.

**Core concept**: Natural language interface → Git operations with plain English explanations

## Architecture

### Skill-Based System

This project is a Claude Code plugin with a declarative skill definition:

- **Plugin manifest**: `.claude-plugin/plugin.json` defines the plugin metadata
- **Skill definition**: `skills/easy-git/SKILL.md` contains the complete skill logic and behavior
- **Reference materials**: Support files in `skills/easy-git/references/` and `skills/easy-git/examples/`

The skill is triggered when users use natural language phrases related to version control operations (see trigger phrases in SKILL.md frontmatter).

### Skill Architecture Pattern

The skill uses a **declarative YAML frontmatter + Markdown documentation** pattern:

```
---
name: skill-name
description: trigger phrases and when to use
version: 1.0.0
allowed-tools: [list of tools the skill can use]
---

# Markdown content with skill logic
```

**Key design principle**: The skill translates user intent → git operations → plain language feedback

### Core Capabilities

1. **INIT**: Initialize git repository (`git init`)
2. **COMMIT**: Save snapshots with auto-generated messages (`git add -A && git commit`)
   - Includes intelligent .gitignore handling for common dot files/directories
3. **STATUS**: Show what changed (`git status`, `git diff`)
4. **STATUS-IGNORED**: Show what's in .gitignore and what files are being excluded
5. **PUSH**: Backup to cloud (`git push`)
   - Defaults to private repositories when using `gh` CLI
6. **PULL**: Get updates (`git pull`)
7. **TAG**: Label versions (`git tag`)

Each capability follows this workflow:
1. Context gathering (check repo state with git commands)
2. Intent analysis (map natural language → git operation)
3. Execution (run git commands)
4. Plain language output (explain what happened)

### Intent Recognition System

The skill uses Claude's natural language understanding to map user phrases to operations. Key mappings:

- Saving/snapshot/checkpoint → COMMIT
- Backup/sync up/upload → PUSH
- Changes/different/modified → STATUS
- Not tracked/ignored/not uploaded/gitignore → STATUS-IGNORED
- Get/download/sync down → PULL
- Mark/label/milestone → TAG
- Start/initialize/begin → INIT

Context clues help disambiguate (e.g., "to cloud" → PUSH, "from cloud" → PULL, "not tracked/ignored" → STATUS-IGNORED)

## File Structure

```
easy-git/
├── .claude-plugin/
│   └── plugin.json              # Plugin metadata, points to skills directory
├── skills/
│   └── easy-git/
│       ├── SKILL.md             # Complete skill logic (THE core implementation)
│       ├── references/
│       │   ├── personas.md      # Language patterns for different user types
│       │   └── git-primer.md   # Git concepts explained simply
│       └── examples/
│           └── workflows.md     # Complete scenario walkthroughs
├── README.md                    # User-facing documentation
├── CONTRIBUTING.md             # Contributor guidelines
├── QUICK_REFERENCE.md          # One-page cheat sheet
├── CHANGELOG.md                # Version history
└── LICENSE                     # MIT license
```

**Critical file**: `skills/easy-git/SKILL.md` contains ALL skill logic and should be the primary focus for modifications.

## Modifying the Skill

### Adding New Language Patterns

1. Add trigger phrases to SKILL.md frontmatter `description` field
2. Add persona-specific phrases to `references/personas.md`
3. Add example interactions to `examples/workflows.md`
4. Update README.md with new examples if user-facing

### Improving Commit Message Generation

The commit message generation logic is in SKILL.md under "Smart commit message generation" (line ~520). It analyzes:
- File types (docs vs code vs config)
- Change patterns (add, modify, delete)
- Combining multiple changes into one message

Modifications should focus on this section.

### Adding Error Handling

Error handling patterns are defined in SKILL.md under "Error Handling Strategies" (line ~349). Each error scenario includes:
- Detection method
- Plain language explanation
- Actionable solutions
- Git context for learning

### Output Format Standards

ALL outputs must follow this structure (defined in SKILL.md line ~446):

1. Status indicator: ✓ (success), ⚠ (warning), 💡 (info)
2. Plain language summary
3. "What I did:" with git commands in parentheses
4. Relevant details (files, counts, messages)
5. "Git context:" brief explanation

## Design Principles

### User Experience Philosophy

- **Trust natural language**: Execute directly without confirmation for standard operations
- **Teach through doing**: Show git commands after execution so users can learn
- **Safety first**: Warn before destructive operations
- **Plain language**: Never force git terminology on users
- **Progressive disclosure**: Introduce git concepts gradually through "Git context" sections

### Key Behavioral Guidelines

1. **Suggest Easy Git commands, not bare git**: When Claude Code needs to suggest git operations to users, always use Easy Git natural language (e.g., "save my progress") instead of bare git commands (e.g., "git commit"), unless there's no Easy Git equivalent.

2. **Default to private repositories**: When using `gh` CLI to create repositories, always use `--private` flag unless the user explicitly requests public.

3. **Smart .gitignore handling**: When committing, automatically detect common dot files/directories (.claude, .obsidian, .vscode, etc.) that should typically be excluded, and offer to add them to .gitignore in plain language before proceeding with the commit.

### Scope Boundaries (v1.0)

**Included**: Linear history, single branch, simple collaboration
**Excluded**: Branching, merging, rebasing, stashing, history rewriting

This is intentional - Easy Git targets non-technical users who need basic version control.

### Persona-Driven Design

The skill recognizes language from 6 persona types:
- Creative Professional (writers, designers)
- Small Business Owner
- Content Creator
- Maker/Hobbyist
- Product Manager
- Product Designer

Each persona uses different terminology for the same operations. See `references/personas.md` for complete mappings.

## Testing Approach

When testing changes, verify:

1. **Trigger recognition**: All documented phrases trigger correctly
2. **Output format**: Follows ✓/⚠/💡 + description + "What I did" + "Git context" structure
3. **Git command display**: Commands shown in parentheses for learning
4. **Error handling**: Edge cases produce helpful guidance
5. **Persona fit**: Language works for target user types

Manual testing checklist in SKILL.md line ~538.

## Documentation Updates

When making changes that affect user experience:

1. **SKILL.md**: Always update (contains all logic)
2. **README.md**: Update if user-facing feature/behavior changes
3. **QUICK_REFERENCE.md**: Update if new common operations added
4. **CHANGELOG.md**: Add entry describing the change
5. **personas.md**: Update if adding new language patterns
6. **git-primer.md**: Update if introducing new git concepts
7. **workflows.md**: Add examples if new interaction patterns

## Plugin Installation

Users install by symlinking or copying to `~/.claude/plugins/easy-git`. The plugin.json points Claude Code to the skills directory.

## Skill vs Plugin

- **Plugin**: Container (`.claude-plugin/plugin.json`)
- **Skill**: The actual logic (`skills/easy-git/SKILL.md`)

A plugin can contain multiple skills. This plugin contains one skill: easy-git.
