# Claude Command Reference v1.0

## Command Overview
This file defines special commands that activate specific Claude behaviors. When these commands appear at the start of a message, Claude will immediately switch to the corresponding mode.

## Answer Reference System

### How Claude References Answers
Every answer from Claude will include:
1. **Reference Number**: `[A#1]`, `[A#2]`, etc.
2. **Topic Tags**: `[#TOPIC-NAME]` for main topics
3. **Cross-references**: `[ref:A#5,#MIKE-CORE]` when building on previous answers

### Format Examples
```
[A#1]
[#FW01] 
Here's how FRAMEWORK 01 works...

[A#2]
[#MIKE-TECH]
[ref:A#1] 
Building on BMAD concepts, MIKE focuses on...

[A#3]
[#OPTIMIZATION]
[ref:A#2,#MIKE-TECH] 
To optimize the MIKE approach from answer #2...

At the end of each answer, after finishing code, you have to summarize what you did in the code, in what file (full path).
[SUMMARY of LAST CODE]

⚠️ MANDATORY: Open the file after coding/editing tasks
```

### Output Structure
```
Project created at: [path]
```

**Code/Edit Completion Rule:**
⚠️ **MANDATORY**: After finishing ANY coding or editing task, Claude must open the file at the end of response

### Topic Tag Convention
- `#PROJECT-NAME` - Main project discussions (e.g., #MIKE-TECH, #BMAD-V4)
- `#IMPLEMENTATION` - Code/implementation details
- `#ARCHITECTURE` - System design discussions
- `#PLANNING` - Strategy and planning topics
- `#TESTING` - Test-related answers
- `#DEBUG` - Troubleshooting and fixes
- `#CONCEPT` - Theoretical explanations
- `#OPTIMIZATION` - Performance improvements

### Using References
You can now say:
- "Continue from A#5"
- "Expand on #MIKE-TECH"
- "Connect A#2 and A#7"
- "What did you say in A#10?"

---

## Process Management Requirements

### Before Running Apps/Scripts/Websites:
⚠️ **MANDATORY SEQUENCE**:
1. **Check**: Search for any existing versions running
2. **Kill**: Terminate all existing instances first
3. **Launch**: Start only ONE new instance
4. **Verify**: Confirm single instance is running

### Applies To:
- Running applications
- Executing scripts
- Opening websites/servers
- Starting development servers
- Launching any executable

### Process Check Commands:
```bash
# Check processes
ps aux | grep [app-name]        # Linux/Mac
tasklist | findstr [app-name]   # Windows

# Kill processes  
pkill [app-name]                # Linux/Mac
taskkill /f /im [app-name]      # Windows
```

### No Duplicate Rule:
- **Never launch multiple instances** of the same app/script
- **Always verify** only one instance is running after launch
- **Clean shutdown** before starting new versions

---

## Coding Workflow Requirements

### After Every Code/Edit Task:
1. **Summary**: `[SUMMARY of LAST CODE]` with full file path
2. **File Opening**: ⚠️ **MANDATORY** - Open the file automatically 
3. **No Exceptions**: This applies to ALL coding/editing tasks (create, modify, debug, etc.)

### Before Running Apps/Scripts/Websites (if applicable):
1. **Process Check**: Verify existing versions running
2. **Process Kill**: Terminate all existing instances
3. **Single Launch**: Start only ONE new instance
4. **Verify**: Confirm single instance running

### File Opening Triggers:
- Creating new files
- Editing existing files  
- Debugging code
- Adding features
- Refactoring
- Any code-related changes

---

## Project Management Requirements

### Mandatory PRD (Product Requirements Document)
**Every project MUST have:**
- PRD file at the project root folder
- Filename format: `YY-MM-DD-HHMM-ProjectName-PRD-vX.X.md`
- **Auto-update rule**: Whenever there are changes to the project, the PRD must be updated
- PRD should include: objectives, features, requirements, timeline, changes log

### PRD Template Structure:
```markdown
/*
Created: [Date, Time] v[Version]
Full Path: [Complete file path]
Project: [Project Name]
Lines: [Number of lines]
*/

# Table of Content
1. Project Overview
2. Features & Requirements
3. Timeline
4. Change Log

---

# [Project Name] - Product Requirements Document v[X.X]

## Project Overview
## Features & Requirements
## Timeline
## Change Log
- v1.0: Initial creation
- v1.1: Added feature X
```

---

## Special Commands

### SSS - Short Answers Mode
**Usage**: `SSS`
**Effect**: Claude provides short answers only, no code

### TP - Template Extraction
**Usage**: 
- `TP [#MIKE-TECH]` - Extract template for specific topic
- `TP from [A#3] to [A#5]` - Extract template from answer range
- `TP from [WHOLE]` - Extract template for entire conversation

**Effect**: Claude uses ultrathink to show user a general template

### BR - Brainstorm Mode
**Usage**: `BR`
**Effect**: Brainstorm with user and show different options with different priority levels
**Rule**: ⚠️ **NO CODE ALLOWED** - Ideas and concepts only

---

## Template System

### When Claude Identifies Special Templates:
1. **Save the template** to `/Desktop/TEMPLATE/` folder with `YY-MM-DD-HHMM-` prefix
2. **Include context**: Short description + current conversation context to help user understand later
3. **Provide reusable prompt**: Give the prompt that user can give to AI Model to use this template to solve problem X
4. **Handle naming**: Use appropriate versioning strategy with timestamp prefix

### Date Scripts Available:
- **PowerShell**: `25-06-28-1500-get-current-date.ps1` (Windows)
- **Bash**: `25-06-28-1500-get-current-date.sh` (Mac/Linux)  
- **Setup Guide**: `25-06-28-1500-date-config-setup.md`
- **Usage**: Creates `claude-date` command for easy date retrieval

## File Standards

### File Naming Convention
**All files must start with**: `YY-MM-DD-HHMM-`
- Example: `25-06-28-1430-TEMPLATE-NAME-v1.0.md`
- Example: `25-06-28-1545-MIKE-TECH-APPROACH.md`

### Required File Header Format
**Every file must begin with:**
```
/*
Created/Edited: [Date, Time] v[Version]
Full Path: [Complete file path]
Project: [Project Name]
Lines: [Number of lines in final version]
*/
```

**Example Session:**
```
User: "Today is June 28, 2025, 2:30 PM. Create a web app project."

First file:  25-06-28-1430-WebApp-main.js
Second file: 25-06-28-1431-WebApp-style.css  
Third file:  25-06-28-1432-WebApp-PRD-v1.0.md
```

**File Header Example:**
```
/*
Created: June 28, 2025, 2:30 PM v1.0
Full Path: C:\Users\NCPC\Desktop\PROJECT\25-06-28-1430-WebApp\src\main.js
Project: WebApp
Lines: 247
*/

# Table of Content
1. Import Statements
2. Main App Component
3. Event Handlers
4. Export Default

---
// Main application code starts here
```

### Date Accuracy Solution
**Option 1 - Automated Script**:
- Use provided date scripts (PowerShell/Bash) 
- Run `claude-date` command before starting session
- Script outputs: "Today is June 28, 2025, 2:30 PM"
- Copy/paste this into Claude to start session

**Option 2 - Manual Session Date Setting**: 
- User provides correct date/time ONCE at start: "Today is June 28, 2025, 2:30 PM"
- Claude uses this as reference date for ALL files in the session
- Time auto-increments for multiple files (2:30 PM, 2:31 PM, 2:32 PM, etc.)

**Option 3 - MCP Integration** (if available):
- Claude Desktop with MCP may have direct system date access
- Test with: "What's the current system date/time?"

**Fallback**: If no date provided, Claude uses system date but notes it may be inaccurate

### Template Versioning Strategy
**For Template Updates/Evolution**:
- Each version gets new timestamp: 
  - `25-06-28-1430-TEMPLATE-NAME-v1.0.md` (original)
  - `25-06-28-1545-TEMPLATE-NAME-v2.0.md` (updated)
- Preserve previous versions for reference
- Document what changed in each version

**For Completely Different Templates**:
- Use unique descriptive names with timestamp
- Example: `25-06-28-1430-MIKE-TECH-v1.0.md` vs `25-06-28-1500-SARAH-APPROACH-v1.0.md`

**Version Tracking Format**:
```markdown
/*
Created/Edited: June 28, 2025, 2:30 PM v2.0
Full Path: C:\Users\NCPC\Desktop\TEMPLATE\25-06-28-1430-TEMPLATE-NAME-v2.0.md
Project: TEMPLATE-NAME
Lines: 156
*/

# Table of Content
1. Template Overview
2. What Changed in v2.0
3. Context
4. Usage Prompt

---

# Template Name v2.0
Filename: 25-06-28-1430-TEMPLATE-NAME-v2.0.md
Updated: June 28, 2025
Previous: v1.0 (original), v1.5 (minor fixes)

## What Changed in v2.0:
- Added error handling section
- Improved workflow steps
- Enhanced prompts

## Context:
[Original conversation context that led to this template]

## Usage Prompt:
"Use the [TEMPLATE-NAME] approach to solve [PROBLEM-TYPE]..."
```

---

## System Status
✅ **Active**: Answer referencing system enabled
✅ **Active**: Special commands ready
✅ **Active**: Template extraction and saving system
✅ **Active**: Version control for templates

---

## Quick Reference
- Every answer gets: `[A#X]` `[#TOPIC]` `[ref:previous]` (each on new line)
- Code answers end with: `[SUMMARY of LAST CODE]`
- **File naming**: `YY-MM-DD-HHMM-NAME-vX.X.ext`
- **File headers**: Date/time, version, full path, project name, line count + Table of Content
- **PRD required**: Every project needs PRD file that updates with changes
- **Date accuracy**: User should provide correct date when starting projects
- Templates save to: `/Desktop/TEMPLATE/YY-MM-DD-HHMM-TEMPLATE-NAME-vX.X.md` (each version gets new timestamp)
- Commands: `SSS` (short), `TP [#topic]` (templates), `TP from [A#X] to [A#Y]`, `TP from [WHOLE]`, `BR` (brainstorm - NO CODE)