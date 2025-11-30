# Managing Development Notes and Background Material

**Last Updated:** 2025-01-27

---

## Purpose

This document defines how to handle working notes, Q&A sessions, brainstorming documents, and other development material that accumulates during story and worldbuilding work.

The goal: **Keep what's useful, archive what's historical, delete what's abandoned.**

---

## The Three-Folder System

### **`_notes/` - Active Working Material**

**What goes here:**
- Current brainstorming and Q&A sessions
- Active feedback on drafts in progress
- Inconsistency tracking for documents being revised
- Planning documents for upcoming work
- Anything you're **actively referencing**

**Rule:** If you haven't looked at it in 2+ weeks and the work it describes is done, it doesn't belong here anymore.

**Example files:**
- `Detective subplot.md` (while working on Act I v8)
- `Act I - v8 Feedback.md` (while revising Act I v8)
- `Service Branches Inconsistencies.md` (until issues are fixed)

---

### **`_archive/` - Completed Development History**

**What goes here:**
- Q&A and brainstorming that led to completed work
- Development iterations and feedback rounds
- Exploratory analysis that informed final decisions
- "How we got here" documentation
- Anything with **historical value** but not active use

**Rule:** Before archiving, add a header explaining what it informed and where to find the final result.

**Header template:**
```markdown
# [Document Title]

**Status:** ARCHIVED - [Date]
**Informed:** [What this led to]
**See:** [Where to find final implementation]

---

[Original content below]
```

**Example files:**
- `Detective Subplot Development.md` (after Act I v8 complete)
- `Framework Review - General Service Structure and Vigiles.md` (analysis complete, decisions made)
- `Vigiles Service - Structure Evaluation.md` (evaluation done, document finalized)

---

### **Deletion - For Truly Abandoned Work**

**What gets deleted:**
- Dead ends with no value
- Completely superseded work
- Redundant copies of information that exists elsewhere
- Abandoned ideas you're certain you won't revisit

**Rule:** Be cautious! When in doubt, archive instead of delete.

---

## Decision Framework

When you finish a piece of work (story draft, worldbuilding doc, etc.), ask:

### **Question 1: "Would I need this information to write a story set in this universe 2 years from now?"**

**YES** → Extract to canonical documents
- Worldbuilding facts → `world-building/` folder
- Character backstory → `characters/` folder
- Technology specs → canonical tech docs
- Plot logic → story outlines or character arcs

**MAYBE** → Archive it
- Development Q&A → `_archive/`
- Feedback rounds → `_archive/`
- Brainstorming sessions → `_archive/`

**NO** → Delete it
- Truly abandoned ideas
- Dead ends with no value
- Superseded drafts (if content is preserved elsewhere)

---

## Workflow Examples

### **Example 1: Detective Subplot Development**

**Phase 1 (Active Work):**
- File: `_notes/Detective subplot.md`
- Status: 376 lines of Q&A developing the subplot
- Action: Keep in `_notes/` while working on Act I v8

**Phase 2 (Work Complete):**
- Act I v8 is finished and stable
- Decision: Some content is reusable worldbuilding

**Actions:**
1. **Extract canonical worldbuilding:**
   - Create `world-building/Corporate Syndicate.md` (faction details)
   - Create `world-building/Known Alien Species.md` (Partners info)
   - Create `world-building/Artifacts and Precursors.md` (artifact lore)
   - Create `world-building/Mercenary Companies.md` (Firestorm Mercs)

2. **Archive development history:**
   - Move to `_archive/Act I v8 - Detective Subplot Development.md`
   - Add header: "Development Q&A that informed Act I v8. See chapters/Act I - Story v8.md"

**Result:**
- ✅ Useful worldbuilding preserved and organized
- ✅ Historical record preserved
- ✅ `_notes/` stays clean

---

### **Example 2: Act Feedback**

**Phase 1 (Active Work):**
- File: `_notes/Act I - v8 Feedback.md`
- Status: Specific critique and suggestions
- Action: Keep in `_notes/` while revising

**Phase 2 (Feedback Addressed):**
- Revisions complete, v8 is stable
- Decision: Feedback has been incorporated

**Actions:**
1. **Check if any general principles emerged:**
   - Yes: Add to `correctness/Writing Process Guide.md` or similar
   - No: Nothing to extract

2. **Archive the feedback:**
   - Move to `_archive/Act I - v8 Feedback (2025-01).md`
   - Add header noting it informed the final v8 draft

**Result:**
- ✅ Specific feedback archived for history
- ✅ General lessons preserved in process guides
- ✅ `_notes/` stays focused on current work

---

### **Example 3: Inconsistency Tracking**

**Phase 1 (Active Work):**
- File: `_notes/Service Branches Inconsistencies.md`
- Status: Lists 5 issues needing fixes
- Action: Keep in `_notes/` until issues resolved

**Phase 2 (Issues Fixed):**
- All 5 inconsistencies corrected in Service Branches doc
- Decision: No ongoing value, work is done

**Actions:**
1. **Verify fixes are complete:**
   - Hospital ships: 30 → 70 ✓
   - Citizenship pathways clarified ✓
   - Etc.

2. **Delete the tracking document:**
   - Issues are fixed in canonical docs
   - No need to preserve the problem list
   - If you want history, could archive instead

**Result:**
- ✅ Issues resolved
- ✅ Canonical docs are correct
- ✅ No clutter remains

---

## Archive Organization (Optional)

As `_archive/` grows, you can organize it:

```
_archive/
├── act-development/
│   ├── Act I v8 - Detective Subplot Development.md
│   └── Act I - v8 Feedback (2025-01).md
├── worldbuilding-analysis/
│   ├── Framework Review - General Service Structure.md
│   └── Vigiles Service - Structure Evaluation.md
└── process-evolution/
    └── [Process improvement iterations]
```

**Not required immediately** - only organize if archive gets large (20+ files).

---

## Integration with Git Workflow

**Before committing major changes:**
1. Review `_notes/` folder
2. Move completed work to `_archive/`
3. Extract any worldbuilding to canonical docs
4. Commit with message noting what was archived/extracted

**Example commit message:**
```
Archive Detective subplot planning, extract worldbuilding

- Moved Detective subplot.md to _archive/
- Extracted Corporate Syndicate to world-building/
- Extracted Partners (aliens) to world-building/
- Act I v8 complete and stable
```

---

## Quick Reference

| Question | Action |
|----------|--------|
| Still actively working on this? | Keep in `_notes/` |
| Work is done, has historical value? | Archive with header |
| Work is done, contains reusable facts? | Extract to canonical docs, then archive |
| Completely abandoned/superseded? | Delete (or archive if uncertain) |
| In doubt between archive/delete? | Archive (disk space is cheap) |

---

## Principles

1. **Active workspace stays clean** - `_notes/` should only contain current work
2. **History has value** - Archive development decisions so you remember "why"
3. **Knowledge gets organized** - Worldbuilding goes in canonical docs, not scattered notes
4. **When in doubt, archive** - Better to keep too much than lose something valuable

---

## See Also

- `GIT-WORKFLOW-FOR-WRITERS.md` - How to commit and manage versions
- `CLAUDE.md` - Project guide and instructions
- `.gitignore` - What folders are excluded from version control
