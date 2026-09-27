# Branching Policy

## Model

Use a lightweight GitHub Flow model. `main` is always reviewable and should remain playable.

## Branch names

- `feature/<issue>-short-description`
- `fix/<issue>-short-description`
- `content/<issue>-short-description`
- `docs/<issue>-short-description`
- `chore/<issue>-short-description`

Examples:

- `feature/12-teleport-targeting`
- `content/31-ash-knight-arena`
- `fix/47-projectile-pooling`

## Rules

1. Create branches from the latest `main`.
2. Keep one coherent change per branch.
3. Open a draft pull request early for changes larger than one day.
4. Link the pull request to its GitHub Project item or issue.
5. Require one approval when the team has multiple contributors.
6. Require passing automated checks before merge once CI exists.
7. Use squash merge and delete the merged branch.
8. Never commit directly to `main` except for an agreed emergency documentation correction.

## Commit messages

Use an imperative summary under 72 characters. Optional prefixes are `feat`, `fix`, `art`, `audio`, `docs`, `test`, and `chore`.

Example: `feat: add collision-safe teleport destination check`

## Releases

Tag milestone builds as `v0.1.0-m1`, `v0.2.0-m2`, and so on. The final vertical slice is `v0.5.0` unless the team adopts a different version plan.
