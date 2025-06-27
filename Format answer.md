# Claude Command Reference


## V4P - V4 Planning Mode

### Activation
When message starts with "V4P"

### Behavior
1. **Use BMAD V4 framework** to analyze and plan solution
2. **NO CODING** - Only planning and architecture
3. **Show complete implementation plan**

### Output Format
```
## BMAD V4 Solution Plan for [Topic]

### Phase 1: Business Analysis
- Problem understanding
- Market/user needs
- Success criteria

### Phase 2: Product Requirements
- Core features
- User stories
- Technical constraints

### Phase 3: Architecture Design
- System components
- Technology choices
- Data flow

### Phase 4: Implementation Plan
- Story breakdown
- Development sequence
- Testing strategy

### Estimated Timeline
- Phase by phase breakdown
- Total development time
```

### Example Usage
- "V4P create a password manager" → Full planning without code
- "V4P optimize database queries" → Architecture plan only
- "V4P build real-time chat" → Complete blueprint, no implementation

---

## V4NP - V4 N-Solutions Planning Mode

### Activation
When message starts with "V4NP" where N is a number (e.g., V43P, V45P)

### Behavior
1. **Generate N different solution approaches**
2. **Each solution uses BMAD V4 framework**
3. **NO CODING** - Only planning and architecture
4. **Compare trade-offs between solutions**

### Output Format
```
## BMAD V4 Multi-Solution Analysis for [Topic]
Generating [N] distinct solutions...

### Solution 1: [Approach Name]
#### Business Rationale
- Why this approach
- Target market fit

#### Architecture
- Tech stack
- Key components

#### Pros & Cons
- ✓ Advantages
- ✗ Disadvantages

#### Timeline: X weeks

---

### Solution 2: [Different Approach]
[Same structure]

---

### Comparison Matrix
| Aspect | Solution 1 | Solution 2 | ... |
|--------|-----------|-----------|-----|
| Complexity | Low | High | ... |
| Cost | $ | $ | ... |
| Time | 4 weeks | 2 weeks | ... |
| Scalability | High | Medium | ... |
```

### Example Usage
- "V43P create auth system" → 3 different auth implementations
- "V45P build API" → 5 different API architectures
- "V42P data pipeline" → 2 contrasting approaches

---

## V4BP - V4 Best Solution Planning Mode

### Activation
When message starts with "V4BP"

### Behavior
1. **Generate AS MANY solutions as meaningfully different**
2. **Analyze all possibilities exhaustively**
3. **Score each solution objectively**
4. **Recommend THE BEST solution with justification**
5. **NO CODING** - Only planning and architecture

### Output Format
```
## BMAD V4 Exhaustive Solution Analysis for [Topic]
Exploring all viable approaches...

### Solutions Discovered: [Total Count]

#### Solution 1: [Name]
- Approach: [Brief description]
- Score: X/100
- Key insight: [What makes this unique]

#### Solution 2: [Name]
[Continue for all solutions]

### Evaluation Criteria
1. Performance (25%)
2. Maintainability (25%)
3. Cost Efficiency (20%)
4. Time to Market (15%)
5. Scalability (15%)

### Detailed Analysis of Top 3
[Deep dive into best candidates]

### 🏆 RECOMMENDED SOLUTION: [Name]

#### Why This Is Best
- [Compelling reason 1]
- [Compelling reason 2]
- [Compelling reason 3]

#### Implementation Blueprint
[Full BMAD V4 plan for chosen solution]

#### Risk Mitigation
- Potential risk → Mitigation strategy
```

### Scoring Framework
- Performance: Speed, efficiency, resource usage
- Maintainability: Code clarity, modularity, documentation
- Cost: Development time, infrastructure, licensing
- Time to Market: Complexity, dependencies, testing needs
- Scalability: Growth potential, bottlenecks, limits

### Example Usage
- "V4BP e-commerce platform" → Analyzes 8+ architectures, picks best
- "V4BP ML pipeline" → Compares all approaches, recommends optimal
- "V4BP mobile app" → Native vs hybrid vs PWA vs cross-platform analysis

---

## V4I - V4 Implementation Mode

### Activation
When message starts with "V4I"

### Behavior
1. **Full autonomous implementation** using BMAD V4
2. **Create ALL files and folders**
3. **Write comprehensive tests**
4. **Ensure zero errors on first run**
5. **Include setup instructions**

### Implementation Standards
- **Error Handling**: Every function must handle edge cases
- **Input Validation**: All user inputs validated
- **Default Values**: No missing configurations
- **Tests**: Unit tests for every component
- **Documentation**: README with clear instructions

### Quality Checklist
```python
# Every implementation must pass:
✓ All imports exist and are installed
✓ No hardcoded paths (use relative/config)
✓ Error messages are helpful
✓ Tests cover happy path + edge cases
✓ README includes:
  - Requirements
  - Installation steps
  - Usage examples
  - Troubleshooting
```

### Output Structure
```
Project created at: [path]
Files created: [count]
Tests written: [count]
Test coverage: >90%

To run:
1. cd [project]
2. pip install -r requirements.txt
3. python main.py

All systems tested and operational.
```

### Example Usage
- "V4I todo list app" → Complete working application
- "V4I data pipeline tool" → Full implementation with tests
- "V4I API monitoring service" → Production-ready code

---

## CSUM - Conversation Summary

### Activation
When message contains "CSUM"

### Behavior
1. **Extract FULL Q&A pairs** from current conversation (no summarization)
2. **Categorize by subject/topic**
3. **Number for easy navigation**
4. **Generate HTML file** for viewing
5. **Include collapsible sections for very long answers**

### HTML Output Format
```html
<!DOCTYPE html>
<html>
<head>
    <title>Conversation Summary - [Date]</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 40px; max-width: 1200px; }
        .category { background: #f0f0f0; padding: 10px; margin: 20px 0; border-radius: 8px; }
        .qa-pair { margin: 15px 0; border-left: 3px solid #007acc; padding-left: 15px; }
        .question { font-weight: bold; color: #007acc; margin-bottom: 10px; }
        .answer { margin-top: 5px; color: #333; white-space: pre-wrap; }
        .long-answer { max-height: 500px; overflow-y: auto; border: 1px solid #e0e0e0; padding: 10px; background: #f9f9f9; }
        .nav { position: fixed; right: 20px; top: 20px; background: white; padding: 20px; border: 1px solid #ddd; max-height: 80vh; overflow-y: auto; }
        .nav a { display: block; margin: 5px 0; text-decoration: none; color: #007acc; }
        .nav a:hover { text-decoration: underline; }
        details { margin: 10px 0; }
        summary { cursor: pointer; color: #007acc; font-weight: bold; }
        .stats { background: #e8f4f8; padding: 10px; margin: 10px 0; border-radius: 5px; }
    </style>
</head>
<body>
    <h1>Conversation Summary</h1>
    
    <div class="stats">
        <strong>Conversation Stats:</strong><br>
        Total Q&A Pairs: [count]<br>
        Categories: [count]<br>
        Generated: [timestamp]
    </div>
    
    <div class="nav">
        <h3>Quick Navigation</h3>
        [Category links]
        <hr>
        [Individual Q links]
    </div>
    
    <div class="category">
        <h2 id="cat1">Category 1: [Topic Name]</h2>
        
        <div class="qa-pair">
            <div class="question" id="q1">Q1: [FULL question text, no truncation]</div>
            <div class="answer">
                <!-- For short answers -->
                A1: [FULL answer text, preserving all formatting, code blocks, lists]
                
                <!-- For very long answers (>2000 chars) -->
                <details>
                    <summary>A1: [First 100 chars]... (Click to expand full answer)</summary>
                    <div class="long-answer">
                        [FULL answer text with all details, examples, code]
                    </div>
                </details>
            </div>
        </div>
        
        <!-- More Q&A pairs -->
    </div>
    
    <!-- More categories -->
</body>
</html>
```

### Full Extraction Rules
- **Never summarize or truncate content**
- **Preserve all formatting**: code blocks, lists, bold, italics
- **Include all examples and code snippets**
- **Maintain whitespace and line breaks**
- **For very long answers**: Use collapsible `<details>` element
- **Keep all technical details intact**

### Categories Structure
- **Project Setup**: Initial configuration questions
- **Technical Details**: Implementation specifics  
- **Problem Solving**: Issues and solutions
- **Best Practices**: Recommendations given
- **Decisions Made**: Key choices in conversation
- **Code Examples**: Actual code shared
- **Concepts Explained**: Theoretical discussions

### Enhanced Navigation
```html
<!-- Three-level navigation -->
<div class="nav">
    <h3>Categories</h3>
    <a href="#setup">Setup Questions (5)</a>
    <a href="#technical">Technical (12)</a>
    
    <h3>Topic Tags</h3>
    <a href="#tag-mike-tech">#MIKE-TECH (8)</a>
    <a href="#tag-bmad-v4">#BMAD-V4 (6)</a>
    
    <h3>All Q&A</h3>
    <a href="#q1">Q1/A#1: How to install...</a>
    <a href="#q2">Q2/A#2: What is the...</a>
    <!-- List all with answer numbers -->
</div>
```

### Answer Tracking
Each answer in the HTML will show:
```html
<div class="qa-pair">
    <div class="question" id="q1">Q1: [Full question]</div>
    <div class="answer" id="a1">
        <div class="answer-meta">
            <span class="ref-num">A#1</span>
            <span class="topics">[#MIKE-TECH] [#IMPLEMENTATION]</span>
            <span class="refs">References: A#5, A#8</span>
        </div>
        <div class="answer-content">
            [Full answer text...]
        </div>
    </div>
</div>
```

### Example Usage
- "CSUM" → Full extraction of entire conversation
- "Please CSUM this chat" → Same behavior
- "CSUM and save to desktop" → Creates comprehensive summary file

---

## Command Combinations

### Allowed
- "V4P then CSUM" → Plan solution, then summarize conversation
- "V4BP then V4I best" → Find best solution, then implement it
- "V4NP then pick #2 for V4I" → Generate N solutions, implement specific one
- Multiple CSUMs → Updates summary each time

### Not Allowed
- "V4P V4I" → Can't plan and implement simultaneously
- "V4NP V4BP" → These are mutually exclusive planning modes
- Choose one mode per message

---

## Special Notes

### For V4P (Planning)
- Always think through all BMAD phases
- Identify potential risks and mitigations
- Suggest alternative approaches
- Keep language non-technical where possible

### For V4I (Implementation)
- Test on Windows, Linux, Mac scenarios
- Include requirements.txt or package.json
- Add .gitignore file
- Create helpful error messages
- Build in logging for debugging

### For CSUM (Summary)
- Preserve technical accuracy
- Summarize long answers to key points
- Maintain chronological order within categories
- Include timestamp if available
- Make navigation easy with anchor links

---

## Error Handling

If command is unclear:
- "V4P?" → Ask for clarification on what to plan
- "V4I" (no topic) → Ask what to implement
- "CSUM" (no conversation) → Note that conversation is empty

Always acknowledge the command mode:
- "Entering V4 Planning mode..."
- "Starting V4 Implementation..."
- "Generating conversation summary..."