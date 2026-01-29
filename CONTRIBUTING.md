# Contributing to Easy Git

Thank you for your interest in improving Easy Git! This guide will help you contribute effectively.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. **Check existing issues** to avoid duplicates
2. **Create a new issue** with:
   - Clear title describing the problem
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment (OS, Claude Code version, git version)

### Suggesting Features

For new feature ideas:

1. **Describe the use case** - who needs this and why
2. **Provide examples** - how would users interact with it
3. **Consider scope** - does it fit the "simple git for non-technical users" mission
4. **Check persona fit** - which persona(s) would use this

### Submitting Changes

#### 1. Fork and Clone

```bash
git clone https://github.com/peterkaminski/easy-git.git
cd easy-git
```

#### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-description
```

#### 3. Make Changes

Follow these guidelines:

**Adding Language Patterns:**
- Add to appropriate persona in `skills/easy-git/references/personas.md`
- Include in trigger phrases in `skills/easy-git/SKILL.md` frontmatter
- Add example interaction to `skills/easy-git/examples/workflows.md`

**Improving Commit Messages:**
- Modify analysis logic in SKILL.md under "Smart commit message generation"
- Test with various file types and change patterns
- Document examples

**Enhancing Error Handling:**
- Add error scenario to SKILL.md
- Provide plain-language explanation
- Offer actionable solutions
- Update git-primer.md if introducing new concepts

**Adding Git Operations:**
- Document in SKILL.md as new capability
- Add plain-language explanation to git-primer.md
- Create workflow examples in workflows.md
- Consider if it fits v1.0 scope (linear history, single branch)

#### 4. Test Your Changes

**Manual Testing:**
```bash
# Install locally
ln -s $(pwd) ~/.claude/plugins/easy-git-test

# Test in Claude Code
# Try all affected trigger phrases
# Verify output format matches standards
# Check error handling
```

**Test Checklist:**
- [ ] Trigger phrases work correctly
- [ ] Output follows format (✓/⚠/💡 + description + what I did + git context)
- [ ] Git commands shown in parentheses
- [ ] Plain language explanations are clear
- [ ] Error cases handled gracefully
- [ ] Works for target persona(s)

#### 5. Document Changes

Update relevant files:
- README.md (if user-facing feature)
- SKILL.md (if logic/capability changes)
- personas.md (if adding language patterns)
- git-primer.md (if new git concepts)
- workflows.md (if new interaction patterns)
- CHANGELOG.md (add entry for your change)

#### 6. Commit and Push

```bash
git add .
git commit -m "Add [feature]: brief description"
git push origin feature/your-feature-name
```

**Commit Message Guidelines:**
- Use present tense: "Add feature" not "Added feature"
- Be specific: "Add support for stash operations" not "Update SKILL.md"
- Reference issues: "Fix #123: Handle detached HEAD state"

#### 7. Create Pull Request

1. Go to GitHub and create a pull request
2. Fill out the template:
   - **What**: What does this PR do
   - **Why**: Why is this needed
   - **How**: How does it work
   - **Testing**: How you tested it
   - **Checklist**: Complete the checklist

## Development Guidelines

### Code Style

**SKILL.md:**
- Use clear, descriptive headings
- Include examples for complex concepts
- Format bash commands in code blocks
- Use bullet lists for steps

**Documentation:**
- Write for non-technical users
- Use analogies and plain language
- Include "Git context" explanations
- Provide specific examples

**Workflows:**
- Show complete interactions
- Include realistic personas
- Cover happy path and errors
- Format consistently

### Language Principles

**Plain Language:**
- Avoid jargon (unless explaining it)
- Use active voice
- Be concise but complete
- Relate to everyday experiences

**User Focus:**
- Prioritize user's mental model
- Meet them where they are
- Don't force git terminology
- Teach git concepts gradually

**Error Messages:**
- Explain what happened in user terms
- Provide specific next steps
- Offer multiple solutions when possible
- Include git context for learning

### Design Principles

**Scope:**
- Stay focused on linear history workflow
- Single branch (main/master) for v1.0
- Simple collaboration (push/pull)
- Common operations only

**User Experience:**
- Trust natural language - execute directly
- Auto-generate commit messages
- Always show what was done
- Provide learning opportunities

**Error Handling:**
- Detect problems early
- Explain clearly
- Guide to resolution
- Prevent data loss

## Project Structure

```
easy-git/
├── .claude-plugin/
│   └── plugin.json          # Plugin metadata
├── skills/
│   └── easy-git/
│       ├── SKILL.md          # Main skill logic
│       ├── references/
│       │   ├── personas.md   # Language patterns
│       │   └── git-primer.md # Git concepts
│       └── examples/
│           └── workflows.md  # Example interactions
├── README.md                 # User documentation
├── CONTRIBUTING.md          # This file
├── LICENSE                  # MIT License
└── CHANGELOG.md            # Version history
```

## Areas for Contribution

### High Priority
- Additional persona language patterns
- Better commit message generation algorithms
- More comprehensive error handling
- Edge case coverage

### Medium Priority
- Internationalization (i18n)
- Additional workflow examples
- Performance optimizations
- Test suite

### Future Enhancements
- Branching support (v2.0)
- Interactive rebase (advanced)
- Stash operations
- Submodule support

## Questions?

- **General questions**: Open a discussion on GitHub
- **Bug reports**: Create an issue
- **Feature ideas**: Create an issue with [Feature Request] tag
- **Documentation unclear**: Create an issue or submit a PR

## Recognition

Contributors will be:
- Listed in README.md
- Credited in CHANGELOG.md
- Thanked profusely!

Thank you for helping make git accessible to everyone! 🎉
