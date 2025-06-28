# Claude Command Reference - Quick Version v1.0

## Answer Format
```
[A#X]
[#TOPIC]
[ref:A#Y] (if building on previous answers)
Response content...
[SUMMARY of LAST CODE] + OPEN FILE (after coding)
```

## Commands
- **SSS** → Short answers only, no code
- **TP [#topic]** → Extract template for topic
- **TP from [A#X] to [A#Y]** → Template from answer range
- **TP from [WHOLE]** → Template for entire conversation
- **BR** → Brainstorm mode (NO CODE, ideas only)

## File Standards

### Naming: `YY-MM-DD-HHMM-NAME-vX.X.ext`

### Header Format:
```
/*
Created/Edited: [Date, Time] v[Version]
Full Path: [Complete file path]
Project: [Project Name]
Lines: [Number of lines]
*/

# Table of Content
1. [Section 1]
2. [Section 2]

---
[File content starts here]
```

### Date Setup:
Say "Today is [date/time]" ONCE at start OR use `claude-date` script

## Project Rules
- **PRD Required**: Every project needs PRD file that updates with changes
- **Coding Rule**: MUST open file after any coding/editing task
- **Process Rule**: CHECK → KILL existing → LAUNCH single instance (apps/scripts/websites)
- **Templates**: Save to `/Desktop/TEMPLATE/` with timestamp prefix

## Topic Tags
`#PROJECT-NAME` `#IMPLEMENTATION` `#ARCHITECTURE` `#PLANNING` `#TESTING` `#DEBUG` `#CONCEPT` `#OPTIMIZATION`

## Quick Examples
```
[A#5]
[#WEB-APP]
[ref:A#3,A#4]
Here's the updated login component...

1. Checking for existing React dev server...
2. Killing existing processes (PID: 1234)
3. Starting single new instance on port 3000
4. Opening login.js file

[SUMMARY: Updated login.js with validation, added to /src/components/]
[Opens file automatically]
```