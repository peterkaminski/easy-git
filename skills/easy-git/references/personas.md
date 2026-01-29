# Personas and Language Patterns

This guide maps natural language phrases to git operations across different user personas. Use this to understand the variety of ways users might express the same intent.

## Persona Profiles

### 1. Creative Professional (Writer, Designer, Photographer)

**Mental Model:** Drafts, versions, backups, "saving work"

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save this version", "save this draft", "freeze this version", "create a checkpoint", "snapshot this", "save my edits" |
| STATUS | "what changed in my draft", "show differences", "what did I edit", "what's new in this version" |
| PUSH | "back this up", "save to backup", "protect this version", "upload this" |
| PULL | "get the latest draft", "sync with backup", "download latest version" |
| TAG | "mark as final", "label this version", "name this draft", "mark as v2" |
| INIT | "start tracking my work", "begin saving versions" |

**Characteristics:**
- Thinks in terms of drafts and final versions
- Concerned about "not losing work"
- May work on multiple devices
- Values simplicity over technical accuracy

**Example Interactions:**
```
User: "save this draft"
→ COMMIT

User: "what did I change in my writing?"
→ STATUS

User: "back up my photos"
→ PUSH (after commit if needed)
```

---

### 2. Small Business Owner

**Mental Model:** Security, backups, recovery, "don't lose stuff"

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save everything", "make this safe", "create backup point", "secure this" |
| STATUS | "what's different", "show me changes", "what's new" |
| PUSH | "backup to cloud", "send to safe place", "upload backup", "protect online" |
| PULL | "get latest from backup", "restore from cloud", "download safe copy" |
| TAG | "mark as stable", "label working version", "mark as production" |
| INIT | "start protecting my files", "begin tracking" |

**Characteristics:**
- Focused on safety and recovery
- May not understand technical terms
- Values peace of mind
- Wants simple, reliable processes

**Example Interactions:**
```
User: "make sure this is safe"
→ COMMIT + PUSH

User: "can I go back to yesterday's version?"
→ Explain log/checkout (advanced - might defer)

User: "backup everything to the cloud"
→ COMMIT + PUSH
```

---

### 3. Content Creator (Blogger, YouTuber)

**Mental Model:** Publishing, drafts, history, "going live"

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save milestone", "checkpoint progress", "save this state", "capture this version" |
| STATUS | "what's ready", "show unpublished changes", "what did I add", "what's different from published" |
| PUSH | "sync my work", "publish changes", "upload to server", "send to website" |
| PULL | "get latest content", "sync down", "download updates", "refresh local copy" |
| TAG | "mark as published", "label as episode-5", "tag as v1.0", "mark as launch" |
| INIT | "start tracking my content", "begin version control" |

**Characteristics:**
- Distinguishes between drafts and published content
- May collaborate with others
- Works on multiple pieces simultaneously
- Thinks in terms of releases/episodes

**Example Interactions:**
```
User: "save this milestone"
→ COMMIT

User: "what's ready to publish?"
→ STATUS (then explain what's committed vs pushed)

User: "sync my work to the server"
→ PUSH
```

---

### 4. Hobbyist/Maker

**Mental Model:** Progress, experiments, "try this out"

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save my progress", "checkpoint this experiment", "save working state", "snapshot this" |
| STATUS | "what did I try", "show what changed", "what's different from before" |
| PUSH | "backup my project", "save to cloud", "upload my work" |
| PULL | "get latest from backup", "sync from other computer", "download updates" |
| TAG | "mark working version", "label this config", "tag as working", "save as v1" |
| INIT | "start tracking changes", "begin saving versions" |

**Characteristics:**
- Experiments frequently
- Wants to try things without fear
- May work on hardware + software projects
- Values ability to "go back if it breaks"

**Example Interactions:**
```
User: "save this before I try something else"
→ COMMIT

User: "what did I change that broke it?"
→ STATUS + maybe diff

User: "label this as working"
→ TAG
```

---

### 5. Product Manager

**Mental Model:** Releases, iterations, sprints, deliverables, tracking

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save this iteration", "checkpoint sprint work", "record this decision", "snapshot deliverables" |
| STATUS | "what changed this sprint", "show current iteration", "what's in this release", "track changes" |
| PUSH | "sync to team", "share updates", "publish iteration", "backup sprint work" |
| PULL | "get team updates", "sync with main", "pull latest iteration" |
| TAG | "mark as sprint-12", "label as release-candidate", "tag as v2.1", "mark milestone" |
| INIT | "start tracking this project", "begin iteration tracking" |

**Characteristics:**
- Thinks in terms of sprints and releases
- Concerned with tracking decisions and progress
- May work with technical and non-technical stakeholders
- Values traceability and history

**Example Interactions:**
```
User: "record this decision"
→ COMMIT (maybe with custom message)

User: "what's in this release?"
→ STATUS or log between tags

User: "mark as sprint-12 complete"
→ TAG
```

---

### 6. Product Designer

**Mental Model:** Iterations, design versions, explorations, prototypes

**Common Language:**

| Intent | Phrases |
|--------|---------|
| COMMIT | "save this exploration", "checkpoint design", "version this prototype", "snapshot iteration", "save design state" |
| STATUS | "what changed in design", "show iterations", "what's different from last version", "track design changes" |
| PUSH | "sync design files", "backup prototypes", "share iteration", "upload designs" |
| PULL | "get latest designs", "sync with team", "download design updates" |
| TAG | "mark as final design", "label exploration-A", "tag as approved", "name this iteration" |
| INIT | "start tracking designs", "begin versioning prototypes" |

**Characteristics:**
- Works through multiple iterations rapidly
- May have parallel design explorations
- Collaborates with other designers and developers
- Values ability to compare versions
- Thinks in terms of iterations and explorations

**Example Interactions:**
```
User: "save this exploration"
→ COMMIT

User: "version this prototype"
→ COMMIT + TAG

User: "what changed from the last iteration?"
→ STATUS or diff

User: "label this as approved"
→ TAG
```

---

## Cross-Persona Language Superset

Common phrases that work across all personas:

### INIT (Start Tracking)
- "start tracking [changes/versions/this project]"
- "begin version control"
- "initialize versioning"
- "make this a versioned project"
- "start keeping history"
- "turn on tracking"

### COMMIT (Save Point)
- "save [snapshot/checkpoint/savepoint/version/progress]"
- "capture [this moment/current state/changes]"
- "freeze this version"
- "record [this/changes/progress]"
- "create [checkpoint/savepoint]"
- "make a snapshot"
- "checkpoint [this/prototype/iteration]"
- "save my work"

### STATUS (What Changed)
- "what [changed/is different/did I do/is new]"
- "show [my changes/changes/what changed/differences]"
- "what's [different/new/uncommitted]"
- "list changes"
- "show me my work"
- "what have I modified"
- "what files changed"

### PUSH (Upload/Backup)
- "backup [to cloud/to server/online]"
- "sync [up/to cloud/to server]"
- "upload [my work/changes/this]"
- "save to [cloud/server/backup/remote]"
- "publish [my changes/this version]"
- "send to backup"
- "push [to cloud/online]"

### PULL (Download/Sync Down)
- "get [latest/updates/changes from cloud]"
- "download [updates/latest version]"
- "sync [down/from cloud/from server]"
- "update from [backup/cloud/server/remote]"
- "refresh from server"
- "pull [latest/from cloud]"

### TAG (Label/Milestone)
- "[mark/label/bookmark/name/tag] this version"
- "create [milestone/marker/label]"
- "name this version [X]"
- "tag this as [X]"
- "mark as [release/milestone/version] [X]"

## Intent Recognition Patterns

### Context Clues

**Direction indicators:**
- "to cloud", "to server", "up", "online" → PUSH
- "from cloud", "from server", "down", "latest" → PULL

**Action types:**
- "what", "show", "list", "tell me" → STATUS
- "save", "record", "capture", "freeze" → COMMIT
- "mark", "label", "name", "tag" → TAG
- "start", "begin", "initialize" → INIT

**State references:**
- "this version", "this state", "right now" → COMMIT/TAG
- "what changed", "differences" → STATUS
- "backup", "safe", "protect" → PUSH

### Ambiguity Resolution

When intent is unclear:

1. **"save" → COMMIT or PUSH?**
   - Default to COMMIT
   - If mentions "cloud", "server", "backup" → PUSH
   - Can auto-chain: COMMIT then PUSH

2. **"sync" → PUSH or PULL?**
   - "sync up", "sync to" → PUSH
   - "sync down", "sync from" → PULL
   - "sync" alone → Ask or check if local is ahead/behind

3. **"what changed" → STATUS or DIFF?**
   - Default to STATUS (summary)
   - If asks for "details", "show me" → include diff output

4. **"version" → COMMIT or TAG?**
   - "save version", "version this" → COMMIT
   - "mark version", "label version [X]" → TAG
   - "version [name]" with name → TAG

## Testing Phrases by Persona

Use these to verify skill recognizes all persona-specific language:

**Creative:**
- ✓ "save this draft"
- ✓ "what changed in my writing"
- ✓ "back up my work"
- ✓ "label this as final"

**Business:**
- ✓ "make this safe"
- ✓ "backup to cloud"
- ✓ "protect this version"

**Content Creator:**
- ✓ "save milestone"
- ✓ "what's ready to publish"
- ✓ "sync to server"

**Maker:**
- ✓ "save my progress"
- ✓ "what did I try"
- ✓ "label as working"

**Product Manager:**
- ✓ "record this decision"
- ✓ "what's in this release"
- ✓ "mark as sprint-12"

**Product Designer:**
- ✓ "save this exploration"
- ✓ "version this prototype"
- ✓ "what changed from last iteration"

## Non-Matches (Should NOT Trigger)

These phrases should not trigger the skill:

- Git technical commands: "git commit", "git push" (handled by standard git tools)
- Branching: "create a branch", "merge branches" (out of scope for v1)
- File operations: "delete this file", "move this file" (file system, not git)
- Build/run: "run tests", "build the project" (separate concerns)
- General questions: "how does git work", "what is version control" (documentation)
