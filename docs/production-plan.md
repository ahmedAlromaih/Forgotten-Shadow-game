# Production Plan

## Planning assumptions

The plan targets an eight-week Unity 2.5D vertical slice. Owners are expressed as roles because team member names and GitHub usernames are not yet available. For a solo project, the Solo Developer owns every task while the role field indicates the required discipline. Art production is controlled through one reusable palace kit, shared character rigs, material variants, and a locked side-view camera.

GitHub Project fields:

- **Status:** Backlog, Ready, In Progress, In Review, Done
- **Milestone:** M0–M5
- **Priority:** P0, P1, P2
- **Size:** XS, S, M, L
- **Owner:** Producer, Game Designer, Gameplay Programmer, AI Programmer, 3D Generalist, Audio Designer, QA

The import-ready backlog is in [`project/github-projects-import.csv`](../project/github-projects-import.csv).

## Milestones

### M0 — Repository and design lock (Week 1)

**Exit criteria:** repository rules exist; scene, benchmark, architecture, scope, and backlog are reviewed; target Unity editor and URP versions are recorded.

### M1 — Teleport combat prototype (Week 2)

**Exit criteria:** the Unity greybox player can move, jump, attack, aim a valid teleport, evade damage, and restore charges through successful attacks on keyboard and gamepad. Movement and teleport destinations remain on the 2.5D plane, and Cinemachine preserves readable framing.

### M2 — Boss framework and first encounter (Weeks 3–4)

**Exit criteria:** reusable boss state machine, hit system, clue interaction, Ash Knight encounter, death/reset flow, and a first external playtest are complete.

### M3 — Complete boss rush (Weeks 5–6)

**Exit criteria:** all three guardians, their abilities, modular 3D rooms, camera transitions, checkpoints, and representative placeholder audio/visual feedback are playable end to end.

### M4 — King’s Chamber and ending (Week 7)

**Exit criteria:** projectile patterns, seals, sorcerer cage, final sequence, and ritual-reversal ending are integrated; the complete slice is beatable.

### M5 — Polish and submission (Week 8)

**Exit criteria:** critical defects are closed, performance and controls meet acceptance criteria, five-player usability results are addressed, and the release build and documentation are packaged.

## Ownership rules

- Every task has exactly one accountable owner role.
- Reviewers may contribute, but responsibility does not move until the board owner changes.
- P0 tasks block the milestone exit criteria.
- No task larger than L enters a sprint; split it first.
- A task moves to Done only after its acceptance criteria are demonstrated.

## Board workflow

1. Producer moves milestone candidates from Backlog to Ready.
2. Owner moves a task to In Progress before starting work.
3. Work is submitted through a pull request linked to the task.
4. A different contributor reviews code or content when the team has more than one person.
5. Owner or reviewer moves the task to Done after verification.
6. Producer reviews milestone risk and unowned work twice per week.

## Definition of done

- Acceptance criteria are met.
- Relevant tests or playtest notes are attached.
- No new critical warnings or errors appear.
- Assets follow naming and folder rules.
- Documentation changes are included where behaviour changed.
- Pull request is approved and merged into `main`.

## Scope-cut order

If the schedule slips, reduce scope in this order:

1. Remove optional scoring and completion rank.
2. Reduce each guardian to three attacks.
3. Replace cinematic shots with one locked in-engine camera, poses, and text.
4. Simplify the Oracle's combined-element puzzle.
5. Reduce final projectile variants while preserving three seals.

The teleport mechanic, three guardian weaknesses, cage objective, and ritual reversal are the protected core and should not be cut.
