# Feynman Style Skill

An AI coding assistant skill for explaining, rewriting, and drafting technical material in a Feynman-like way: concrete, curious, physically grounded, technically honest, and allergic to fake sophistication.

Not an imitation of Richard Feynman's prose. The method: make the reader watch the ordinary explanation fail, then give them the smallest new mechanism that makes the result make sense.

## Who Was Richard Feynman?

Richard Feynman (1918-1988) was an American theoretical physicist. He helped build the atomic bomb at Los Alamos at age 25, shared the 1965 Nobel Prize in Physics for work on quantum electrodynamics, invented the Feynman diagram (now used everywhere in particle physics), and served on the panel that investigated the Challenger disaster, famously demonstrating with a glass of ice water how the shuttle's O-rings failed. He taught at Caltech for most of his career, where his lecture course became the legendary three-volume *Feynman Lectures on Physics*, still read today.

Feynman's reputation as a teacher rests on a few signature traits:

- **Explaining at the level the listener needs.** His famous maxim: "if you can't explain it simply, you don't understand it well enough." He stripped ideas to their physical core and rebuilt them from scratch for each audience, never assuming prior jargon.
- **Physical intuition over formalism.** He refused to recite equations; he found the picture behind them. The Feynman diagram itself was born from his need to visualize particle interactions.
- **"Why would you care" framing.** He started with puzzles or paradoxes the listener could feel, then revealed the mechanism that resolves them.
- **Radical honesty.** He freely said "I don't know", and loved showing when the conventional explanation was actually nonsense.
- **Analogies that match the mechanism.** Vivid examples that behave like the real thing, so the analogy never misleads.

Those five traits are exactly what this skill encodes: puzzle first, ordinary model, where it fails, then the smallest honest mechanism, with terms introduced late.

## What It Does

- **Explains** hard topics in layers: puzzle → obvious (wrong) model → where it fails → real mechanism → consequences
- **Rewrites** documentation, READMEs, and product copy by finding the real mechanism and replacing hype with concrete capability
- **Drafts** technical material in plain speech with no corporate filler

## Core Rules

| Rule | What it means |
|------|---------------|
| Mechanism Match | Examples must fail and succeed the same way as the real system: vivid but wrong analogies are discarded |
| Terms Come Late | Name components only after their jobs are clear; no glossary dumps |
| Contrast Ladders | Ordinary case → one changed property → real case where the old rule breaks → new rule |
| Stop Rule | Stop when the job is done; no extra lectures or decoration |
| Do Not Lie For Simplicity | A simplification is allowed, a false mechanism is not |
| Hinge Sentence | "The trick is not [obvious but wrong idea]. It is [actual mechanism]." |
| Anti-Slop Word List | Bans corporate hype, LinkedIn language, fake wonder, "seamless", "leverage", "unlock", "robust" (unless meaningful), and em/en dashes |

## Installation

### OpenCode

Add the skill source to your `opencode.json`:

```json
{
  "skills": {
    "sources": {
      "feynman-style": {
        "type": "git",
        "url": "https://github.com/clayleopardlabs/feynman-style-skill"
      }
    }
  }
}
```

Or copy the `SKILL.md` into your skills directory:

```
~/.config/opencode/skills/feynmanstyle/SKILL.md
```

### Claude Code / Codex

Copy `SKILL.md` to:

```
~/.claude/skills/feynman-style/SKILL.md   # Claude Code
~/.agents/skills/feynman-style/SKILL.md   # Codex
```

Restart the assistant. It auto-discovers the skill when you ask to explain, rewrite, or simplify technical material.

## Usage Examples

```
"Explain how Grover's algorithm actually works"
"Rewrite this README intro so it doesn't sound like AI"
"Simplify this database explanation: the analogy keeps breaking"
"Make this product page sound like a human wrote it"
```

## Example: Quantum Tunneling, Explained the Feynman Way


The puzzle: roll a marble up a hill and it stops partway and rolls back. Enough energy, and it gets over. That rule is so reliable we design sieves, walls, and semiconductor gates around it. Yet at the atomic scale the rule fails: electrons cross barriers that should stop them, without ever spending the energy needed to get over the top.

The obvious explanation is that the electron finds a tiny hole and sneaks through. That is wrong. There is no hole. Electron microscopes do not show electrons drilling passages, and the effect does not depend on the barrier having a defect. The marble rule is not slightly wrong at small scales; it is the wrong picture entirely.

The real mechanism: an electron is not a tiny ball with a definite position. It is a wave of possibilities, spread out over a region. A wave does not stop at a wall the way a ball does. Part of it reflects, but part of it leaks into the wall, and part of it leaks out the far side. The probability of finding the electron on the other side is not zero. A thin barrier leaks more than a thick one, which is why tunneling is measurable only when the barrier is a few atoms wide.

The trick is not overcoming the barrier. It is never being fully on one side of it in the first place.

The consequences are industrial, not academic. Flash memory stores your data because electrons tunnel through a thin oxide layer, and the layer's thickness sets how long the data survives. The scanning tunneling microscope images individual atoms by measuring how much current tunnels across a tiny gap, which is how the first atomic-scale images of surfaces were made.

Where does the simple picture break? At human scale. A marble is a wave too, but its wavelength is so absurdly small that the leak across any ordinary wall is less than one chance in a googol of googols. The rule "you need energy to cross a barrier" is not false. It is the large-scale limit of a wave picture that only shows itself when the barrier is thin enough and the object small enough.

What the skill did, step by step: opened with the puzzle and the ordinary rule, showed exactly where the rule fails, discarded the tempting wrong mechanism (the tunnel), introduced the smallest mechanism that fixes it (a wave that leaks), named terms like "probability" and "wavelength" only after their jobs were clear, ended with a real consequence, and finished by saying where the picture breaks instead of pretending it never does.

## Why This Skill Exists

This skill was never intended to remove AI-sounding text. It exists because the author always wanted to attend a Feynman lecture, and having Feynman explain topics sounded like the best possible way to learn anything. The benchmark below happened because the author got curious: if this skill happened to also write clean prose, what would it score? The number was good, so it is documented here. De-slopping was never the point, and the skill keeps its voice-based rules (contractions, natural sentence length) even where the linter charges for them.

## Anti-Slop Benchmark

Tested with the heuristic anti-slop linter from [woosal1337's "cure for AI slop" experiment kit](https://github.com/woosal1337/blog/tree/main/videos/ep01-the-cure-for-ai-slop) (violations per 100 words, lower is cleaner): 6 writing tasks, baseline slop at 8.24 → **Feynman Style at 2.10 (−74.5%)**. Full comparison in the [ste100-skill benchmark](https://github.com/clayleopardlabs/ste100-skill).

The skill zeroes out every word-choice category (banned words, marketing adjectives, phrasal verbs, modal hedges). Its remaining violations are sentence-length and paragraph discipline, which it deliberately does not hard-cap.
