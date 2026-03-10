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

### Performance

| Skill | Mindset | Use when... |
|---|---|---|
| `/shannon` | [Shannon](performance/shannon.md) | Data crosses boundaries and meaning gets lost. Traces information flow and signal degradation. |
| `/von-neumann` | [von Neumann](performance/von-neumann.md) | Design looks elegant but runs slow. Audits allocation, copying, I/O, and machine cost. |

### Testing

| Skill | Mindset | Use when... |
|---|---|---|
| `/popper` | [Popper](testing/popper.md) | Design sounds convincing but isn't tested against failure. Extracts claims and designs falsification tests. |

### Strategy

| Skill | Mindset | Use when... |
|---|---|---|
| `/deming` | [Deming](strategy/deming.md) | Bugs recur despite fixes. Looks beyond the code to the system that produced the failure. |
| `/hamming` | [Hamming](strategy/hamming.md) | Team is busy but not advancing. Identifies whether work targets high-leverage problems. |

## Recommended Pairings

| Scenario | Combination | Why |
|---|---|---|
| Bug fixes & refactors | `/feynman` + `/dijkstra` | Feynman finds the confusion, Dijkstra structures the fix |
| Architecture & API design | `/einstein` + `/turing` | Einstein identifies what's necessary, Turing makes it executable |
| Performance & distributed systems | `/shannon` + `/von-neumann` | Shannon traces information flow, von Neumann measures machine cost |
| Reliability & production review | `/popper` + `/deming` | Popper tests assumptions, Deming fixes the system |
| New feature planning | `/hamming` + `/einstein` | Hamming questions priorities, Einstein questions assumptions |

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
