# Contributor Recognition Scoring (Proposal)
## Problem

Currently, the system mainly relies on total contribution counts.
This makes it difficult to:
- recognize leadership roles (like chapter/project leaders)
- highlight consistently active contributors
- differentiate between meaningful contributions and just high volume
---

## Goal
Improve the ranking system so that it reflects:
- contribution quality
- leadership impact
- consistency over time
---

## Proposed Approach
### 1. Contribution Breakdown
Instead of using a single aggregated count, contributions can be separated into:
- Pull Requests (PRs)
- Code Reviews
- Issues
This helps better understand the type of contribution.
---

### 2. Leadership Recognition
From the existing `EntityMember` model:
- Users with role = LEADER  
- and marked as active + reviewed  
should receive higher importance in scoring.
---

### 3. Consistency Factor
Using `contribution_data`, we can estimate:
- how regularly a user contributes  
- not just how much they contributed once  
This helps prioritize consistent contributors over one-time spikes.
---

### 4. Combined Scoring Idea
A simple scoring approach could combine:
- contribution types (PR, review, issue)
- leadership bonus
- consistency factor
The exact weights can be adjusted based on discussion.
---

## Why this helps
- Moves beyond just counting contributions  
- Recognizes leadership roles (as suggested in discussion)  
- Rewards consistent contributors  
- Aligns better with real contributor impact  
---

## Next Steps

- Refine weights for each contribution type  
- Define clear tier thresholds  
- Validate approach with existing data  
