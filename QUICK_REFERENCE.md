# Easy Git Quick Reference

One-page guide to using Easy Git with natural language.

## Common Commands

### Save Your Work
```
"save my progress"
"checkpoint this"
"save a snapshot"
"create a savepoint"
```
→ Creates a commit with auto-generated message

### Check What Changed
```
"what changed?"
"show my changes"
"what did I do?"
"show me my work"
```
→ Shows modified, new, and deleted files

### Check Ignored Files
```
"what files are not tracked?"
"what's not being uploaded?"
"is there anything ignored by version control?"
"what's in gitignore"
```
→ Shows files/directories excluded from version control

### Backup to Cloud
```
"backup to cloud"
"sync up"
"upload my work"
"send to backup"
```
→ Pushes commits to remote (after committing if needed)

### Get Updates
```
"get latest"
"sync down"
"download updates"
"pull from cloud"
```
→ Pulls changes from remote

### Label a Version
```
"mark this as v1.0"
"create milestone"
"tag this version"
"label as release"
```
→ Creates a named tag

### Start Tracking
```
"start version control"
"initialize tracking"
"begin tracking changes"
```
→ Initializes git repository

### Getting Help
```
"tell me about Easy Git"
"what can Easy Git do"
"how do I backup"
"explain saving work"
"what should I do now"
```
→ Get guidance on Easy Git capabilities and next steps

## Quick Workflows

### Daily Work
```
1. "what changed today?"        (see your work)
2. "save my progress"           (commit)
3. "backup to cloud"            (push)
```

### Multi-Device Sync
```
# Device 1
"backup my work"                (commit + push)

# Device 2
"get my latest work"            (pull)
[work on device 2]
"backup my work"                (commit + push)

# Back on Device 1
"get latest"                    (pull)
```

### Collaboration
```
1. "get latest from team"       (pull)
2. [make your changes]
3. "save my updates"            (commit)
4. "sync with team"             (push)
```

### First Time
```
1. "start tracking this project"  (git init)
2. "save initial version"         (first commit)
3. "backup to cloud"              (set up remote + push)
```

## Understanding Output

### Success
```
✓ Backed up your work to the cloud

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update docs" (git commit)
• Uploaded to cloud (git push)

Git context: Brief explanation...
```

### Warning
```
⚠ You have unsaved changes

[explanation]

Options:
1. [option 1]
2. [option 2]
```

### Info
```
💡 You're not tracking versions yet!

[explanation and guidance]
```

## Common Scenarios

### "I want to try something without losing my work"
```
1. "save a checkpoint"          (save current state)
2. [try your experiment]
3. If it works: "save this version"
   If it fails: "go back" or just discard changes
```

### "I accidentally included the wrong files"
```
"I didn't mean to save [filename]"
→ Easy Git will help you fix the commit
```

### "Someone else changed the same file"
```
[When pulling]
⚠ Merge conflict detected

Options:
1. "keep my version"
2. "use their version"
3. "help me fix it manually"
```

### "I need an old version"
```
1. "show my history"            (see past commits)
2. "what was in [commit]?"      (see specific commit)
3. "show me that version"       (view old version)
4. "return to present"          (back to current)
```

## Phrase Cheat Sheet

### By Intent

| I Want To... | Say... |
|-------------|---------|
| Save my work | "save snapshot", "checkpoint this" |
| See changes | "what changed?", "show changes" |
| Check ignored files | "what's not being uploaded?", "show ignored files" |
| Upload/backup | "backup to cloud", "sync up" |
| Download updates | "get latest", "sync down" |
| Mark important version | "tag this as X", "label version" |
| Start tracking | "initialize tracking" |
| Get help | "tell me about Easy Git", "how do I backup", "what should I do now" |

### By Persona

**Writer/Designer:**
- "save this draft"
- "what changed in my writing"
- "back up my designs"

**Business Owner:**
- "make this safe"
- "backup everything"
- "don't lose this"

**Content Creator:**
- "save milestone"
- "sync to server"
- "what's ready to publish"

**Maker/Hobbyist:**
- "save my progress"
- "what did I try"
- "label as working"

**Product Manager:**
- "record this decision"
- "mark as sprint-12"
- "what's in this release"

**Product Designer:**
- "save exploration"
- "version prototype"
- "checkpoint iteration"

## Troubleshooting

### Skill not responding?
- Try exact phrase: "save my progress"
- Check Claude Code has loaded the skill
- Verify you're in a project directory

### Can't push to cloud?
- Need remote configured (GitHub, GitLab, etc.)
- Say "help me set up cloud backup"
- Check authentication (tokens, SSH keys)

### Changes not showing?
- Files might be in .gitignore
- Try "show all changes" to see everything

### Merge conflict?
- Don't panic! Easy Git will guide you
- Choose: keep yours, use theirs, or merge manually
- Can always ask "help me fix this conflict"

## Tips

1. **Commit often** - Small, frequent snapshots are better than big ones
2. **Push regularly** - Backup to cloud daily (or more)
3. **Pull before work** - Get latest updates before starting
4. **Descriptive tags** - Use meaningful names: "v1.0", "working", "approved"
5. **Ask questions** - Easy Git will explain what it's doing

## Learn More

- Full documentation: See [README.md](README.md)
- All phrases: See [skills/easy-git/references/personas.md](skills/easy-git/references/personas.md)
- Git concepts: See [skills/easy-git/references/git-primer.md](skills/easy-git/references/git-primer.md)
- Example workflows: See [skills/easy-git/examples/workflows.md](skills/easy-git/examples/workflows.md)

---

**Remember**: Just describe what you want to do in your own words. Easy Git understands!
