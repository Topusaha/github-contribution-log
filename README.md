# Contribution [# 1]: [[Security] PHI-correlating identifier logged without LogSafe in SpireLabTest.java]

**Contribution Number:** [1]  
**Student:** [Topu Saha]  
**Issue:** [[link](https://github.com/carlos-emr/carlos/issues/2317)]  
**Status:** [Phase I Complete]

---

## Why I Chose This Issue

This ticket caught my eye because PHI-safe logging is a compliance boundary I haven't worked with directly in my current position. This ticket helps me understand how HIPAA shapes logging architecture differently than the patterns I use today.

---

## Understanding the Issue

### Problem Description

demographicNo is a surrogate key rather than direct clinical text. However, it represents a patient record and should not appear in plain log output. In debug mode, this information is logged, which we don't want because it can expose patient information. Since debug mode is turned off in production, this is not a high-priority ticket but should still be resolved. 

### Expected Behavior

Instead of logging the demographicNo directly, we should be using the wrapper LogSafe, which sanitizes the information.

### Current Behavior

Currently, we have this code executing, which logs demographicNo directly. 

// src/main/java/io/github/carlos_emr/carlos/lab/ca/on/Spire/SpireLabTest.java:134
log.debug("going out " + this.demographicNo);

### Affected Components

Any part of the codebase that logs demographicNo without using the LogSafe wrapper is involved. 

---

## Reproduction Process

### Environment Setup

1. Clone and Fork the repo
2. Set up dev containers on the repo (currently stuck and not working)

Dev containers is currently on a loop and do not fully connect; the maintainers say it takes a while but I ran it for a whole day and the dev containers never connected. I currently tried to check if any other containers are taking up the required ports and they aren't. I'm planning to talk to my teammate who successfully installed this and get back and track this upcoming week. 

### Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
