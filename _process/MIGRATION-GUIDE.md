# Shield Doctrine - Migration Guide

## Quick Summary

**Everything you need beyond regular Claude Code:** Just the Creative Writing Skills plugin

Your project is fully backed up and ready to migrate. This guide will help you set up Shield Doctrine on a new machine.

---

## Prerequisites on New Machine

### 1. Install Git
- **Windows:** Download from https://git-scm.com/
- **Mac:** `brew install git` or install Xcode Command Line Tools
- **Linux:** `sudo apt-get install git` (Ubuntu/Debian) or equivalent

### 2. Install Claude Code
Follow the standard installation instructions at https://claude.com/claude-code

### 3. Install Creative Writing Skills Plugin

**CRITICAL:** This project uses the Creative Writing Skills plugin for all story writing and worldbuilding documentation.

**Installation:**
```bash
claude install creative-writing-skills
```

This plugin provides specialized skills for:
- `cw-prose-writing` - Writing and editing story chapters
- `cw-official-docs` - Creating worldbuilding documentation
- `cw-story-critique` - Analyzing and providing feedback
- `cw-brainstorming` - Capturing creative exploration

**Without this plugin, you cannot effectively work on story content.**

---

## Migration Steps

### Step 1: Configure Git (If Not Already Configured)

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Step 2: Clone the Repository

```bash
# Navigate to where you want the project
cd ~/Documents  # or wherever you keep projects

# Clone from GitHub
git clone https://github.com/MWallin/Shield-Doctrine.git

# Enter the project directory
cd Shield-Doctrine
```

### Step 3: Verify the Clone

```bash
# Check that all files are present
git status

# Verify you're on the correct branch
git branch

# If you want to work on the current development branch:
git checkout consistency/stellar-republic-alignment
```

### Step 4: Configure Claude Code Permissions

The project has a `.claude/settings.local.json` file that configures permissions. This file is **already in the repository** and will be cloned with the project.

**Verify it exists:**
```bash
cat .claude/settings.local.json
```

This configuration allows Claude to:
- Automatically use Creative Writing Skills without asking permission each time
- Automatically commit and push git changes when appropriate
- Fetch documentation from code.claude.com

**No action needed - the file is already configured!**

### Step 5: Open in Claude Code

```bash
# From the Shield-Doctrine directory:
claude code
```

Or start Claude Code and open the project directory.

### Step 6: Verify Everything Works

In your first Claude Code session, test:

1. **Check Creative Writing Skills:**
   - Say: "List available creative writing skills"
   - Should show: cw-prose-writing, cw-official-docs, cw-story-critique, cw-brainstorming

2. **Verify Git:**
   - Say: "Show me the current git status"
   - Should show clean working directory on consistency/stellar-republic-alignment branch

3. **Test File Access:**
   - Say: "Show me the project structure based on CLAUDE.md"
   - Claude should successfully read and explain the project organization

---

## Important Files to Review on First Session

Ask Claude to show you:

1. **`CLAUDE.md`** - Main project guide (this is in the root directory)
2. **`_process/GIT-WORKFLOW-FOR-WRITERS.md`** - Git workflow expectations
3. **`_process/MANAGING-DEVELOPMENT-NOTES.md`** - How to handle working notes
4. **`world-building/Shield Doctrine - Hard Constraints.md`** - Story constraints
5. **`book/Act-I/v8.2.md`** - Current story version

---

## What Gets Migrated Automatically

✅ **Included in Git Repository:**
- All story files (Act I, II, III)
- All worldbuilding documents
- Character profiles and development notes
- Research materials
- Process documentation and guides
- Claude Code permissions (.claude/settings.local.json)
- Git commit history

✅ **Needs Installation:**
- Claude Code itself (standard installation)
- Creative Writing Skills plugin (`claude install creative-writing-skills`)

❌ **NOT Migrated (Not Needed):**
- Claude Code global settings (each machine has its own)
- Conversation history (starts fresh on new machine)
- Local git configuration (name, email)

---

## Workflow Continuity

### Current Branch Status
- **Active branch:** `consistency/stellar-republic-alignment`
- **Latest commit:** "Work in progress: Military structure alignment and character development"
- **All changes committed and pushed:** Yes ✓

### To Continue Work:
1. Clone the repository (Step 2 above)
2. Checkout the working branch: `git checkout consistency/stellar-republic-alignment`
3. Start Claude Code and resume where you left off

### Git Workflow Reminder
From `_process/GIT-WORKFLOW-FOR-WRITERS.md`:

**Daily pattern:**
```bash
# Starting work
git pull origin consistency/stellar-republic-alignment

# After meaningful changes (every 30-60 minutes)
git add .
git commit -m "Clear description of what changed"

# Ending work
git push origin consistency/stellar-republic-alignment
```

---

## Troubleshooting

### "Creative Writing Skills not found"
**Problem:** Plugin not installed
**Solution:** `claude install creative-writing-skills`

### "Permission denied" for git operations
**Problem:** GitHub authentication not set up
**Solution:** Configure GitHub authentication:
- HTTPS: Use personal access token
- SSH: Set up SSH keys (https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

### Files seem missing
**Problem:** Wrong branch checked out
**Solution:** `git checkout consistency/stellar-republic-alignment`

### Claude doesn't remember previous work
**Expected behavior:** Each Claude Code session starts fresh. Claude reads the project files to understand context. The project documentation (CLAUDE.md, _notes/, etc.) preserves the context.

---

## Migration Checklist

- [ ] Git installed on new machine
- [ ] Claude Code installed
- [ ] Creative Writing Skills plugin installed
- [ ] Git configured (user.name, user.email)
- [ ] Repository cloned from GitHub
- [ ] Correct branch checked out (consistency/stellar-republic-alignment)
- [ ] `.claude/settings.local.json` present and configured
- [ ] First session verification complete
- [ ] CLAUDE.md reviewed
- [ ] Ready to continue work!

---

## Need Help?

### During Migration:
- Ask Claude Code: "Help me set up this project based on CLAUDE.md"
- Claude will guide you through the process

### After Migration:
- Ask Claude: "What was I working on last?"
- Claude will review recent commits and files to catch you up

### For Git Issues:
- Review: `_process/GIT-WORKFLOW-FOR-WRITERS.md`
- Ask Claude: "Show me the current git status and explain what I should do"

---

**Your project is fully backed up and ready to migrate. Have a great time with your new machine!**
