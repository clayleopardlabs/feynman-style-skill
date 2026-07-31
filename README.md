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
| Feynman's Voice | Contractions are mandatory. Every explanation gets a named person in a scene, the listener's objection is answered in their own words, whys chain until they stop at something you feel, the question is reframed before being answered, and honesty is a personal relationship ("I'd be cheating you"). All distilled from the verbatim BBC 1981 "Why Questions" transcript |

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
"Explain how GPS knows where I am"
"Explain how a QR code stores information"
"Explain how a rocket moves in space, where there's no air to push against"
"Explain how git stores my project history"
```


Both examples below were written by DeepSeek V4 Flash, a model not especially known for being a great writer: the structure and word choice come from the skill, not the model.


## Example 1: Why the Sky Is Blue, Explained the Feynman Way

Your kid Danny asks you at breakfast why the sky is blue, and you open your mouth and hear yourself say something about light scattering, and you're not even sure what that means, and honestly it's a perfectly reasonable question, so let's see if we can do better than the words you're not sure about.

First, the question is doing something sneaky. "Why is the sky blue" sounds like it's about the sky. It's actually about sunlight, and about air, and about your eyes, and the sky is just where all three happen to meet. So what does sunlight look like? White. But white isn't a color; it's all the colors mixed. The sun's light is every color at once, and when they mix, you see white.

So why doesn't the whole sky look white? Because air gets in the way. Sunlight hits the gas molecules in the air, and the molecules grab the light and fling it off in a new direction. That's scattering. And here's the whole trick, you see: the molecules are much better at flinging short waves than long ones. Blue is a short wave, so the air grabs blue and throws it everywhere; red is a long wave, so it just sails on through. When you look at the sky away from the sun, you're seeing the blue that got knocked loose and thrown around. The sky isn't blue. It's all the blue the air stole from the sunlight.

And you'll notice, the more I ask why, the deeper it goes, and it stops somewhere you can feel. Why is the sunset red? Because at sunset the sun is low, so its light crosses more air, so more blue gets knocked loose along the way, until only the red is left by the time it reaches you. Why are clouds white? Because clouds are made of big water droplets, and big things scatter everything evenly, so clouds throw all the colors back at you at once, which is white again. And if I told you "the sky is blue because of Rayleigh scattering," I'd be cheating you; that's just the name for the thing we just watched happen.

Now where does the simple picture break? The gas molecules aren't the only thing doing the flinging. Dust and pollution scatter long waves too, so the sky turns whiter, and after a big volcano, people see strange sunsets for a year, same mechanism wearing a different hat. And if you were a student, I could go further: the reason short waves scatter more is that air molecules ring like little antennas, and short waves make them ring louder. But the honest bottom, any way you slice it: the blue you see is the sun's own light doing a U-turn in the air. The sky is the part of the sun you're not looking at.

## Example 2: Why a Site Doesn't Need Your Password

You sign up for a site, it asks for a password, you type one, and later you type it again and the site lets you in. Somewhere, you figure, the site keeps your password in a drawer, and every time you come back it takes yours out, holds it next to the one you just typed, and checks that they match. And that's a perfectly reasonable picture of what's happening. It's also exactly wrong. If I told you the site keeps your password, I'd be cheating you, because the good sites don't have your password at all.

So what does "I forgot my password" actually do, then? Here's the clue: the site doesn't show you your old password. It mails you a new one. Why does it do that? Because it can't. There's nothing to show. The site never had it.

What the site has instead is a fingerprint. When you set your password, the site doesn't save the password; it feeds it to a machine that scrambles it beyond recognition, and it saves only the scrambled version. When you log in, it scrambles the password you just typed and compares the new scrambled version to the old one. If they match, you're in. The original was never needed, any more than a guard needs a copy of your fingerprint on file to recognize your finger when you press it down. You'll notice the site never asks you to confirm the original; it only asks for something that scrambles the same way.

And here's where it stops being clever, you see, and becomes a matter of life and death for a company: the scramble is one-way. You can't un-scramble it. And if you were a student, I could go further: the machine throws part of the information away on purpose, so there's literally nothing to work backward from. So when the site gets hacked, and it will get hacked, the thieves steal a drawer full of fingerprints, and fingerprints are useless to them, except for one attack: guessing. They guess millions of passwords and check which ones scramble into a match. That's why your grandma's password, sunshine123, is the most dangerous thing in the company's drawer, and why a site that promises to "keep your password safe" is lying by its very design. It was never about keeping. It was about not keeping.

Now where does the simple picture break? The one-way machine is only as strong as its own design. Old scrambling machines were fast and predictable, so guesses came a billion a second, and fingerprints started matching. That's why sites keep upgrading their scrambling, and why you get asked to re-enter your password after a breach: the site is re-fingerprinting everyone with a better machine. And the honest bottom, first person: I can't tell you exactly how a stolen fingerprint becomes your password, any better than that, because it's mostly guessing, and the only defense is to be too unlikely to guess. Which is why the weird passphrase you use, the one your sister Tina makes fun of, is quietly the strongest thing in the room.

## Why This Skill Exists

This skill was never intended to remove AI-sounding text. It exists because I always wanted to attend a Feynman lecture, and having Feynman explain topics sounded like the best possible way to learn anything. The benchmark below happened because I got curious: if this skill happened to also write clean prose, what would it score? The number was good, so it is documented here. De-slopping was never the point, and the skill keeps its voice-based rules (contractions, natural sentence length) even where they conflict with that goal.

## Bonus: Anti-Slop Benchmark

Tested with the heuristic anti-slop linter from [woosal1337's "cure for AI slop" experiment kit](https://github.com/woosal1337/blog/tree/main/videos/ep01-the-cure-for-ai-slop) (violations per 100 words, lower is cleaner): 6 writing tasks, baseline slop at 8.24 → **Feynman Style at 2.10 (−74.5%)**. Full comparison in the [ste100-skill benchmark](https://github.com/clayleopardlabs/ste100-skill).

The skill zeroes out every word-choice category (banned words, marketing adjectives, phrasal verbs, modal hedges). Its remaining violations are sentence-length and paragraph discipline, which it deliberately does not hard-cap.
