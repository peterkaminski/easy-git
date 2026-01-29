# Changelog

All notable changes to Easy Git will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-01-29

### Added
- Initial release of Easy Git skill for Claude Code
- Natural language interface for git operations
- Support for 6 user personas:
  - Creative Professional (writer, designer, photographer)
  - Small Business Owner
  - Content Creator (blogger, YouTuber)
  - Hobbyist/Maker
  - Product Manager
  - Product Designer
- Core git operations:
  - Initialize tracking (git init)
  - Save snapshots (git commit)
  - Check changes (git status)
  - Backup to cloud (git push)
  - Get updates (git pull)
  - Label versions (git tag)
- Auto-generated commit messages based on file analysis
- Plain language error handling and guidance
- Learning mode - shows git commands after execution
- First-time user setup assistance
- Comprehensive documentation:
  - User guide (README.md)
  - Skill logic (SKILL.md)
  - Persona language patterns (personas.md)
  - Git concepts in plain language (git-primer.md)
  - Example workflows (workflows.md)
  - Contributing guide (CONTRIBUTING.md)

### Supported Operations
- **INIT**: "start tracking changes", "initialize versioning"
- **COMMIT**: "save snapshot", "checkpoint this", "save progress"
- **STATUS**: "what changed?", "show changes", "what did I do"
- **PUSH**: "backup to cloud", "sync up", "upload my work"
- **PULL**: "get latest", "sync down", "download updates"
- **TAG**: "mark this version", "create milestone", "label as v1.0"

### Features
- 50+ natural language trigger phrases across all personas
- Smart commit message generation
- Merge conflict detection and resolution guidance
- Multi-device sync workflow support
- Error recovery with plain language explanations
- Progressive learning (shows git commands with plain explanations)

### Known Limitations
- Single branch workflow only (main/master)
- Linear history (no complex rebasing)
- Simple conflict resolution (manual merge guidance)
- No branch management (planned for v2.0)
- No stash support (planned for future release)
- No cherry-pick or advanced git operations

## [1.1.0] - 2026-01-29

### Added
- **Smart .gitignore handling**: Automatically detects common dot files/directories (.claude, .obsidian, .vscode, etc.) and offers to exclude them during commit
- **Check ignored files capability**: New phrases to view what files are excluded from version control:
  - "what files are not tracked?"
  - "what's not being uploaded?"
  - "is there anything ignored by version control?"
  - "what's in gitignore"
  - "show me ignored files"
- **Private by default**: When using `gh` CLI to create repositories, now defaults to private repos
- Support for Read, Write, Edit tools to manage .gitignore files

### Changed
- **Claude Code behavior**: Now suggests Easy Git natural language commands (e.g., "save my progress") instead of bare git commands (e.g., "git commit") when recommending operations to users
- COMMIT workflow now includes .gitignore check before staging files
- Enhanced skill capabilities from 6 to 7 (added STATUS-IGNORED)

### Improved
- Better user privacy with private repository default
- Proactive protection of development tool configurations
- More comprehensive file tracking visibility

## [Unreleased]

### Planned for v1.2
- Enhanced commit message generation with more context
- Additional language patterns based on user feedback
- Improved conflict resolution strategies
- Support for more git configurations

### Planned for v2.0
- Branch creation and switching
- Branch merging workflows
- Support for parallel work streams
- More advanced collaboration features

### Under Consideration
- Internationalization (non-English languages)
- Stash operations
- Interactive rebase (simplified)
- Cherry-pick support
- Git hooks integration
- Team workflow presets

## Version History

### Version Numbering
- **Major version** (X.0.0): Breaking changes, major new features
- **Minor version** (1.X.0): New features, backward compatible
- **Patch version** (1.0.X): Bug fixes, documentation updates

### Release Notes Location
- Latest: See above
- Detailed changes: See GitHub releases
- Migration guides: See UPGRADING.md (when applicable)

---

## Change Categories

Changes are grouped into these categories:
- **Added**: New features
- **Changed**: Changes to existing functionality
- **Deprecated**: Soon-to-be removed features
- **Removed**: Removed features
- **Fixed**: Bug fixes
- **Security**: Security improvements

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to suggest changes or report issues.
