---
name: easy-git
description: This skill should be used when the user wants to save work ("save snapshot", "checkpoint this", "save my progress", "create savepoint", "capture this moment", "freeze this version", "record changes", "make a snapshot", "checkpoint prototype", "save version"), backup to cloud ("backup to cloud", "sync up", "upload my work", "send to backup", "save to server", "publish my changes", "push to cloud", "backup online"), check changes ("what changed?", "show changes", "what did I do", "show me my work", "what's different", "list changes", "what have I modified", "what is new"), get updates ("get latest", "sync down", "download updates", "pull from cloud", "refresh from server", "update from backup", "get changes from cloud"), label versions ("mark this version", "create milestone", "tag this", "bookmark version", "label this version", "name this version", "tag as release"), or start tracking ("start version control", "initialize versioning", "begin tracking changes", "start keeping history", "make this a versioned project"). This skill translates natural language into git operations for non-technical users.
version: 1.0.0
allowed-tools:
  - Bash(git init*)
  - Bash(git add*)
  - Bash(git commit*)
  - Bash(git push*)
  - Bash(git pull*)
  - Bash(git status*)
  - Bash(git tag*)
  - Bash(git diff*)
  - Bash(git log*)
  - Bash(git remote*)
  - Bash(git branch*)
  - Bash(git config*)
  - Bash(test*)
  - Read
---

# Easy Git - Natural Language Git Operations

Makes git accessible through plain language. No git knowledge required.

## When to Use This Skill

Invoke when the user uses natural, non-technical language to describe version control operations. This skill is designed for users who think in terms of:
- Saving drafts, versions, backups
- Protecting work, making it safe
- Publishing, syncing, sharing
- Checkpoints, milestones, progress markers

See trigger phrases in frontmatter description for full list.

## Core Capabilities

### 1. Initialize Tracking (INIT)

Detect uninitialized repos and guide users through setup.

**When to use:**
- User mentions "start tracking", "initialize", "begin version control"
- Any operation attempted on uninitialized repo

**Context gathering:**
```bash
# Check if git is initialized
test -d .git && echo "initialized" || echo "not initialized"
```

**Workflow:**
1. Check if `.git` directory exists
2. If not initialized:
   - Explain benefits in plain language
   - Ask for confirmation (optional - can auto-execute)
   - Run `git init`
   - Configure user name/email if needed
   - Offer to set up remote backup (GitHub, GitLab, etc.)
3. Provide confirmation message

**Output format:**
```
✓ Started tracking your project!

What I did:
• Initialized version control (git init)
• Set up local history tracking

Git context: This created a hidden .git folder that tracks all your changes.

Next steps:
• Save a snapshot: "save my progress"
• Backup to cloud: "backup to cloud" (requires GitHub/GitLab setup)
```

### 2. Save Snapshot (COMMIT)

Stage all changes and commit with auto-generated message.

**When to use:**
- "save snapshot", "checkpoint", "save progress", "capture this", "record changes"
- Any saving/checkpointing language

**Context gathering:**
```bash
# Get current changes
git diff HEAD
git status --short
git log --oneline -5
```

**Workflow:**
1. Gather context about what changed
2. Analyze file changes to understand the work:
   - What files were added/modified/deleted
   - Nature of changes (docs, code, config, assets)
   - Look for patterns (feature, fix, update, refactor)
3. Generate descriptive commit message:
   - Summarize what changed concisely
   - Focus on what/why, not how
   - Use present tense
   - Example: "Update documentation and add examples"
4. Execute:
   ```bash
   git add -A
   git commit -m "generated message"
   ```
5. Display result in plain language + git commands

**Output format:**
```
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update documentation and add examples" (git commit)

Files saved:
• Modified: README.md, docs/guide.md
• Added: examples/workflow.md

Git context: This is called "committing" - you can always return to this exact point.
```

### 3. Check Changes (STATUS)

Show what's different since last snapshot.

**When to use:**
- "what changed", "show changes", "what did I do", "what's different"
- Any inquiry about current state

**Context gathering:**
```bash
git status
git diff --stat
git diff --name-status
```

**Workflow:**
1. Get git status and diff statistics
2. Categorize changes:
   - New files (never tracked before)
   - Modified files (changed since last snapshot)
   - Deleted files
3. Translate into plain language
4. Show summary statistics

**Output format:**
```
Here's what changed since your last snapshot:

Modified files:
• README.md (23 lines changed)
• src/app.js (12 lines changed)

New files:
• examples/demo.js

Summary: 2 files modified, 1 file added

Git context: These are "uncommitted changes" - save a snapshot to preserve them.
```

### 4. Backup to Cloud (PUSH)

Upload local snapshots to remote repository.

**When to use:**
- "backup to cloud", "sync up", "upload", "publish", "send to backup"
- Any cloud/remote upload language

**Context gathering:**
```bash
git remote -v
git branch --show-current
git log @{u}.. --oneline 2>&1
git status
```

**Workflow:**
1. Check if remote exists:
   - If no remote: Guide through GitHub/GitLab setup
   - Explain what a remote is in plain language
2. Check for uncommitted changes:
   - If uncommitted: Ask if they want to save snapshot first
3. Check tracking branch:
   - If no upstream: Set up tracking with `git push -u origin [branch]`
4. Execute push:
   ```bash
   git push origin [branch]
   ```
5. Handle errors:
   - Authentication: Guide through credential setup
   - Rejected push: Explain need to pull first
   - No commits: Explain nothing to backup

**Output format:**
```
✓ Backed up your work to the cloud

What I did:
• Uploaded 3 snapshots to cloud storage (git push origin main)

Snapshots backed up:
• "Update documentation and add examples"
• "Fix configuration bug"
• "Add new feature"

Git context: This is called "pushing" - your work is now safe on the remote server.
```

### 5. Get Updates (PULL)

Download changes from remote repository.

**When to use:**
- "get latest", "sync down", "download updates", "pull from cloud"
- Any download/sync from remote language

**Context gathering:**
```bash
git remote -v
git branch --show-current
git status
git diff --stat
```

**Workflow:**
1. Check for uncommitted changes:
   - If uncommitted: Warn that they might be lost
   - Offer to save snapshot first
2. Check remote exists:
   - If no remote: Explain can't sync without cloud setup
3. Execute pull:
   ```bash
   git pull
   ```
4. Detect merge conflicts:
   - If conflicts: Provide plain-language conflict resolution guidance
   - List conflicted files
   - Offer resolution options
5. Display update summary

**Output format (no conflicts):**
```
✓ Downloaded latest updates from cloud

What I did:
• Synced with cloud storage (git pull)

Updates received:
• "Update API endpoints" (by teammate)
• "Fix typo in README" (by teammate)

Files changed:
• Modified: src/api.js, README.md

Git context: This is called "pulling" - you now have the latest version.
```

**Output format (with conflicts):**
```
⚠ Your local work conflicts with cloud version

What happened: Someone else changed the same files you did.

Files with conflicts:
• README.md (both you and teammate edited the same sections)
• config.json (different values for same setting)

Options:
1. Keep your version: "use my version"
2. Use cloud version: "use cloud version"
3. Fix manually: I'll guide you through editing the files

Git context: This is called a "merge conflict" - it happens when the same
content is edited in two places.
```

### 6. Label Version (TAG)

Create named milestone for current snapshot.

**When to use:**
- "mark this version", "create milestone", "tag this", "label version"
- "name this version X", "tag as X"

**Context gathering:**
```bash
git tag -l
git log -1 --oneline
git status
```

**Workflow:**
1. Check for uncommitted changes:
   - If uncommitted: Suggest saving snapshot first
2. Extract tag name from user input:
   - Look for version numbers (v1.0.0, 1.2.3)
   - Look for milestone names ("beta", "launch", "working-version")
   - If not specified: Ask what to name it
3. Check if tag already exists:
   - If exists: Warn and ask for different name
4. Create tag:
   ```bash
   git tag [name]
   ```
5. Offer to backup tag to cloud:
   ```bash
   git push origin [name]
   ```

**Output format:**
```
✓ Labeled this version as "v1.0.0"

What I did:
• Created version label "v1.0.0" (git tag v1.0.0)
• Backed up label to cloud (git push origin v1.0.0)

This label points to:
• Snapshot: "Add new feature and documentation"

Git context: This is called "tagging" - you can always return to this named version.
```

## Intent Analysis

Use natural language understanding to map user phrases to operations. Don't rely on exact phrase matching - understand the intent.

**Mapping guide:**
- **Saving/snapshot/checkpoint/progress/record/capture/freeze** → COMMIT
- **Backup/sync up/upload/publish/send to server/push** → PUSH
- **Changes/different/modified/what did I do/show work** → STATUS
- **Get/download/sync down/update from/pull/refresh** → PULL
- **Mark/label/milestone/tag/bookmark/name version** → TAG
- **Start/initialize/begin tracking/version control** → INIT

**Context clues:**
- "to cloud", "to server", "online" → suggests PUSH
- "from cloud", "from server", "latest" → suggests PULL
- "what", "show", "list" → suggests STATUS
- "this version", "this as", "[name]" → suggests TAG

## Error Handling Strategies

### No .git directory
```
💡 You're not tracking versions yet!

Would you like to start? This will:
• Keep a history of your changes
• Let you go back to earlier versions
• Enable backup to the cloud (optional)

Say "yes, start tracking" or "start version control" to begin.
```

### No remote configured (when trying to push/pull)
```
💡 No cloud backup is set up yet

To backup to the cloud, you need to:
1. Create a repository on GitHub or GitLab
2. Connect it to this project

Would you like help setting this up? Say "set up cloud backup" and I'll guide you.
```

### Uncommitted changes (when pulling)
```
⚠ You have unsaved changes

Before getting updates from the cloud, you should save your current work.

Options:
1. "save my progress" - Create a snapshot first (recommended)
2. "discard my changes" - Throw away current changes (careful!)
3. "cancel" - Don't sync right now

Git context: This prevents your work from being lost during the sync.
```

### Merge conflicts
```
⚠ Your local work conflicts with cloud version

What happened: Both you and someone else changed the same parts of these files:
• README.md (lines 15-23)
• config.json (line 8)

Options:
1. "keep my version" - Use your changes (git checkout --ours [file])
2. "use cloud version" - Use their changes (git checkout --theirs [file])
3. "show me the conflicts" - I'll show you what's different
4. "help me fix it" - Guide me through manual resolution

Git context: This is a "merge conflict" - git can't automatically combine the changes.
```

### Detached HEAD
```
⚠ You're viewing an old version

You're currently looking at an old snapshot, not your current work.

To get back to your current work: "go back to main"

Git context: This is called "detached HEAD" - you're in read-only history mode.
```

### Authentication errors
```
⚠ Can't connect to cloud storage

Problem: Authentication failed - git can't verify who you are.

Solutions:
1. If using GitHub: Set up a personal access token
2. If using SSH: Set up SSH keys
3. Check your credentials are up to date

Say "help with authentication" for detailed setup instructions.
```

### Nothing to commit
```
💡 No changes to save

You haven't modified anything since your last snapshot.

Git context: This is normal - you can only save when there are changes.
```

### Already up to date (pull)
```
✓ Already up to date

You already have the latest version from the cloud - no updates available.

Git context: Your local copy matches the remote - nothing to download.
```

## Output Format Standards

Always structure responses with:

1. **Status indicator:** ✓ (success), ⚠ (warning), 💡 (info)
2. **Plain language summary:** What happened in user terms
3. **What I did:** Bullet list with git commands in parentheses
4. **Relevant details:** Files, messages, counts
5. **Git context:** Brief explanation of the git concept

**Example:**
```
✓ Backed up your work to the cloud

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update documentation and examples" (git commit)
• Uploaded to cloud (git push origin main)

Files backed up:
• Modified: README.md, docs/guide.md
• Added: examples/workflow.md

Git context: This is called "committing and pushing" - your work is now safely
stored on the remote server and you can access it from anywhere.
```

## First-Time User Experience

When a user attempts any operation on an uninitialized repository:

1. **Detect state:**
   ```bash
   test -d .git && echo "initialized" || echo "not initialized"
   ```

2. **Provide friendly explanation:**
   ```
   💡 You're not tracking versions yet!

   Would you like to start? This will:
   • Keep a history of your changes
   • Let you go back to earlier versions
   • Enable backup to the cloud (optional)

   Say "yes, start tracking" or "start version control" to begin.
   ```

3. **After initialization:**
   ```
   ✓ Started tracking your project!

   What I did:
   • Initialized version control (git init)

   Next steps:
   • Save a snapshot: "save my progress"
   • Check what changed: "what changed?"
   • Backup to cloud: "backup to cloud" (requires GitHub/GitLab setup)

   Git context: You now have a hidden .git folder that tracks all your changes.
   ```

## Advanced Workflows

### First commit + push
When user wants to backup but has never committed:
1. Detect no commits exist
2. Suggest: "save a snapshot first"
3. Auto-chain: commit → push

### Pull before push
When user tries to push but remote has new commits:
1. Detect push rejection
2. Explain: "cloud has updates you don't have"
3. Suggest: "get latest updates first"
4. Guide through: pull → resolve conflicts (if any) → push

### Smart commit message generation
Analyze git diff to create messages:
- File types: docs → "Update documentation", code → "Modify [component]"
- Patterns: new files → "Add [feature]", deletions → "Remove [feature]"
- Mix: "Update [X] and add [Y]"
- Keep under 72 characters
- Be specific but concise

## Reference Materials

- See `references/personas.md` for language variations across user types
- See `references/git-primer.md` for git concepts in plain language
- See `examples/workflows.md` for complete scenario walkthroughs

## Testing Checklist

- [ ] Init: new project, already initialized
- [ ] Commit: changes exist, no changes, generated message quality
- [ ] Status: various file states (modified, new, deleted)
- [ ] Push: first push, subsequent push, no remote, auth error
- [ ] Pull: clean pull, merge conflicts, already up to date
- [ ] Tag: create tag, duplicate tag, push tag
- [ ] Errors: handle all error scenarios gracefully
- [ ] Persona phrases: test all trigger phrases work
