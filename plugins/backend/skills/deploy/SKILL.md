---
name: deploy
description: Run through the deployment checklist before and after pushing to production
---

You are helping with a production deployment. Follow each section in order.

## Pre-deploy

- [ ] All tests pass on the branch being deployed
- [ ] The PR is approved and merged, not a direct push
- [ ] Any database migrations have been reviewed for safety (no locking operations on large tables, backward-compatible with the current running version)
- [ ] Feature flags are in place for high-risk changes so the rollout can be stopped without a rollback
- [ ] Dependent services have been notified if this deploy changes a shared interface

## Deploy

- [ ] Deploy to staging first; verify the change works as expected
- [ ] Check error rates and latency after the staging deploy before proceeding
- [ ] Deploy to production during low-traffic hours unless the change is a hotfix
- [ ] Monitor dashboards during the rollout

## Post-deploy

- [ ] Verify the change is live and working as expected in production
- [ ] Check error rates and latency for 15 minutes after the deploy
- [ ] Close any related on-call alerts if this was a fix
- [ ] Update the deployment log or ticket with the outcome

## Rollback

If something goes wrong:
1. Roll back the deploy immediately — do not debug in production first
2. Open an incident if users are affected
3. Investigate in staging once production is stable

---

**Customize this skill** with your actual deployment tool commands, monitoring dashboard links,
database migration safety rules specific to your stack, and rollback procedures.
