# Universal PRD Breakdown Template
## Modular Architecture Framework for Any Project

### Template Version: 1.0
### Created: July 4, 2025
### Purpose: Standardized breakdown methodology for all PRDs

---

## 1. Module Naming Convention

### Semantic Path System
```
SYSTEM.FEATURE.COMPONENT.UNIT.ATOM
```

### Alternative Naming Patterns (Choose One)
```
Option A: DOMAIN.CATEGORY.MODULE.SUBMODULE.NANO
Option B: LAYER.SECTION.BLOCK.ELEMENT.PARTICLE
Option C: AREA.FUNCTION.SERVICE.METHOD.PRIMITIVE
```

### System Prefixes (Customize per project)
```
CORE    - Core infrastructure
AUTH    - Authentication & authorization  
DATA    - Data management & storage
API     - External interfaces
UI      - User interface components
PROC    - Business processes
UTIL    - Utility functions
INT     - Integrations
SEC     - Security features
```

---

## 2. Module Hierarchy Levels

### Level Structure with Token Limits
```
L1: Large Modules (System Level)          [No limit]
├── L2: Medium Modules (Feature Level)    [<10,000 tokens]
│   ├── L3: Small Modules (Component)     [<2,000 tokens]
│   │   ├── L4: Tiny Modules (Unit)       [<300 tokens]
│   │   │   └── L5: Nano Modules (Atom)   [30-50 tokens]
```

### Level Characteristics
| Level | Purpose | Token Range | Dependencies | Reusability |
|-------|---------|-------------|--------------|-------------|
| L1 | System boundaries | Unlimited | Multiple L2s | 0-20% |
| L2 | Major features | 2K-10K | Multiple L3s | 20-40% |
| L3 | Components | 300-2K | Multiple L4s | 40-60% |
| L4 | Units | 50-300 | Multiple L5s | 60-80% |
| L5 | Atoms | 30-50 | None | 100% |

---

## 3. Breakdown Process Template

### Step 1: Identify L1 Systems
```markdown
## L1: Large Modules (System Level)

### L1.1 [SYSTEM_NAME_1]
- Purpose: [Brief description]
- Key responsibilities: [List 3-5]

### L1.2 [SYSTEM_NAME_2]
- Purpose: [Brief description]
- Key responsibilities: [List 3-5]

### L1.3 [SYSTEM_NAME_3]
- Purpose: [Brief description]
- Key responsibilities: [List 3-5]
```

### Step 2: Break Down to L2 Features
```markdown
## L2: Medium Modules (Feature Level)

### From L1.1 [SYSTEM_NAME_1]:
- **L2.1.1** [FEATURE_NAME_1]
  - Token estimate: [X tokens]
  - Dependencies: [List any]
  
- **L2.1.2** [FEATURE_NAME_2]
  - Token estimate: [X tokens]
  - Dependencies: [List any]
```

### Step 3: Continue to L3 Components
```markdown
## L3: Small Modules (Component Level)

### From L2.1.1 [FEATURE_NAME_1]:
- **L3.1.1.1** [COMPONENT_NAME_1]
  - Token estimate: [X tokens]
  - Reusability: [X%]
  
- **L3.1.1.2** [COMPONENT_NAME_2]
  - Token estimate: [X tokens]
  - Reusability: [X%]
```

### Step 4: Define L4 Units
```markdown
## L4: Tiny Modules (Unit Level)

### From L3.1.1.1 [COMPONENT_NAME_1]:
- **L4.1.1.1.1** [UNIT_NAME_1]
  - Token estimate: [X tokens]
  - Type: [Function/Class/Interface]
  
- **L4.1.1.1.2** [UNIT_NAME_2]
  - Token estimate: [X tokens]
  - Type: [Function/Class/Interface]
```

### Step 5: Specify L5 Atoms
```markdown
## L5: Nano Modules (Atom Level)

### From L4.1.1.1.1 [UNIT_NAME_1]:
- **L5.1.1.1.1.1** [ATOM_NAME_1]
  - Tokens: [30-50]
  - Pure code: Yes
  - Inline-able: Yes
  
- **L5.1.1.1.1.2** [ATOM_NAME_2]
  - Tokens: [30-50]
  - Pure code: Yes
  - Inline-able: Yes
```

---

## 4. Module Specification Template

### For Each Module, Document:
```markdown
### Module: [FULL.PATH.TO.MODULE]
- **Level**: [L1-L5]
- **Tokens**: [Estimated count]
- **Purpose**: [One-line description]
- **Dependencies**: [List module paths or "None"]
- **Reusability**: [0-100%]
- **State**: [PLANNED|CODING|TESTING|READY|INTEGRATED]
- **Priority**: [CRITICAL|HIGH|MEDIUM|LOW]
- **Type**: [System|Feature|Component|Function|Pure]
```

---

## 5. State Tracking Matrix Template

```markdown
## Module State Tracking

| Module ID | Level | State | Dependencies | Priority | Tokens | Reusability |
|-----------|-------|-------|--------------|----------|--------|-------------|
| [PATH.TO.MODULE] | L5 | READY | None | CRITICAL | 45 | 100% |
| [PATH.TO.MODULE] | L4 | CODING | [Deps] | HIGH | 250 | 80% |
| [PATH.TO.MODULE] | L3 | PLANNED | [Deps] | MEDIUM | 1500 | 60% |
```

### State Definitions
- **PLANNED**: Defined but not started
- **CODING**: Implementation in progress
- **TESTING**: Code complete, testing ongoing
- **READY**: Fully tested, ready to integrate
- **INTEGRATED**: Successfully merged into parent
- **DEPRECATED**: No longer needed

---

## 6. Dependency Visualization Template

```markdown
## Module Dependencies

### Dependency Graph
```
[MODULE_A]
├── depends on: [MODULE_X], [MODULE_Y]
└── required by: [MODULE_B], [MODULE_C]

[MODULE_B]
├── depends on: [MODULE_A]
└── required by: [MODULE_D]
```

### Circular Dependency Check
- [ ] No circular dependencies found
- [ ] All dependencies resolve correctly
- [ ] Dependency depth < 5 levels
```

---

## 7. Implementation Sequence Template

```markdown
## Implementation Order

### Phase 1: Foundation (Nano Modules)
1. Implement all L5 atoms with 100% reusability
2. Unit test each atom independently
3. Document inline usage examples

### Phase 2: Assembly (Tiny Modules)
1. Combine L5 atoms into L4 units
2. Verify <300 token limit
3. Integration test combinations

### Phase 3: Components (Small Modules)
1. Build L3 from tested L4 units
2. Ensure <2000 token limit
3. Add component-level tests

### Phase 4: Features (Medium Modules)
1. Integrate L3 into L2 features
2. User acceptance testing
3. Performance optimization

### Phase 5: Systems (Large Modules)
1. Complete L1 system integration
2. End-to-end testing
3. Production readiness
```

---

## 8. Quality Checklist Template

```markdown
## Module Quality Checklist

### For L5 (Nano) Modules:
- [ ] 30-50 tokens only
- [ ] Zero dependencies
- [ ] 100% reusable
- [ ] Pure code (no side effects)
- [ ] Can be inlined
- [ ] Single responsibility
- [ ] Fully tested

### For L4 (Tiny) Modules:
- [ ] <300 tokens
- [ ] Clear interface
- [ ] 80%+ reusability
- [ ] Documented usage
- [ ] Error handling

### For L3 (Small) Modules:
- [ ] <2000 tokens
- [ ] Component boundaries clear
- [ ] 60%+ reusability
- [ ] Integration tests
- [ ] Performance benchmarked

### For L2 (Medium) Modules:
- [ ] Feature complete
- [ ] User-facing documentation
- [ ] Acceptance tested
- [ ] Security reviewed

### For L1 (Large) Modules:
- [ ] System integration tested
- [ ] Production ready
- [ ] Monitoring in place
- [ ] Deployment documented
```

---

## 9. Reusability Analysis Template

```markdown
## Reusability Matrix

### Identify Reusable Patterns
| Module Type | Example | Reuse Locations | Savings |
|-------------|---------|-----------------|---------|
| Validators | EMAIL.VALIDATOR | Auth, Profile, Forms | 200 tokens |
| Parsers | JSON.PARSER | API, Config, Data | 150 tokens |
| Formatters | DATE.FORMATTER | UI, Logs, Reports | 100 tokens |

### Cross-System Reuse
- Module: [PATH]
- Used in: [System1], [System2], [System3]
- Total savings: [X tokens]
```

---

## 10. Project Customization Guide

### How to Adapt This Template:

1. **Choose Naming Convention**
   - Pick one pattern (Semantic/Domain/Layer)
   - Define your system prefixes
   - Stick to it consistently

2. **Adjust Token Limits**
   - Scale based on project complexity
   - Keep L5 at 30-50 (non-negotiable)
   - Adjust L3/L4 if needed

3. **Add Project-Specific Sections**
   - Domain-specific modules
   - Industry requirements
   - Compliance needs

4. **Define Success Metrics**
   - Reusability targets
   - Performance goals
   - Quality thresholds

---

## 11. Quick Reference Card

### Module Breakdown Rules
```
L5 (Nano):   30-50 tokens,  100% reusable, pure code
L4 (Tiny):   <300 tokens,   80%+ reusable, minimal deps
L3 (Small):  <2000 tokens,  60%+ reusable, clear bounds
L2 (Medium): <10K tokens,   40%+ reusable, feature complete
L1 (Large):  No limit,      System level,  fully integrated
```

### Priority Levels
```
CRITICAL: Blocks everything, core functionality
HIGH:     Important features, affects UX
MEDIUM:   Nice-to-have, enhances system
LOW:      Future improvements, optional
```

### Quick Commands
```
Find all L5 modules:     grep "L5\." 
Count dependencies:      grep "depends on"
Check reusability:       grep "100%"
Find critical modules:   grep "CRITICAL"
```

---

## 12. Template Usage Examples

### Example 1: E-commerce System
```
L1: SHOP (Shopping system)
├── L2: SHOP.CART (Cart management)
│   ├── L3: SHOP.CART.ITEMS (Item handling)
│   │   ├── L4: SHOP.CART.ITEMS.ADD (Add to cart)
│   │   │   └── L5: SHOP.CART.ITEMS.ADD.VALIDATOR
```

### Example 2: Authentication System
```
L1: AUTH (Authentication)
├── L2: AUTH.LOGIN (Login feature)
│   ├── L3: AUTH.LOGIN.OAUTH (OAuth handler)
│   │   ├── L4: AUTH.LOGIN.OAUTH.TOKEN (Token mgmt)
│   │   │   └── L5: AUTH.LOGIN.OAUTH.TOKEN.PARSER
```

### Example 3: Data Pipeline
```
L1: PIPE (Data pipeline)
├── L2: PIPE.EXTRACT (Data extraction)
│   ├── L3: PIPE.EXTRACT.SOURCES (Source handlers)
│   │   ├── L4: PIPE.EXTRACT.SOURCES.CSV (CSV reader)
│   │   │   └── L5: PIPE.EXTRACT.SOURCES.CSV.PARSER
```

---

## Template Maintenance

- **Version**: Update when methodology changes
- **Review**: Every 3 months or 5 projects
- **Feedback**: Collect from team usage
- **Evolution**: Add new patterns as discovered

This template provides a complete framework for breaking down any PRD into modular, reusable components while maintaining clarity and trackability throughout the development process.