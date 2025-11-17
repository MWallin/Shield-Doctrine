# Git Workflow Quick Reference Guide

## How Claude Code Works With Your Repository

### The Branch Setup
- **main** Your clean, reviewed work
- **claude/[session-id]** Claude's working branch for this session
- Changes stay separate until you merge them

## Workflow: From Claude's Changes to Your Main Branch
### Step 1: Claude Makes Changes
Claude edits files and automatically commits/pushes to the **claude/...** branch.

### Step 2: Review on GitHub
1. Go to your repository on GitHub
2. Click "Compare & pull request" (appears when new branch is pushed)
3. Review the "Files changed" tab see exactly what changed
4. Add comments if you want

### Step 3: Merge (if you like the changes)
Click "Merge pull request" button on GitHub

- This merges claude/... branch → main branch
- Only happens on GitHub, not your local computer yet

## Step 4: Update Your Local Computer
	# Switch to main branch
	git checkout main
	
	# Get the merged changes from GitHub
	git pull origin main

Done! Your local main branch now has Claude's changes.

## Alternative: Merge Locally (Without PR)
If you're already happy with the changes:

	# Make sure you're on main
	git checkout main
	
	# Merge the claude branch
	git merge claude/incomplete-request-01CDUfCHaRbUr1i1euntgW6F
	
	# Push to GitHub
	git push origin main

## Useful Commands
	# See which branch you're on
	git branch
	
	# See what changed
	git status
	
	# See commit history
	git log --oneline
	
	# Switch branches
	git checkout main
	git checkout claude/incomplete-request-01CDUfCHaRbUr1i1euntgW6F

## Why This Workflow?

- ✅ Safe Main branch stays clean until you approve
- ✅ Reviewable See exactly what changed before merging
- ✅ Reversible Don't like it? Just don't merge the PR
- ✅ Clear history Understand what changed and when

