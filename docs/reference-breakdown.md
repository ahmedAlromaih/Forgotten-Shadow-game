# Reference Breakdown

## Selected benchmark scene

**Dead Cells — Hand of the King boss encounter**

This encounter is the primary benchmark because it demonstrates how a side-view action game can stage a climactic arena fight using readable telegraphs, rapid movement, environmental hazards, phase escalation, and short recovery windows. The proposed scene does not reproduce its attacks, art style, or layout. It uses the encounter as a standard for clarity, pace, and mechanical testing while implementing the space with 3D assets in Unity.

The wider design also draws supporting principles from *Dishonored* for teleportation, *Hotline Miami* for decisiveness and rapid retries, and *My Friend Pedro* for stylish movement chains. Those influences remain secondary so the team has one clear benchmark for production review.

## Mechanics

### Benchmark decomposition

- A bounded arena keeps the encounter focused.
- Attacks have distinct anticipation, execution, and recovery phases.
- Ground hazards force vertical or lateral repositioning.
- The boss alternates between direct attacks and arena-control patterns.
- Later phases remix learned actions instead of introducing an entirely new ruleset.
- Safe damage windows reward recognizing patterns rather than trading health.
- Failure leads back to a fast, understandable retry loop.

### Adaptation

The King’s Chamber uses the same principles but changes the objective. The Shadow King is an invulnerable source of pressure rather than a conventional health-bar target. His projectiles control space while the player crosses the arena to break seals.

Teleportation replaces much of the benchmark's roll-and-jump response. Every attack must define when teleporting is useful, when normal movement is sufficient, and where the player can safely arrive. Guardian fights prepare the player through isolated lessons before the final encounter combines them.

The scene's expected interaction set is deliberately small:

| Input | Function |
|---|---|
| Move | Ground and air positioning |
| Jump/drop | Platform navigation |
| Sword attack | Damage, object breaking, charge recovery |
| Teleport | Traversal, evasion, backstab positioning |
| Ability | Contextual guardian power |
| Shadow Sight | Reveal hidden targets and magical links |

## Visuals

### Benchmark decomposition

- Strong separation between player, boss, hazards, and background.
- Large boss silhouette remains recognizable during effects-heavy attacks.
- Telegraph colours are consistent and appear before damage occurs.
- Arena boundaries and hazard zones are visually explicit.
- Background detail supports atmosphere without competing with combat information.

### Adaptation

The scene uses a dark ruined-palace palette with restrained values. Interactive magic receives saturated colour coding: orange for fire, cyan for water, violet-white for lightning, and pale gold for revealed ritual connections. Enemy attacks use magenta-black so they cannot be confused with player powers.

The 2.5D presentation uses a perspective camera with a narrow field of view, locked combat depth, and carefully framed 3D rooms. A small modular kit—floor segments, arches, pillars, platforms, cage parts, and three background set pieces—is reused with different arrangements, materials, fog, and lighting. Bosses use 3D rigs so shared locomotion, hit reactions, and base attack animations can be retargeted instead of drawing unique sprite frames.

The three guardian rooms share architectural materials but each has a distinct silhouette and hazard layer. Stained glass, books, and mosaics communicate weaknesses. In the throne room, the cage remains visible in the background from the start, while Shadow Sight moves its ritual connections into the active gameplay layer.

Visual-effects density must never hide teleport destinations or projectile edges. The player silhouette receives a thin high-contrast rim light, and the teleport marker changes state for valid, obstructed, and out-of-range destinations. Depth-of-field remains subtle or disabled during combat to prevent gameplay objects from becoming unclear.

## Audio

### Benchmark decomposition

- Each attack family has a unique warning sound.
- Impact sounds confirm successful hits and parries.
- Music escalates with encounter phases.
- Brief reductions in music or ambience make major attacks readable.
- Boss vocalizations reinforce animation telegraphs.

### Adaptation

Each King projectile has a unique cue before it appears: a rising whisper for tracking orbs, a sharp tonal line for the beam, and three paced pulses for the portal barrage. Teleportation uses a short vacuum followed by a directional arrival impact. A successful sword hit, magic drain, broken seal, and invalid attack on the King's regenerating body each require distinct feedback.

The guardian themes add one musical layer after each victory. All three layers combine in the throne room, then fall away when the player enters the cage. The sorcerer's warning plays over near-silence so the final choice is readable and emotionally weighted.

## Interaction complexity

| Layer | Benchmark | Proposed scene | Complexity control |
|---|---|---|---|
| Movement | Run, jump, roll | Run, jump, teleport | Three teleport charges and fixed range |
| Offence | Multiple equipped weapons | One sword plus one contextual ability | No weapon switching in the slice |
| Defence | Dodge, positioning | Teleport, Tidal Guard | One-hit shield with clear cooldown |
| Boss reading | Learn telegraphs and phases | Learn telegraphs, clues, and weaknesses | One weakness per guardian |
| Arena | Platforms and hazards | 3D hazards, seals, valid teleport surfaces on a 2D plane | Authored modular rooms, no procedural layout |
| Progression | Build assembled across a run | Three fixed powers across the scene | No random item pool in the slice |

The greatest added complexity is aiming teleportation while reading dense projectiles. The prototype must validate this interaction before art production. Aim assistance, brief time dilation while choosing a destination, and controller-stick snapping are acceptable accessibility options if free aiming proves unreliable.

## Benchmark acceptance criteria

The scene meets the benchmark when:

- A first-time player can identify the source and direction of every damaging event.
- Each major attack is recognizable from silhouette and sound alone.
- A skilled player can complete the finale without taking damage.
- Death-to-retry time stays below eight seconds.
- The final room escalates by combining learned systems, not by adding unexplained rules.
- Combat effects remain readable at the target resolution and frame rate.
