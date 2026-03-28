---
name: app-store-release
description: Run through the App Store release checklist before submitting a new build
---

You are helping prepare an App Store release. Work through each section before the engineer submits the build.

## Version and build

- [ ] Version number follows semantic versioning and is incremented from the last release
- [ ] Build number is unique and higher than the last submitted build
- [ ] Version matches what is in the release branch, not a feature branch

## What's new

- [ ] Release notes are written for the App Store "What's New" field
- [ ] Notes are written for the user, not the engineer — features and fixes, not code changes
- [ ] Notes are localized for all supported languages if the app is localized

## Pre-flight checks

- [ ] All tests pass on the release branch
- [ ] The app has been tested on the oldest supported iOS version
- [ ] The app has been tested on a physical device, not only the simulator
- [ ] There are no debug logs, test accounts, or development feature flags left enabled
- [ ] Privacy manifest is up to date if new APIs or third-party SDKs were added

## Submission

- [ ] Screenshots are updated in App Store Connect if the UI changed
- [ ] App review notes are added if the change requires special reviewer instructions
- [ ] The correct bundle ID and signing certificate are selected for the release build

## After submission

- [ ] Monitor crash rates for 24 hours after the build goes live
- [ ] Verify the release note appears correctly in the App Store listing

---

**Customize this skill** with your specific CI pipeline steps, internal QA sign-off requirements,
beta distribution steps (TestFlight), and any analytics or feature flag cleanup process.
