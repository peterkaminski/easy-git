# Example Workflows

Complete scenario walkthroughs showing how different personas use easy-git.

## Workflow 1: Creative Professional - First Time Setup

**Persona:** Writer working on a novel

**Scenario:** Sarah wants to start tracking her manuscript revisions

### Interaction

```
Sarah: "I want to start tracking changes to my novel"

Easy Git:
💡 You're not tracking versions yet!

Would you like to start? This will:
• Keep a history of your changes
• Let you go back to earlier versions
• Enable backup to the cloud (optional)

Say "yes, start tracking" or "start version control" to begin.

---

Sarah: "yes, start tracking"

Easy Git:
✓ Started tracking your project!

What I did:
• Initialized version control (git init)
• Configured git with your name and email

Next steps:
• Save a snapshot: "save my progress"
• Check what changed: "what changed?"
• Backup to cloud: "backup to cloud" (requires GitHub/GitLab setup)

Git context: You now have a hidden .git folder that tracks all your changes.

---

Sarah: "save my progress"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Initial manuscript draft with chapters 1-3" (git commit)

Files saved:
• Added: chapter1.txt
• Added: chapter2.txt
• Added: chapter3.txt
• Added: outline.txt

Git context: This is called "committing" - you can always return to this exact point.

---

Sarah: "back this up to the cloud"

Easy Git:
💡 No cloud backup is set up yet

To backup to the cloud, you need to:
1. Create a repository on GitHub or GitLab
2. Connect it to this project

Would you like help setting this up? I can guide you through:
• Creating a GitHub account (if needed)
• Creating a new repository
• Connecting it to your project

Say "help me set up GitHub backup" to continue.
```

---

## Workflow 2: Small Business Owner - Daily Backup Routine

**Persona:** Coffee shop owner maintaining a website

**Scenario:** Mike updates his menu and wants to backup changes

### Interaction

```
Mike: "what changed today?"

Easy Git:
Here's what changed since your last snapshot:

Modified files:
• menu.html (45 lines changed)
• styles.css (8 lines changed)

New files:
• images/new-latte.jpg

Summary: 2 files modified, 1 file added

Git context: These are "uncommitted changes" - save a snapshot to preserve them.

---

Mike: "make this safe"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update menu with new latte and seasonal items" (git commit)

Files saved:
• Modified: menu.html, styles.css
• Added: images/new-latte.jpg

Git context: This is called "committing" - you can always return to this exact point.

---

Mike: "backup to the cloud"

Easy Git:
✓ Backed up your work to the cloud

What I did:
• Uploaded 1 snapshot to cloud storage (git push origin main)

Snapshot backed up:
• "Update menu with new latte and seasonal items"

Git context: This is called "pushing" - your work is now safe on the remote server.
```

---

## Workflow 3: Content Creator - Publishing Workflow

**Persona:** Blogger preparing a new post

**Scenario:** Emma writes a blog post, reviews changes, and publishes

### Interaction

```
Emma: "show me what I wrote today"

Easy Git:
Here's what changed since your last snapshot:

Modified files:
• posts/2026-01-new-year-tips.md (127 lines added)
• index.html (3 lines changed)

New files:
• images/newyear-header.jpg
• images/tips-graphic.png

Summary: 2 files modified, 2 files added

Git context: These are "uncommitted changes" - save a snapshot to preserve them.

---

Emma: "save this milestone"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Add New Year tips blog post with graphics" (git commit)

Files saved:
• Modified: posts/2026-01-new-year-tips.md, index.html
• Added: images/newyear-header.jpg, images/tips-graphic.png

Git context: This is called "committing" - you can always return to this exact point.

---

Emma: "label this as ready to publish"

Easy Git:
✓ Labeled this version as "ready-to-publish"

What I did:
• Created version label "ready-to-publish" (git tag ready-to-publish)

This label points to:
• Snapshot: "Add New Year tips blog post with graphics"

Would you like to backup this label to the cloud? Say "yes" or "backup tag"

Git context: This is called "tagging" - you can always return to this named version.

---

Emma: "sync to my website server"

Easy Git:
✓ Backed up your work to the cloud

What I did:
• Uploaded 1 snapshot to cloud storage (git push origin main)
• Uploaded version label "ready-to-publish" (git push origin ready-to-publish)

Snapshot backed up:
• "Add New Year tips blog post with graphics"

Git context: This is called "pushing" - your work and labels are now on the remote server.
```

---

## Workflow 4: Hobbyist - Experimentation Workflow

**Persona:** Arduino hobbyist trying different LED patterns

**Scenario:** James tries different code versions and wants to save working states

### Interaction

```
James: "checkpoint this - the LED pattern works!"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Add working rainbow LED pattern with smooth transitions" (git commit)

Files saved:
• Modified: led_controller.ino

Git context: This is called "committing" - you can always return to this exact point.

---

James: "label this as working"

Easy Git:
✓ Labeled this version as "working"

What I did:
• Created version label "working" (git tag working)

This label points to:
• Snapshot: "Add working rainbow LED pattern with smooth transitions"

Git context: This is called "tagging" - you can always return to this named version.

---

[James tries a new pattern that doesn't work]

James: "what did I change that broke it?"

Easy Git:
Here's what changed since your last snapshot:

Modified files:
• led_controller.ino (23 lines changed)
  - Changed: timing values in rainbow function
  - Changed: color calculation algorithm
  - Added: debug logging statements

Summary: 1 file modified

Git context: These are "uncommitted changes" - you can discard them to go back to the working version.

---

James: "go back to the working version"

Easy Git:
✓ Restored to version "working"

What I did:
• Discarded uncommitted changes (git restore .)
• Now at tagged version "working"

Git context: Your files now match the snapshot labeled "working". Your broken changes are gone.
```

---

## Workflow 5: Product Manager - Sprint Workflow

**Persona:** PM tracking sprint deliverables

**Scenario:** Alex manages sprint work and creates releases

### Interaction

```
Alex: "save this iteration"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Complete user authentication and profile features" (git commit)

Files saved:
• Modified: src/auth.js, src/profile.js, README.md
• Added: tests/auth.test.js

Git context: This is called "committing" - you can always return to this exact point.

---

Alex: "sync with the team"

Easy Git:
✓ Synced with team

What I did:
• Downloaded latest updates (git pull)
• Uploaded your changes (git push origin main)

Updates received:
• "Fix navigation bug" (by Sarah)
• "Update API documentation" (by Mike)

Your changes shared:
• "Complete user authentication and profile features"

Git context: You're now in sync with the team - everyone has the same code.

---

Alex: "mark this as sprint-12 complete"

Easy Git:
✓ Labeled this version as "sprint-12-complete"

What I did:
• Created version label "sprint-12-complete" (git tag sprint-12-complete)
• Backed up label to cloud (git push origin sprint-12-complete)

This label points to:
• Snapshot: "Complete user authentication and profile features"

Git context: This is called "tagging" - you can always see what was delivered in sprint 12.

---

Alex: "what's in this release?"

Easy Git:
Changes since last release (sprint-11-complete → sprint-12-complete):

Commits:
• "Complete user authentication and profile features"
• "Fix navigation bug"
• "Update API documentation"
• "Add password reset flow"
• "Implement user profile editing"

Files changed:
• 12 files modified
• 5 files added
• 78 insertions, 23 deletions

Git context: This shows everything delivered between the two tagged versions.
```

---

## Workflow 6: Product Designer - Design Iteration Workflow

**Persona:** Designer versioning prototypes

**Scenario:** Maya explores different design directions

### Interaction

```
Maya: "save this exploration"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Explore minimalist homepage layout with card-based design" (git commit)

Files saved:
• Modified: homepage.html, styles/homepage.css
• Added: designs/minimalist-exploration.fig

Git context: This is called "committing" - you can always return to this exact point.

---

Maya: "label this as exploration-A"

Easy Git:
✓ Labeled this version as "exploration-A"

What I did:
• Created version label "exploration-A" (git tag exploration-A)

This label points to:
• Snapshot: "Explore minimalist homepage layout with card-based design"

Git context: This is called "tagging" - you can always return to this named version.

---

[Maya tries a different design direction]

Maya: "version this prototype"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Try bold colorful homepage with hero image" (git commit)

Files saved:
• Modified: homepage.html, styles/homepage.css
• Added: designs/colorful-exploration.fig, images/hero-image.jpg

Git context: This is called "committing" - you can always return to this exact point.

---

Maya: "tag this as exploration-B"

Easy Git:
✓ Labeled this version as "exploration-B"

What I did:
• Created version label "exploration-B" (git tag exploration-B)

This label points to:
• Snapshot: "Try bold colorful homepage with hero image"

Git context: This is called "tagging" - you can always return to this named version.

---

Maya: "what's different between exploration-A and exploration-B?"

Easy Git:
Comparing exploration-A → exploration-B:

Files changed:
• homepage.html (45 lines changed)
  - Changed: layout structure from cards to hero
  - Added: hero section with full-width image
  - Removed: card grid layout

• styles/homepage.css (67 lines changed)
  - Changed: color scheme from minimalist to bold
  - Added: hero image styling
  - Added: gradient overlays

• New file: images/hero-image.jpg
• New file: designs/colorful-exploration.fig

Summary: Shifted from minimalist card-based to bold hero-driven design

Git context: This shows the differences between your two tagged explorations.

---

Maya: "which one did the team like? go back to exploration-A"

Easy Git:
✓ Restored to version "exploration-A"

What I did:
• Switched to tagged version "exploration-A" (git checkout exploration-A)

Current state:
• Back to: "Explore minimalist homepage layout with card-based design"
• exploration-B is still saved - you can return to it anytime

Git context: Your files now show the minimalist exploration. Both versions are preserved.
```

---

## Workflow 7: Collaboration - Handling Conflicts

**Persona:** Two writers collaborating on a document

**Scenario:** Both edit the same file, need to resolve conflict

### Interaction

```
Alice: "save my edits"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Revise introduction and add examples" (git commit)

Files saved:
• Modified: introduction.md

Git context: This is called "committing" - you can always return to this exact point.

---

Alice: "sync with the team"

Easy Git:
⚠ Your local work conflicts with cloud version

What happened: Both you and Bob changed the same parts of these files:
• introduction.md (lines 12-25)

Bob's changes:
• Rewrote opening paragraph
• Added statistics

Your changes:
• Rewrote opening paragraph differently
• Added different examples

Options:
1. "keep my version" - Use your changes (discard Bob's)
2. "use cloud version" - Use Bob's changes (discard yours)
3. "show me the conflicts" - See exactly what's different
4. "help me fix it" - Guide me through manual resolution

Git context: This is a "merge conflict" - git can't automatically combine the changes.

---

Alice: "show me the conflicts"

Easy Git:
Conflict in introduction.md (lines 12-25):

<<<<<<< HEAD (your version)
Our platform revolutionizes content creation by providing
AI-powered tools that enhance creativity. Writers report
40% faster completion times with our system.
=======
Our platform transforms how content is created through
innovative AI assistance. Recent studies show users are
35% more productive when using our tools.
>>>>>>> origin/main (Bob's version)

Both versions:
• Rewrite the opening paragraph
• Add supporting data

Differences:
• You say "revolutionizes", Bob says "transforms"
• You focus on "creativity", Bob focuses on "innovation"
• You cite "40% faster", Bob cites "35% more productive"

Suggestion: The messages are similar - you could combine the best parts.

What would you like to do?
1. "keep my version"
2. "use Bob's version"
3. "I'll edit it manually" - combine both

Git context: You need to decide which version to keep, or manually merge them.

---

Alice: "I'll edit it manually"

Easy Git:
💡 To manually resolve:

1. Open introduction.md in your editor
2. Find the conflict markers: <<<<<<<, =======, >>>>>>>
3. Delete the markers and edit the content to combine both versions
4. Save the file
5. Tell me when done: "I fixed the conflict"

Tip: You can keep parts from both versions - just make sure to remove all the marker lines.

Git context: This is manual conflict resolution - you're creating the best version from both.

---

Alice: "I fixed the conflict"

Easy Git:
✓ Conflict resolved and synced

What I did:
• Marked conflict as resolved (git add introduction.md)
• Created merge commit (git commit)
• Synced with team (git push origin main)

Your merged version is now the official version.

Git context: The conflict is resolved - everyone now has your combined version.
```

---

## Workflow 8: Multi-Device Sync

**Persona:** Developer working from laptop and desktop

**Scenario:** Switching between computers during the day

### Interaction (Laptop - Morning)

```
User: "save my morning work"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Implement search feature with filters" (git commit)

Files saved:
• Modified: src/search.js, src/filters.js
• Added: tests/search.test.js

Git context: This is called "committing" - you can always return to this exact point.

---

User: "backup to cloud"

Easy Git:
✓ Backed up your work to the cloud

What I did:
• Uploaded 1 snapshot to cloud storage (git push origin main)

Snapshot backed up:
• "Implement search feature with filters"

Git context: This is called "pushing" - your work is now safe on the remote server.
```

### Interaction (Desktop - Afternoon)

```
User: "get my latest work"

Easy Git:
✓ Downloaded latest updates from cloud

What I did:
• Synced with cloud storage (git pull)

Updates received:
• "Implement search feature with filters" (from your laptop)

Files changed:
• Modified: src/search.js, src/filters.js
• Added: tests/search.test.js

Git context: This is called "pulling" - you now have your laptop work on your desktop.

---

User: "save my afternoon progress"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Add pagination to search results" (git commit)

Files saved:
• Modified: src/search.js
• Added: src/pagination.js

Git context: This is called "committing" - you can always return to this exact point.

---

User: "sync up"

Easy Git:
✓ Backed up your work to the cloud

What I did:
• Uploaded 1 snapshot to cloud storage (git push origin main)

Snapshot backed up:
• "Add pagination to search results"

Git context: This is called "pushing" - your desktop work is now on the server.
```

---

## Workflow 9: Going Back in Time

**Persona:** User who wants to see or restore an old version

**Scenario:** Need to check what was in an old version

### Interaction

```
User: "show me my history"

Easy Git:
Here's your project history (most recent first):

1. "Add pagination to search results" (2 hours ago)
2. "Implement search feature with filters" (6 hours ago)
3. "Update homepage design" (yesterday)
4. "Fix navigation bug" (2 days ago)
5. "Initial project setup" (1 week ago)

Git context: This is your commit history - every snapshot you've saved.

To see an old version: "show me version X" or "go back to [description]"

---

User: "what was in 'Update homepage design'?"

Easy Git:
Snapshot: "Update homepage design" (from yesterday)

Files changed:
• Modified: homepage.html (45 lines)
• Modified: styles/home.css (23 lines)
• Added: images/banner.jpg

Changes:
• Added hero banner section
• Updated color scheme to blue/white
• Simplified navigation menu

To view this version: "show me this version"
To restore this version: "go back to this version"

Git context: This shows what changed in that commit.

---

User: "I need to see what the homepage looked like then"

Easy Git:
✓ Viewing old version: "Update homepage design"

What I did:
• Switched to viewing that snapshot (git checkout [commit-hash])

⚠ You're in "view-only" mode (detached HEAD)

Your files now show how they looked yesterday. You can:
• Look at the files
• Copy code you need
• Compare with current version

To get back to current work: "return to present" or "go back to main"

Git context: You're viewing history - any changes you make won't be saved unless you create a new branch.

---

User: "return to present"

Easy Git:
✓ Back to current work

What I did:
• Returned to main timeline (git checkout main)

You're now at: "Add pagination to search results" (your latest work)

Git context: You're back to your current work - time travel complete!
```

---

## Workflow 10: Error Recovery

**Persona:** User who made a mistake

**Scenario:** Accidentally committed wrong files

### Interaction

```
User: "save everything"

Easy Git:
✓ Saved a snapshot of your work

What I did:
• Staged all changes (git add -A)
• Created snapshot: "Update project files" (git commit)

Files saved:
• Modified: src/app.js
• Added: secret-keys.txt
• Added: node_modules/* (1,247 files)

Git context: This is called "committing" - you can always return to this exact point.

---

User: "oh no! I didn't mean to save secret-keys.txt or node_modules!"

Easy Git:
💡 Don't worry - we can fix this!

You committed files you didn't mean to. Options:

1. "undo that commit" - Remove the commit completely (keeps files)
2. "remove those files from commit" - Keep commit but exclude those files
3. "start over from previous snapshot" - Go back to before this commit

Recommendation: Option 2 - we can remove just those files from the commit.

Git context: Commits can be modified before you upload them to the cloud.

---

User: "remove those files from commit"

Easy Git:
✓ Fixed the commit

What I did:
• Removed last commit (git reset HEAD~1)
• Added .gitignore for secret-keys.txt and node_modules/
• Re-staged only the right files (git add src/)
• Created new commit: "Update application code" (git commit)

Files now in commit:
• Modified: src/app.js

Files excluded:
• secret-keys.txt (now ignored)
• node_modules/* (now ignored)

Git context: The mistake is fixed - those files won't be tracked anymore.

---

User: "backup to cloud"

Easy Git:
✓ Backed up your work to the cloud

What I did:
• Uploaded 1 snapshot to cloud storage (git push origin main)

Snapshot backed up:
• "Update application code"

Security note: secret-keys.txt was never uploaded - your secrets are safe.

Git context: This is called "pushing" - only the correct files are on the remote server.
```

---

## Workflow 11: Learning Easy Git

**Persona:** New user discovering Easy Git

**Scenario:** User wants to understand what Easy Git can do before using it

### Interaction

```
User: "tell me about Easy Git"

Easy Git:
💡 Easy Git makes version control simple

I translate everyday language into git operations - no git knowledge required!

What I can do:

📸 Save snapshots
• "save my progress" - Create a checkpoint of your work
• "checkpoint this" - Freeze this version

🔍 Show changes
• "what changed?" - See what you modified
• "show my changes" - List your edits

🚫 Check ignored files
• "what's not being uploaded?" - See excluded files
• "what's in gitignore" - Show ignored patterns

☁️ Backup to cloud
• "backup to cloud" - Upload your work to GitHub/GitLab
• "sync up" - Send changes to server

⬇️ Get updates
• "get latest" - Download from cloud
• "sync down" - Get team's changes

🏷️ Label versions
• "mark this as v1.0" - Name important versions
• "tag as release" - Create milestone markers

🎬 Start tracking
• "start version control" - Begin tracking changes
• "initialize tracking" - Set up version history

Common workflows:
• Daily backup: "what changed?" → "save my progress" → "backup to cloud"
• Multi-device: "backup my work" on device 1 → "get latest" on device 2

Want details on a specific operation? Ask: "how do I backup" or "explain saving"

---

User: "how do I backup to the cloud?"

Easy Git:
💡 Backing up your work to the cloud

What it does:
Uploads your saved snapshots to a remote server (GitHub, GitLab, etc.) so you can:
• Access your work from multiple devices
• Protect against local computer failure
• Collaborate with others

How to use it:
1. First, save a snapshot: "save my progress"
2. Then backup: "backup to cloud"
3. Easy Git will:
   • Check if cloud storage is set up (helps you configure if needed)
   • Upload all your saved snapshots to the server
   • Confirm what was backed up

Alternative phrases:
• "backup to cloud"
• "sync up"
• "upload my work"
• "send to backup"
• "push to cloud"

Git context: This is called "pushing" - it sends your commits to a remote
repository where they're safely stored and accessible from anywhere.

Common workflow:
Make changes → "what changed?" → "save my progress" → "backup to cloud"

Important: You must save a snapshot before backing up. The backup sends your
saved snapshots, not unsaved changes.

Ready to try it? Say: "backup to cloud"

---

User: "what should I do now?"

Easy Git:
💡 You're not tracking versions yet

Current state: This project doesn't have version control set up.

What you can do now:
1. "start version control" - Begin tracking your changes

Once initialized, you'll be able to:
• Save snapshots of your work
• Go back to earlier versions
• Backup to the cloud

Want to learn more? Ask: "tell me about Easy Git"

---

User: "start version control"

Easy Git:
✓ Started tracking your project!

What I did:
• Initialized version control (git init)
• Configured git with your name and email

Next steps:
• Save a snapshot: "save my progress"
• Check what changed: "what changed?"
• Backup to cloud: "backup to cloud" (requires GitHub/GitLab setup)

Git context: You now have a hidden .git folder that tracks all your changes.

---

User: "what should I do now?"

Easy Git:
💡 Ready to save your first snapshot

Current state: Version control is set up, but you haven't saved anything yet.

What you can do now:
1. "what changed?" - See what files are in your project
2. "save my progress" - Create your first snapshot

This will start tracking your project history!

Want to learn more about saving? Ask: "how do I save work"
```

---

## Common Patterns

### Pattern 1: Save and Backup (Most Common)
```
User: "backup my work"
→ Auto-chain: COMMIT (if changes) → PUSH
```

### Pattern 2: Sync Before Work
```
User: "get latest before I start"
→ PULL → STATUS (to see what came down)
```

### Pattern 3: Check Before Commit
```
User: "what did I do today?"
→ STATUS → "save it" → COMMIT
```

### Pattern 4: Milestone + Label
```
User: "save this as version 1.0"
→ COMMIT → TAG → PUSH (commit and tag)
```

### Pattern 5: Multi-Device Workflow
```
Device 1: COMMIT → PUSH
Device 2: PULL → work → COMMIT → PUSH
Device 1: PULL
```
