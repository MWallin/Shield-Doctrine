# Git Workflow for Writers

A simple, practical guide for using Git and GitHub to version your book writing.

## Core Philosophy: Keep It Simple

As a writer first, your Git workflow should be **invisible most of the time** and only noticeable when you need it. This guide gives you a simple daily routine plus tools for when things get complex.

---

## Your Daily Writing Workflow

### The Basic Rhythm

1. **Start your writing session**
   ```bash
   git pull origin main
   ```
   This gets any changes from other machines or collaborators.

2. **Write** (this is the important part!)

3. **Save your work regularly**
   ```bash
   git add .
   git commit -m "Chapter 3: Added confrontation scene"
   ```

4. **End your session**
   ```bash
   git push origin main
   ```

That's it for 90% of your writing days.

### What Makes a Good Commit?

Think of commits like bookmarks in your writing journey. Make one when you've completed something meaningful:

- ✅ "Finished Chapter 3 first draft"
- ✅ "Added backstory for Marcus"
- ✅ "Revised opening scene - stronger hook"
- ✅ "Worldbuilding: Added magic system rules"
- ❌ "Changed stuff" (too vague)
- ❌ "asdf" (meaningless)

**Frequency:** Commit every 30-60 minutes of focused writing, or whenever you finish a logical chunk (scene, character profile, major revision).

---

## Working Across Multiple Machines

### The Golden Rule
**Always pull before you start, always push when you finish.**

### The Complete Multi-Machine Workflow

**On Machine A (morning writing):**
```bash
git pull origin main          # Get latest
# ... write ...
git add .
git commit -m "Chapter 5: First half drafted"
git push origin main          # Share your work
```

**On Machine B (evening writing):**
	```bash
	git pull origin main          # Get what you did this morning
	# ... write ...
	git add .
	git commit -m "Chapter 5: Completed and revised"
	git push origin main
	```

**Working with Claude or other tools:**
Same principle - Claude works on the `claude/*` branches and you work on `main`, but you can merge Claude's work when ready.

### What If You Forget to Pull?

If you start writing without pulling and Git complains when you try to push:

```bash
git pull --rebase origin main
git push origin main
```

The `--rebase` option replays your local changes on top of the remote changes. It usually works smoothly for text files.

---

## Branching Strategy: Simple and Effective

### Main Branch (`main`)
- Your **single source of truth**
- Always keep it in a "working" state
- All your completed writing lives here
- This is what you pull from and push to daily

### Feature Branches (when you need them)
Use branches for **experimental work** or **major changes** you're not sure about:

```bash
# Create a branch for a major revision
git checkout -b revision/darker-tone

# Write and commit on this branch
git add .
git commit -m "Experimenting with darker tone in Act 2"

# When happy, merge it back
git checkout main
git merge revision/darker-tone
git push origin main

# Delete the branch (locally and remotely)
git branch -d revision/darker-tone
git push origin --delete revision/darker-tone
```

### When to Use Branches

**DO use branches for:**
- Major structural changes you might abandon
- Experimental rewrites
- Alternative endings/versions you want to compare
- Big revisions where you want to preserve the original

**DON'T use branches for:**
- Daily writing
- Small edits or revisions
- Normal chapter progression
- Minor character tweaks

**Simple rule:** If you're not sure whether you'll keep the changes, use a branch. Otherwise, work on `main`.

### Branch Naming for Writers

Keep it descriptive and simple:
- `revision/act-one-pacing`
- `experiment/first-person-pov`
- `alternative/different-ending`
- `draft/complete-rewrite-ch4`

---

## Tags: Marking Milestones

Tags are like **bookmarks for major milestones**. They mark a specific point in your book's history that you might want to return to.

### When to Create Tags

- First complete draft of the book
- Each revision pass
- Before major structural changes
- Beta reader versions
- Submission versions

### How to Create Tags

```bash
# Finish your first draft
git add .
git commit -m "Completed first draft of all chapters"

# Tag it
git tag -a v1.0-first-draft -m "Complete first draft - 85,000 words"

# Push the tag to GitHub
git push origin v1.0-first-draft
```

### Tag Naming Convention

Use a simple, descriptive system:

```
v1.0-first-draft
v1.1-revision-pass-1
v1.2-revision-pass-2
v2.0-structural-revision
v3.0-beta-reader-draft
v4.0-final-draft
v4.1-copyedits
v5.0-submission
```

The numbers help you track progress, and the labels tell you what that version was.

### Viewing Your Tags

```bash
# List all tags
git tag

# See details of a specific tag
git show v1.0-first-draft

# Return to a tagged version (just to look)
git checkout v1.0-first-draft

# Return to current work
git checkout main
```

---

## Releases: Major Versions

GitHub Releases are tags with extra documentation. Use them for truly significant milestones.

### When to Create a Release

- First complete draft
- Major revision milestones
- Beta reader versions
- Final submission version

### How to Create a Release

1. **Via GitHub website** (easiest):
   - Go to your repository on GitHub
   - Click "Releases" → "Create a new release"
   - Choose a tag (or create new): `v1.0-first-draft`
   - Write release notes:
     ```
     First Draft Complete

     - All 25 chapters drafted
     - 85,000 words
     - Main plot arcs complete
     - Known issues: Pacing in Act 2, character development for Sarah
     ```
   - Click "Publish release"

2. **Via command line** (if you prefer):
   ```bash
   # Create and push a tag first
   git tag -a v1.0-first-draft -m "First complete draft"
   git push origin v1.0-first-draft

   # Then create release via gh CLI or GitHub website
   ```

### What to Include in Release Notes

- Word count
- What's complete
- Known issues or areas needing work
- Major changes since last release
- Notes for beta readers (if applicable)

---

## Handling Common Scenarios

### "I want to try a completely different approach to Chapter 7"

```bash
# Create a branch
git checkout -b experiment/chapter7-rewrite

# Make your changes
# ... write ...

# Commit
git add .
git commit -m "Experimental rewrite of Chapter 7"

# If you like it, merge
git checkout main
git merge experiment/chapter7-rewrite

# If you don't like it, just abandon it
git checkout main
# The branch still exists if you want to revisit
```

### "I want to see what my book looked like 2 weeks ago"

```bash
# Find the commit from 2 weeks ago
git log --since="2 weeks ago" --until="13 days ago"

# Checkout that commit (note the hash)
git checkout abc1234

# Look around, read files
# When done, return to present
git checkout main
```

### "I accidentally deleted a whole chapter!"

```bash
# If you haven't committed the deletion yet
git restore chapters/chapter-7.md

# If you committed it
git log -- chapters/chapter-7.md  # Find when it existed
git checkout abc1234 -- chapters/chapter-7.md  # Restore from that commit
```

### "I want to compare two versions of my opening"

```bash
# Compare current version with a previous commit
git diff abc1234 chapters/chapter-1.md

# Or use a visual diff tool
git difftool abc1234 chapters/chapter-1.md
```

---

## Best Practices for Writers

### 1. Commit Messages Tell Your Story
Your commit history is the story of your book's creation. Make it readable:

```bash
# Good commit messages
git commit -m "Chapter 3: Added foreshadowing for final reveal"
git commit -m "Characters: Expanded Marcus backstory with military service"
git commit -m "Worldbuilding: Defined magic system limitations"
git commit -m "Revision: Tightened pacing in Act 2"

# Bad commit messages
git commit -m "updates"
git commit -m "fixes"
git commit -m "chapter stuff"
```

### 2. Don't Commit Sensitive Info
Add to `.gitignore`:
```
# Personal notes you don't want public
private-notes.md
journal.md

# System files
.DS_Store
Thumbs.db

# Editor files
*.swp
*~
.vscode/
```

### 3. README for Context
Keep a README.md that explains your project:
```markdown
# Shield Doctrine

A military science fiction novel about...

## Status
Currently on second draft, targeting 90,000 words.

## Structure
- `chapters/` - Main manuscript
- `characters/` - Character profiles and development
- `world-building/` - Setting, technology, politics
- `research/` - Reference materials
```

### 4. Use Issues for Tracking
Create GitHub Issues for:
- Plot holes to fix
- Character inconsistencies
- Research needed
- Beta reader feedback

### 5. Regular Backups
GitHub IS a backup, but consider:
- Keep a local backup on external drive
- Export major milestones to PDF/Word
- Cloud storage for extra redundancy

---

## Quick Reference Card

### Daily Commands
```bash
git pull origin main           # Start session
git add .                       # Stage changes
git commit -m "message"         # Save checkpoint
git push origin main            # End session
```

### Milestone Commands
```bash
git tag -a v1.0-draft -m "First draft"     # Create tag
git push origin v1.0-draft                  # Push tag
```

### Branching Commands
```bash
git checkout -b branch-name              # Create branch
git checkout main                        # Switch to main
git merge branch-name                    # Merge branch
git branch -d branch-name                # Delete branch
```

### Emergency Commands
```bash
git restore filename                # Undo uncommitted changes
git log                            # See history
git diff                          # See what changed
```

---

## Your Workflow Checklist

Print this and keep it by your desk:

**Starting a writing session:**
- [ ] `git pull origin main`
- [ ] Check `git status` to see where you are

**During writing:**
- [ ] Save files normally
- [ ] Commit every 30-60 minutes or after meaningful chunks
- [ ] Use clear commit messages

**Ending a writing session:**
- [ ] `git add .`
- [ ] `git commit -m "Description of what you did"`
- [ ] `git push origin main`

**Weekly:**
- [ ] Review your commit history (`git log --oneline`)
- [ ] Clean up any branches you're done with

**At major milestones:**
- [ ] Create a tag for the milestone
- [ ] Create a GitHub Release with notes
- [ ] Consider backing up to external storage

---

## Advanced Topics (For Later)

Once you're comfortable with the basics, you might explore:

- **Collaborating with editors**: Branches and pull requests
- **Multiple versions**: Maintaining different editions simultaneously
- **Automated backups**: GitHub Actions to backup to other services
- **Writing analytics**: Scripts to track word count over time
- **Manuscript compilation**: Scripts to compile chapters into single document

But start simple. Master the daily workflow first.

---

## Getting Help

- Check `git status` when confused - it often tells you what to do
- Google error messages - they're usually common
- Ask your friendly AI assistant (that's me!)

Remember: Git is a tool to serve your writing, not the other way around. Keep it simple and let it fade into the background so you can focus on what matters - the words.
