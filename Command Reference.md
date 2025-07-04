# Command Reference

ALWAYS ANSWER IN VIETNAMESE
EXCEPT SOME SPECIAL CASES
## Command Overview
This file defines special commands that activate specific  behaviors. When these commands appear at the start of a message, AI will immediately switch to the corresponding mode.

## Answer Reference System

### How References Answers
Every answer from Claude will include:
1. **Reference Number**: `[A#1]`, `[A#2]`, etc.
2. **Topic Tags**: `[#TOPIC-NAME]` for main topics
3. **Cross-references**: `[ref:A#5,#MIKE-CORE]` when building on previous answers

### Format Examples
```
[A#1][#FW01] Here's how FRAMEWORK 01 works...

[A#2][#MIKE-TECH][ref:A#1] Building on BMAD concepts, MIKE focuses on...

[A#3][#OPTIMIZATION][ref:A#2,#MIKE-TECH] To optimize the MIKE approach from answer #2...

At the end of each answer, after finishing code, you have to summarize what you did in the code, in what file (full path).
[SUMMARY of LAST CODE]

```

- `#DESKTOP-COMMANDER` [full_path_of_the_file you are working]- BEFORE you use MCP Desktop-commander
- 

IF YOU USE DESKTOP COMMAND, YOU MUST USE 