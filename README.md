# Feynman Style Skill

An AI coding assistant skill for explaining, rewriting, and drafting technical material in a Feynman-like way — concrete, curious, physically grounded, technically honest, and allergic to fake sophistication.

Not an imitation of Richard Feynman's prose. The method: make the reader watch the ordinary explanation fail, then give them the smallest new mechanism that makes the result make sense.

## What It Does

- **Explains** hard topics in layers: puzzle → obvious (wrong) model → where it fails → real mechanism → consequences
- **Rewrites** documentation, READMEs, and product copy by finding the real mechanism and replacing hype with concrete capability
- **Drafts** technical material in plain speech with no corporate filler

## Core Rules

| Rule | What it means |
|------|---------------|
| Mechanism Match | Examples must fail and succeed the same way as the real system — vivid but wrong analogies are discarded |
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
"Simplify this database explanation — the analogy keeps breaking"
"Make this product page sound like a human wrote it"
```

## Anti-Slop Benchmark

Tested with the heuristic anti-slop linter from [woosal1337's "cure for AI slop" experiment kit](https://github.com/woosal1337/blog/tree/main/videos/ep01-the-cure-for-ai-slop) (violations per 100 words, lower is cleaner): 6 writing tasks, baseline slop at 8.24 → **Feynman Style at 2.10 (−74.5%)**. Full comparison in the [ste100-skill benchmark](https://github.com/clayleopardlabs/ste100-skill).

The skill zeroes out every word-choice category (banned words, marketing adjectives, phrasal verbs, modal hedges). Its remaining violations are sentence-length and paragraph discipline, which it deliberately does not hard-cap.
