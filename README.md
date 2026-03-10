# Software Analysis Mindsets

Cross-language thinking models for analyzing software — as readable guides and as executable [Claude Code](https://docs.anthropic.com/en/docs/claude-code) slash commands.

These are not tied to one programming language or framework. Treat them as lenses to apply when a problem feels unclear, unstable, or overcomplicated.

## Quick Start

Clone this repo into any project and start using the slash commands:

```bash
# Copy the .claude/commands/ directory into your project
cp -r .claude/commands/ /path/to/your/project/.claude/commands/

# Then in Claude Code, use them with:
/feynman src/auth.ts
/dijkstra src/utils/parser.ts
/popper src/services/payment.ts
/grothendieck src/domain/billing
/tao src/migrations/v2
/lamport src/events/
/ostrom src/platform/
```

Or use them directly from this repo — Claude Code auto-discovers `.claude/commands/` in the working directory.

## Mindsets & Skills

### Debugging

| Skill | Mindset | Use when... |
|---|---|---|
| `/feynman` | [Feynman](debugging/feynman.md) | Code works but no one can explain why. Strips jargon, exposes hidden confusion. |
| `/dijkstra` | [Dijkstra](debugging/dijkstra.md) | Code works but is too hard to verify or trust. Audits hidden state and reasoning burden. |

### Architecture

| Skill | Mindset | Use when... |
|---|---|---|
| `/einstein` | [Einstein](architecture/einstein.md) | Design rests on habit, not necessity. Separates real constraints from convention. |
| `/newton` | [Newton](architecture/newton.md) | State changes feel surprising. Maps state, forces, and invariants. |
| `/turing` | [Turing](architecture/turing.md) | Intent doesn't match implementation. Verifies procedures terminate and handle all cases. |
| `/liskov` | [Liskov](architecture/liskov.md) | Interface implementations behave inconsistently. Audits substitutability and contract safety. |
| `/lamport` | [Lamport](architecture/lamport.md) | Distributed ordering assumptions are unclear. Checks happens-before and race risks. |
| `/hoare` | [Hoare](architecture/hoare.md) | Critical logic needs explicit guarantees. Defines preconditions, postconditions, and invariants. |
| `/hopper` | [Hopper](architecture/hopper.md) | Teams are slowed by boilerplate and accidental complexity. Promotes tooling and better abstractions. |

### Performance

| Skill | Mindset | Use when... |
|---|---|---|
| `/shannon` | [Shannon](performance/shannon.md) | Data crosses boundaries and meaning gets lost. Traces information flow and signal degradation. |
| `/von-neumann` | [von Neumann](performance/von-neumann.md) | Design looks elegant but runs slow. Audits allocation, copying, I/O, and machine cost. |
| `/wiener` | [Wiener](performance/wiener.md) | Control loops oscillate under load. Stabilizes retries, autoscaling, and feedback delays. |
| `/taleb` | [Taleb](performance/taleb.md) | Rare events create outsized damage. Maps fragility and tail-risk controls. |

### Testing

| Skill | Mindset | Use when... |
|---|---|---|
| `/popper` | [Popper](testing/popper.md) | Design sounds convincing but isn't tested against failure. Extracts claims and designs falsification tests. |
| `/polya` | [Polya](testing/polya.md) | Complex bugs are hard to attack. Breaks failures into solvable evidence-driven steps. |

### Strategy

| Skill | Mindset | Use when... |
|---|---|---|
| `/deming` | [Deming](strategy/deming.md) | Bugs recur despite fixes. Looks beyond the code to the system that produced the failure. |
| `/hamming` | [Hamming](strategy/hamming.md) | Team is busy but not advancing. Identifies whether work targets high-leverage problems. |
| `/grothendieck` | [Grothendieck](strategy/grothendieck.md) | One-off fixes keep repeating. Lifts recurring problems into stronger shared abstractions and invariants. |
| `/tao` | [Tao](strategy/tao.md) | Goals are complex and blocked. Decomposes work into validated subproblems with clear checkpoints. |
| `/ostrom` | [Ostrom](strategy/ostrom.md) | Shared platform assets degrade over time. Designs rules and ownership for software commons. |
| `/simon` | [Simon](strategy/simon.md) | Analysis paralysis blocks progress. Chooses bounded-rational, good-enough decisions. |
| `/boyd` | [Boyd](strategy/boyd.md) | Teams react too slowly. Tightens observe-orient-decide-act loops. |
| `/meadows` | [Meadows](strategy/meadows.md) | Local fixes fail repeatedly. Finds highest-leverage system interventions. |
| `/jacobs` | [Jacobs](strategy/jacobs.md) | Architecture over-centralizes or fragments. Balances modular diversity with coherent interfaces. |

## Recommended Pairings

| Scenario | Combination | Why |
|---|---|---|
| Bug fixes & refactors | `/feynman` + `/dijkstra` | Feynman finds the confusion, Dijkstra structures the fix |
| Architecture & API design | `/einstein` + `/turing` | Einstein identifies what's necessary, Turing makes it executable |
| Performance & distributed systems | `/shannon` + `/von-neumann` | Shannon traces information flow, von Neumann measures machine cost |
| Reliability & production review | `/popper` + `/deming` | Popper tests assumptions, Deming fixes the system |
| New feature planning | `/hamming` + `/einstein` | Hamming questions priorities, Einstein questions assumptions |
| Structural refactors | `/grothendieck` + `/dijkstra` | Grothendieck upgrades abstraction boundaries, Dijkstra keeps local reasoning explicit |
| Complex migrations | `/tao` + `/popper` | Tao decomposes execution into checkpoints, Popper falsifies risky assumptions |
| Shared platform governance | `/ostrom` + `/deming` | Ostrom defines commons rules, Deming improves the surrounding system |
| Distributed correctness | `/lamport` + `/hoare` | Lamport validates ordering assumptions, Hoare formalizes local guarantees |
| Incident adaptation speed | `/boyd` + `/wiener` | Boyd tightens decision cycles, Wiener stabilizes control loops |
| Resilience under tail risk | `/taleb` + `/popper` | Taleb maps fragility, Popper designs falsification tests |
| Practical architecture decisions | `/simon` + `/einstein` | Simon sets satisficing thresholds, Einstein checks first principles |

## Mindset Index

Alphabetical quick index of all available mindsets and slash commands.

| Mindset | Skill | Category | Link |
|---|---|---|---|
| Boyd | `/boyd` | Strategy | [strategy/boyd.md](strategy/boyd.md) |
| Deming | `/deming` | Strategy | [strategy/deming.md](strategy/deming.md) |
| Dijkstra | `/dijkstra` | Debugging | [debugging/dijkstra.md](debugging/dijkstra.md) |
| Einstein | `/einstein` | Architecture | [architecture/einstein.md](architecture/einstein.md) |
| Feynman | `/feynman` | Debugging | [debugging/feynman.md](debugging/feynman.md) |
| Grothendieck | `/grothendieck` | Strategy | [strategy/grothendieck.md](strategy/grothendieck.md) |
| Hamming | `/hamming` | Strategy | [strategy/hamming.md](strategy/hamming.md) |
| Hoare | `/hoare` | Architecture | [architecture/hoare.md](architecture/hoare.md) |
| Hopper | `/hopper` | Architecture | [architecture/hopper.md](architecture/hopper.md) |
| Jacobs | `/jacobs` | Strategy | [strategy/jacobs.md](strategy/jacobs.md) |
| Lamport | `/lamport` | Architecture | [architecture/lamport.md](architecture/lamport.md) |
| Liskov | `/liskov` | Architecture | [architecture/liskov.md](architecture/liskov.md) |
| Meadows | `/meadows` | Strategy | [strategy/meadows.md](strategy/meadows.md) |
| Newton | `/newton` | Architecture | [architecture/newton.md](architecture/newton.md) |
| Ostrom | `/ostrom` | Strategy | [strategy/ostrom.md](strategy/ostrom.md) |
| Polya | `/polya` | Testing | [testing/polya.md](testing/polya.md) |
| Popper | `/popper` | Testing | [testing/popper.md](testing/popper.md) |
| Shannon | `/shannon` | Performance | [performance/shannon.md](performance/shannon.md) |
| Simon | `/simon` | Strategy | [strategy/simon.md](strategy/simon.md) |
| Taleb | `/taleb` | Performance | [performance/taleb.md](performance/taleb.md) |
| Tao | `/tao` | Strategy | [strategy/tao.md](strategy/tao.md) |
| Turing | `/turing` | Architecture | [architecture/turing.md](architecture/turing.md) |
| von Neumann | `/von-neumann` | Performance | [performance/von-neumann.md](performance/von-neumann.md) |
| Wiener | `/wiener` | Performance | [performance/wiener.md](performance/wiener.md) |

## Usage Tips

- Use **one** skill when you need clarity fast
- Combine **two** when a problem has both design and operational dimensions
- Avoid stacking many lenses on a trivial task
- Each skill reads your actual code and produces a structured report with file/line references

## Installation

### Per-project (recommended for teams)

Copy `.claude/commands/` into your project's `.claude/` directory. Commit it to share with the team.

```bash
cp -r .claude/commands/ /path/to/your/project/.claude/commands/
```

### Global (all projects)

Copy the command files to your personal Claude Code config:

```bash
mkdir -p ~/.claude/commands
cp .claude/commands/*.md ~/.claude/commands/
```

## License

Open source. Use, modify, and share freely.
