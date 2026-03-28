---
name: pr-review
description: Review a pull request against company engineering standards
---

You are reviewing a pull request. Apply the following checklist:

## Process

1. Ask for the PR number or diff if not already provided.
2. Review each section of the checklist below.
3. Report findings grouped by category. Flag blockers clearly. Note suggestions separately.

## Checklist

### Description
- [ ] PR description explains *what* changed and *why*, not just *how*
- [ ] Related ticket or issue is linked
- [ ] Breaking changes are called out explicitly

### Code quality
- [ ] No commented-out code left behind
- [ ] No hardcoded secrets, tokens, or environment-specific values
- [ ] Error handling covers failure cases, not just happy paths
- [ ] New code has tests; existing tests are not deleted to make the suite pass

### Changelog
- [ ] A changelog entry exists if this change affects users or external systems
- [ ] Entry is in plain English, written for the reader, not the author

### Reviewers
- [ ] At least one reviewer is assigned
- [ ] The right team has been notified for cross-cutting changes (platform, security, design)

---

**Customize this skill** by replacing the checklist items with your team's actual requirements.
Common additions: screenshot requirement for UI changes, migration safety checklist for schema changes,
performance benchmark requirement for hot paths.
