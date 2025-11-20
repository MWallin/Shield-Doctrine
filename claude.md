# Shield Doctrine - Project Guide

## Project Identity & Purpose

**Shield Doctrine** is a military science fiction trilogy set in a Roman-inspired stellar republic in 2750 CE. The story focuses on professional competence, earned citizenship, and infrastructure as the foundation of civilization.

**Current Development Status:** Act I v7 with investigation subplot, Acts II-III v5

**Genre:** Hard military sci-fi with emphasis on tactical realism and professional competence

## Document Hierarchy (Source of Truth)

### PRIMARY REFERENCES (Must Respect)
- **Worldbuilding Consistency Guide.md** - CANONICAL constraints that cannot be violated
- **correctness/Roman Principles Integration Guide.md** - Roman integration requirements and opportunities
- **world-building/The Stellar Republic.md** - Political and civic structure (3,200+ lines)

### ACTIVE STORY VERSION
- **chapters/Act I - Story v7.md** - Current Act I with investigation subplot (10,465 words)
- **chapters/Act II - Story v5.md** - Current Act II
- **chapters/Act III - Story v5.md** - Current Act III
- **chapters/Act I - Story v6.md** - Previous Act I version (reference)
- **chapters/*Improvements.md** - Analysis and enhancement notes for each act

### SUPPORTING MATERIALS
- **world-building/** - Technology systems, themes, settings
- **characters/Key Characters.md** - Character profiles and development
- **research/** - Historical Roman military and civic model reference material
- **Future Story Opportunities.md** - Potential expansions and future storylines

### WORKING DIRECTORIES (Not Canonical)
- **_notes/** - Temporary notes and scratch work
- **_process/** - Process documentation and workflow notes

## Git Workflow & Version Control

### Commit Frequency (IMPORTANT)
**Commit early and often** to preserve work and maintain clear history:

- **After every major text change** (~500-1000 words written or significant scene revision)
- **After completing a logical unit** (scene, character profile, investigation sequence)
- **Before and after major refactoring** (character name changes, plot restructuring)
- **At natural stopping points** (end of writing session, before switching tasks)

**Rule of thumb:** If you've been working for 30-60 minutes without committing, commit now.

### Daily Workflow Pattern

**Starting work:**
```bash
git pull origin main          # Get latest changes
git status                    # Check current state
```

**During work:**
```bash
# After each meaningful change (every 30-60 minutes):
git add .
git commit -m "Clear description of what changed"

# Examples of good commit messages:
# "Act I: Add murder mystery investigation scenes (lines 40-122)"
# "Characters: Update Chen's service time to 18 years"
# "Fix: Rename Williams → Thompson to preserve Act III character"
```

**Ending work:**
```bash
git add .
git commit -m "Description of final changes"
git push origin main          # Share your work
```

### Claude's Workflow Responsibilities

When working with Claude (that's me!):

1. **I will remind you to commit** after substantial changes to story files
2. **I will commit automatically** after:
   - Major text additions (>1000 words)
   - Character consistency fixes across multiple files
   - Documentation updates that complete a task
3. **I will suggest commit points** when we've been working for extended periods
4. **I will create clear commit messages** that describe what changed and why

### What Makes a Good Commit

✅ **Good commits:**
- "Act I v7: Add investigation subplot with Webb interrogation"
- "Characters: Add gender markers for Davis, Kim, Okonkwo"
- "Fix: Change Morrison to rank/last name during duty situations"
- "Update Act I Improvements.md for v7 progress (10,465 words)"

❌ **Bad commits:**
- "updates" (too vague)
- "fixes" (what did it fix?)
- "changes" (meaningless)

### Milestone Tags

Create tags for major milestones:
```bash
git tag -a v1.0-act-I-complete -m "Act I first complete draft"
git push origin v1.0-act-I-complete
```

**When to tag:**
- First complete draft of each act
- Major revision milestones
- Before structural changes
- Beta reader versions

### Emergency Recovery

**If you need to undo changes:**
```bash
git restore filename          # Undo uncommitted changes
git log                      # See history to find previous version
git checkout abc1234 -- filename  # Restore from specific commit
```

See `_process/GIT-WORKFLOW-FOR-WRITERS.md` for complete git reference.

## Hard Constraints (Cannot Violate)

### Timeline
- **2150 CE:** Humanity's exodus from Earth (asteroid threat)
- **2150-2400 CE:** Diaspora period, colony establishment
- **2400-2550 CE:** Emergence of stellar nations
- **2550-2600 CE:** Confederation formation
- **2745 CE:** Confederation captures Krell vessels, begins reverse-engineering jump drives
- **2750 CE:** Shield Doctrine trilogy main events
  - Obsidian Station attack (Year 0)
  - Typhon battle (6 weeks later)
  - Hammerfall (16 months after Typhon)

### Physics & Technology Hard Limits

**Faster-Than-Light Travel:**
- Jump drives ONLY (spatial compression, not wormholes)
- Requires massive energy (scales exponentially with distance)
- Calculation time vs. accuracy trade-off is fundamental
- Cannot jump near massive gravitational sources safely
- **NO FTL communication possible**

**Phase-Variance Shields:**
- Duration limited by power and psychological factors
- **Cannot communicate electronically while phased**
- Objects must be in physical contact to remain phased together
- Phased objects cannot interact with normal matter
- Recently discovered technology (discovered at Obsidian Station, 2750 CE)

**Jump Drives:**
- Recently acquired from Krell (2745 CE)
- Confederation still mastering the technology
- Creates strategic vulnerability (limited operational range)

### Military Organization (Roman Terms)
- **Century:** 80 legionaries
- **Cohort:** Multiple centuries
- **Legion:** Multiple cohorts
- **Centurion:** Century commander (typically 15+ years experience)
- **Primus Pilus:** Senior centurion, second-in-command
- **Gladius:** Ceremonial and practical close-quarters weapon (molecular-edge, vibration field)

## Core Themes (Must Be Present)

### 1. Professional Competence Overcomes Adversity
- Success comes from training, experience, adaptation, and professional excellence
- **No narrative shortcuts, luck, or special powers**
- Characters succeed because they're good at what they do
- Failures happen due to genuine difficulty, not character stupidity
- Creates satisfying "competence porn" where readers watch professionals excel

**Roman Connection:** Roman military success came from systematic training, professional development, and institutional learning—not individual heroics.

### 2. Earned Citizenship Creates Stakeholder Society
- Political rights come through service
- Graduated tiers acknowledge contributions incrementally
- **Tiered System:** Civic Participant (2 years) → Regional Citizen (4 years) → Federal Citizen (6 years)
- Creates stakeholders invested in the system's success

**Roman Connection:** Roman citizenship was a strategic weapon transforming conquered enemies into stakeholders. Graduated citizenship (Latini, civitas sine suffragio, full citizenship) created multiple levels of belonging.

### 3. Infrastructure as Foundation of Civilization
- Roads, aqueducts, communication networks enable prosperity
- Infrastructure investment creates long-term strategic advantage
- Engineering excellence matters as much as military prowess

**Roman Connection:** Roman roads, aqueducts, and fortifications enabled both military control and economic prosperity for centuries.

## Writing Style Requirements

### Tone & Approach
- **Technical accuracy matters** (engineering, military tactics, physics)
- Show systematic adaptation and institutional learning
- Characters succeed through skill, training, and adaptation
- After-action reviews and doctrine refinement are part of the culture
- Respect the intelligence of both characters and readers

### What to Avoid
- Narrative shortcuts or deus ex machina solutions
- Characters making stupid decisions to create drama
- Technology working inconsistently for plot convenience
- Individual "chosen one" heroics over professional teamwork
- Ignoring established constraints for convenience

### What to Emphasize
- Combined arms integration (boarding specialists + engineers + support)
- Systematic problem-solving and iterative improvement
- Professional military culture and traditions
- Engineering challenges solved through expertise under pressure
- Tactical innovation within established constraints

## Roman Integration Principles

### Military (Well Established)
- Professional volunteer military (6-year service minimum)
- Career progression based on merit and experience
- Combined arms doctrine
- Systematic after-action reviews
- Adaptation of enemy technologies
- Gladius as symbol of legionary tradition

### Civic (Needs Strengthening)
- Citizenship through service model
- Senate deliberation and debate
- Provincial governance structures
- Infrastructure as state priority
- Public works and engineering culture

### Cultural (Opportunities for Development)
- Values transmission through formal education
- Ancestor veneration and family traditions
- Public ceremonies and rituals
- Engineering as prestige profession
- Service ethos embedded in culture

## Common Collaboration Tasks

### Story Development
1. Check current versions in `chapters/` (Act I v7, Acts II-III v5)
2. Reference corresponding Improvements docs for analysis
3. Verify consistency with Worldbuilding Consistency Guide
4. Check Roman Principles Integration Guide for opportunities
5. **Commit after major changes** (see Git Workflow section)

### Character Work
1. Maintain consistency with `characters/Key Characters.md`
2. Ensure character actions reflect professional competence
3. Show growth through experience and adaptation
4. Respect established backgrounds and motivations

### Technology & Worldbuilding
1. **Must align with Consistency Guide constraints**
2. Check `world-building/Key Technology.md` for established systems
3. Ensure new tech doesn't violate hard physics limits
4. Consider strategic/tactical implications of any changes

### Roman Elements
1. Reference Integration Guide for gaps and opportunities
2. Consider both military and civic applications
3. Ensure historical parallels enhance rather than constrain story
4. Balance authenticity with narrative needs

## Version History

- **Act I v7** - Current with investigation subplot, murder mystery, character fixes (10,465 words)
- **Act I v6** - Character consistency improvements, previous version
- **Acts II-III v5** - Current working versions
- Earlier versions retained for reference only
- Untracked folders (`_notes/`, `_process/`) excluded by .gitignore

## Key Story Beats (Spoiler Warning)

**Act I - Obsidian Station (v7):**
- Dr. Adeyemi discovers phase-variance shields from mysterious artifact
- Rodriguez and Park discover Sarah Miller murdered with encrypted data drive
- Tanaka investigates: 5 suspects, unauthorized transmissions to Krell
- Krell attack station (coordinates leaked weeks ago, timed to supply arrival)
- Centurion Chen's century holds the line while researchers evacuate
- Conference call: Varro, Torres, Chen, Adeyemi plan rescue with phase-shields
- Torres builds working shields in 35 minutes with real engineering challenges
- Varro makes emergency jump with incomplete calculations (4 days stranded)
- Investigation during stranding: Torres builds memory core reader, AI reconstructs files
- Tanaka interrogates suspects: distillery red herring, Webb as ideological traitor
- Webb interrogation: Democracy vs Republic debate, refuses to recant
- Act II setup: Webb's handler "Aurelius" and underground movement revealed

**Act II - Typhon:**
- 6 weeks of systematic training and doctrine development
- Mathematical breakthrough: phase-shields and jump drives share underlying principles
- Security investigation reveals citizenship system created insider threat (Webb)
- Battle of Typhon: VLC (Very Low Confidence jump) + phase-shield tactics succeed

**Act III - Hammerfall:**
- 16 months later: Confederation strikes back at Krell
- Ambitious multi-fleet operation with incomplete preparation
- Phase-anchor technology fails at critical moment
- Professional adaptation and improvisation secure victory despite setbacks
- Citizenship reforms implemented based on lessons learned

---

*This guide is a living document. Update as the project evolves, but always respect the hard constraints in the Worldbuilding Consistency Guide.*
