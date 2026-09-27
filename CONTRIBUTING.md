# Contributing

## Before starting

1. Choose an assigned Ready item from the project board.
2. Confirm its acceptance criteria and dependencies.
3. Create a branch following `docs/branching-policy.md`.

## Development rules

- Use the Unity editor version recorded in `ProjectSettings/ProjectVersion.txt`.
- Do not add plugins or large binary assets without team agreement.
- Keep gameplay values in ScriptableObjects instead of duplicating constants.
- Follow the repository's C# style and keep MonoBehaviours focused.
- Prefer C# events or ScriptableObject event channels over hard-coded scene lookups.
- Keep prefabs and scenes focused and reusable; avoid editing unrelated scenes in one pull request.
- Test keyboard/mouse and gamepad for changes affecting input.
- Do not commit generated builds, import caches, editor settings, or credentials.

## Naming

- Files, classes, methods, properties, and events: `PascalCase`
- Private fields and local variables: `camelCase`
- Serialized private fields: `camelCase` with `[SerializeField]`
- Constants: `PascalCase`
- GameObjects and prefabs: descriptive `PascalCase`

## Pull requests

- Complete the pull-request template.
- Link the relevant issue or project item.
- Describe how the change was tested.
- Include a screenshot or short capture for visual changes.
- Keep refactors separate from feature work when practical.
- Resolve review comments or record the agreed follow-up task.

## Review checklist

- Behaviour matches the task acceptance criteria.
- Teleport destinations and attacks cannot escape authored bounds.
- Visual and audio telegraphs remain readable.
- No unrelated assets or settings changed.
- New exported properties have useful defaults and tooltips.
- Documentation and tests are updated when required.

## Reporting problems

Use the bug template. Include reproduction steps, expected behaviour, actual behaviour, build/commit, input device, and supporting media when available. Never include passwords, tokens, or private account information.
