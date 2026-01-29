# Easy Git - Natural Language Git for Claude Code

A Claude Code skill that makes git accessible to non-technical users through natural language. Save work, backup to the cloud, and track changes using everyday language - no git knowledge required.

## What is This?

Easy Git translates plain language into git operations. Instead of learning git commands, just describe what you want to do:

- **"save my progress"** → git commit
- **"backup to cloud"** → git push
- **"what changed?"** → git status
- **"get latest"** → git pull
- **"mark this version"** → git tag

Designed for writers, designers, small business owners, content creators, makers, product managers, and anyone who wants version control without the complexity.

## Features

- **Natural language interface** - Use everyday phrases instead of git commands
- **Auto-generated commit messages** - Analyzes your changes to create descriptive messages
- **Smart .gitignore handling** - Automatically detects and offers to exclude common development files
- **Plain language explanations** - Understands what you did, explains git concepts simply
- **Error recovery guidance** - Handles conflicts and errors with helpful, non-technical advice
- **Learning mode** - Shows git commands after execution so you can learn
- **Built-in help system** - Context-aware guidance available anytime with "what can I do" or "how do I backup"
- **First-time friendly** - Guides you through setup if you're new to version control
- **Privacy by default** - Creates private repositories when setting up cloud backup

## Installation

### Prerequisites

- [Claude Code](https://claude.com/code) installed
- Git installed on your system

### Install the Skill

**Note: You might want your technical person to help you with this installation step!**

**After that, Easy Git will make it easier to track versions of your files using plain language.**

1. Clone or download this repository:
   ```bash
   git clone https://github.com/peterkaminski/easy-git.git
   cd easy-git
   ```

2. Install as a Claude Code plugin:
   ```bash
   # Option 1: Symlink to your Claude plugins directory
   ln -s $(pwd) ~/.claude/plugins/easy-git
   
   # Option 2: Copy to your Claude plugins directory
   cp -r . ~/.claude/plugins/easy-git
   ```

3. Reload Claude Code or restart your session

### Verify Installation

In Claude Code, try:
```
User: "what changed?"
```

If the skill is installed correctly, Easy Git will respond with your current git status in plain language.

## Usage

### First Time Setup

When you first use Easy Git in a new project:

```
User: "start tracking my project"

Easy Git:
✓ Started tracking your project!

What I did:
• Initialized version control (git init)

Next steps:
• Save a snapshot: "save my progress"
• Backup to cloud: "backup to cloud" (requires GitHub/GitLab setup)
```

### Common Operations

#### Save Your Work
```
User: "save a snapshot"
User: "checkpoint this"
User: "save my progress"
```

Easy Git will stage all changes and create a commit with an auto-generated message.

#### Check What Changed
```
User: "what changed?"
User: "show my changes"
User: "what did I do?"
```

Shows modified, new, and deleted files in plain language.

#### Check Ignored Files
```
User: "what files are not tracked?"
User: "what's not being uploaded?"
User: "is there anything ignored by version control?"
```

Shows what files/directories are in .gitignore and being excluded from backups.

#### Backup to Cloud
```
User: "backup to cloud"
User: "sync up"
User: "upload my work"
```

Pushes commits to your remote repository (GitHub, GitLab, etc.).

#### Get Updates
```
User: "get latest"
User: "sync down"
User: "download updates"
```

Pulls changes from the remote repository.

#### Label Versions
```
User: "mark this as v1.0"
User: "create milestone"
User: "tag this version"
```

Creates a named tag for the current commit.

### Getting Help

Easy Git includes built-in, context-aware help:

#### Ask About Easy Git
```
User: "tell me about Easy Git"
User: "what can Easy Git do"
User: "how does Easy Git work"
```

Get an overview of all capabilities with example phrases.

#### Ask About Specific Operations
```
User: "how do I backup to cloud"
User: "explain saving work"
User: "help me understand changes"
```

Get detailed guidance on any operation including:
- What it does
- How to use it
- Alternative phrases you can use
- Common workflows
- Git context explained simply

#### Ask What to Do Next
```
User: "what should I do now"
User: "what's next"
User: "what can I do"
```

Get context-aware suggestions based on your current repo state:
- Not initialized? Learn how to start tracking
- No commits? Learn how to save your first snapshot
- Have changes? See the workflow to save and backup
- All clean? Know your options for what's next

Help is always available - just ask in plain language!

### Example Workflows

#### Daily Work Cycle
```
1. User: "what changed today?"
   → See your modifications

2. User: "save my work"
   → Commit changes

3. User: "backup to cloud"
   → Push to remote
```

#### Collaboration
```
1. User: "get latest from team"
   → Pull changes

2. [Make your changes]

3. User: "save my updates"
   → Commit your work

4. User: "sync with team"
   → Push your commits
```

#### Multi-Device
```
# On laptop
User: "backup my work"
→ Commit + push

# On desktop
User: "get my latest work"
→ Pull changes

# Continue working on desktop
User: "save and backup"
→ Commit + push

# Back on laptop
User: "get latest"
→ Pull desktop changes
```

## Supported Personas

Easy Git understands language from different user types:

### Creative Professional
- "save this draft"
- "what changed in my writing"
- "back up my work"

### Small Business Owner
- "make this safe"
- "backup to cloud"
- "don't lose this"

### Content Creator
- "save milestone"
- "what's ready to publish"
- "sync to server"

### Hobbyist/Maker
- "save my progress"
- "what did I try"
- "label as working"

### Product Manager
- "record this decision"
- "what's in this release"
- "mark as sprint-12"

### Product Designer
- "save this exploration"
- "version this prototype"
- "what changed from last iteration"

See [references/personas.md](skills/easy-git/references/personas.md) for complete phrase lists.

## How It Works

### Intent Recognition

Easy Git uses Claude's natural language understanding to map your phrases to git operations. You don't need to use exact phrases - just describe what you want:

- Saving/snapshot/checkpoint → **COMMIT**
- Backup/sync up/upload → **PUSH**
- Changes/different/what did I do → **STATUS**
- Get/download/sync down → **PULL**
- Mark/label/milestone → **TAG**

### Smart Commit Messages

When you save a snapshot, Easy Git analyzes your changes and generates a descriptive commit message:

```
Files changed:
- Modified: README.md, docs/guide.md
- Added: examples/workflow.md

Generated message:
"Update documentation and add workflow examples"
```

### Plain Language Output

Every response includes:
- What happened in everyday language
- What commands were run (for learning)
- Brief explanation of the git concept

```
✓ Backed up your work to the cloud

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update docs" (git commit)
• Uploaded to cloud (git push origin main)

Git context: This is called "committing and pushing" - your work is now safely stored on the remote server.
```

## Error Handling

Easy Git handles common errors gracefully:

### No Remote Configured
```
💡 No cloud backup is set up yet

To backup to the cloud, you need to:
1. Create a repository on GitHub or GitLab
2. Connect it to this project

Would you like help setting this up?
```

### Merge Conflicts
```
⚠ Your local work conflicts with cloud version

Files with conflicts:
• README.md (both you and teammate edited the same sections)

Options:
1. "keep my version" - Use your changes
2. "use cloud version" - Use their changes
3. "help me fix it" - Guide me through manual resolution
```

### Uncommitted Changes
```
⚠ You have unsaved changes

Before getting updates from the cloud, you should save your current work.

Options:
1. "save my progress" - Create snapshot first (recommended)
2. "discard my changes" - Throw away current changes
```

## Documentation

- **[SKILL.md](skills/easy-git/SKILL.md)** - Complete skill logic and capabilities
- **[personas.md](skills/easy-git/references/personas.md)** - Language patterns for different user types
- **[git-primer.md](skills/easy-git/references/git-primer.md)** - Git concepts explained simply
- **[workflows.md](skills/easy-git/examples/workflows.md)** - Detailed example scenarios

## Scope

### Included (v1.0)
- Initialize tracking (git init)
- Save snapshots (git commit)
- Check changes (git status)
- Backup to cloud (git push)
- Get updates (git pull)
- Label versions (git tag)
- Simple conflict detection and guidance

### Not Included (Future)
- Branching and merging
- Interactive rebasing
- Cherry-picking
- Stashing
- Complex conflict resolution
- History rewriting

Easy Git focuses on a single-branch, linear history workflow suitable for individual users and simple collaboration.

## Requirements

- **Claude Code**: Latest version
- **Git**: Version 2.x or higher
- **Remote repository** (optional): GitHub, GitLab, Bitbucket, or self-hosted

## Troubleshooting

### Skill Not Triggering

If Easy Git doesn't respond to natural language:

1. Check installation: `ls ~/.claude/plugins/easy-git`
2. Verify SKILL.md exists in skills/easy-git/
3. Try exact trigger phrase: "save my progress"
4. Reload Claude Code

### Git Errors

If you see git errors:

1. Ensure git is installed: `git --version`
2. Check you're in a project directory
3. Verify remote is configured: `git remote -v`
4. Check credentials: `git config user.name`

### Authentication Issues

For push/pull authentication errors:

1. **GitHub**: Set up personal access token
2. **SSH**: Configure SSH keys
3. **Credentials**: Use `git config credential.helper store`

## Contributing

Contributions welcome! Areas for improvement:

- Additional persona language patterns
- Better commit message generation
- More conflict resolution strategies
- Support for additional git operations
- Localization to other languages

## License

MIT License - see LICENSE file for details

## Credits

Created by Peter Kaminski

Built for Claude Code by Anthropic

## Learn More

- [Git documentation](https://git-scm.com/doc)
- [GitHub guides](https://guides.github.com/)
- [Claude Code documentation](https://claude.com/code/docs)

## Support

For issues or questions:
- Open an issue on GitHub
- Consult [git-primer.md](skills/easy-git/references/git-primer.md) for git concepts
- Check [workflows.md](skills/easy-git/examples/workflows.md) for examples

---

**Remember**: You don't need to know git to use Easy Git. Just describe what you want to do in your own words!
