# Contributing to Unified Career Acceleration Platform

This repository follows a strict Vertical Domain GitHub workflow to ensure the 3-member team can collaborate seamlessly during the 1-week sprint without stepping on each other's toes.

## Core Rule

Never work directly on `main` or `dev`. Create a task branch, push that branch, and merge changes through a pull request into your specific Domain branch.

## Branch Architecture

We use a domain-driven branch strategy to map perfectly to the 3 team members.

| Branch | Purpose | Owner | Merges into |
| --- | --- | --- | --- |
| `main` | Production-ready, deployed code | Team | Deployment |
| `dev` | Fully integrated project for the final release | Team | `main` |
| `domain-jobs` | Integration for Job Engine & Tracker | Member 1 | `dev` |
| `domain-mentorship`| Integration for Mentorship & Consulting | Member 2 | `dev` |
| `domain-core` | Integration for Auth & Referrals | Member 3 | `dev` |

```text
feature/job-filters   --PR--> domain-jobs -------\
feature/mentor-slots  --PR--> domain-mentorship --+--PR--> dev --PR--> main
feature/auth-jwt      --PR--> domain-core -------/
```

### Permanent Branch Responsibilities

- **`main`:** Must always be production-ready. 
- **`dev`:** Contains the working integrated platform. This is where M1, M2, and M3's work finally meets.
- **`domain-*` Branches:** These act as the "main" branch for each specific member. Member 1 only merges into `domain-jobs`. Member 2 only merges into `domain-mentorship`. 

## Choosing the Correct Base Branch

| Change scope | Create the branch from | Open the PR into |
| --- | --- | --- |
| Job Engine / Tracker task | `domain-jobs` | `domain-jobs` |
| Mentorship / Booking task | `domain-mentorship` | `domain-mentorship` |
| Auth / Referral / Wallet task | `domain-core` | `domain-core` |
| Shared UI Components / Theme | `dev` | `dev` |
| Urgent production fix | `main` | `main` |

## No Hardcoding & Strict Contracts (Code Quality Rules)
As defined in `team-rules.md`:
1. **Never merge hardcoded dummy data.** If you use mocks, they must perfectly match the agreed-upon TypeScript/Database schemas.
2. **Never merge un-responsive UI.** Every PR must look perfect on Mobile and Desktop. Reviewers MUST reject PRs that break on mobile screens.
3. **Never alter shared models unexpectedly.** Changes to `User`, `Wallet`, or `Jobs` models require a quick sync with the team before the PR is merged.

## Starting and Updating Work

Update your specific domain base before creating a task branch. For Member 1:

```bash
git switch domain-jobs
git pull --ff-only origin domain-jobs
git switch -c feature/kanban-board
```

Before final review, rebase to ensure clean history:

```bash
git fetch origin
git switch feature/kanban-board
git rebase origin/domain-jobs
```

## Pull Request Rules

Every pull request should include:
- What changed (e.g., "Added mobile-responsive ATS checker component")
- The API Schema (if a new endpoint was added)
- **Testing that was done: specifically confirming mobile responsiveness.**

Good pull request title examples:
- `feat(jobs): add drag-and-drop kanban board`
- `feat(mentorship): implement zoom link generation`
- `fix(core): resolve JWT token expiration edge case`

## Integration and Release Flow

1. Open a PR from your `domain-*` branch into `dev`.
2. Test the complete application across all 3 domains.
3. Merge the approved PR.
4. When `dev` is stable, open a release PR into `main` for deployment. 

**Integrate daily:** In a 7-day sprint, waiting until Day 6 to merge your domain into `dev` will cause catastrophic merge conflicts. Merge into `dev` at the end of every day.
