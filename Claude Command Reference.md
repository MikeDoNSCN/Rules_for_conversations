# Claude Command Reference

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
[A#1][#FW01] Here's how FRAMEWORK 01 works...

[A#2][#MIKE-TECH][ref:A#1] Building on BMAD concepts, MIKE focuses on...

[A#3][#OPTIMIZATION][ref:A#2,#MIKE-TECH] To optimize the MIKE approach from answer #2...
```
### Output Structure
```
Project created at: [path]

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

## SSS - Short answers mode only, No code

---


---
