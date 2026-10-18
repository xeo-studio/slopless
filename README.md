# Slopless

No model has driven home in silence after a bad day, landed in a city where it knows no
one, or burned the first pancake and eaten it anyway. Writing gets its weight from lived
experience, and every person's experience is different from every other person's who has
ever been alive. That is the one ingredient a model cannot supply, and it is the reason
your writing is worth doing yourself.

This tool does not exist to write instead of you. It exists to strip out the machine
patterns that creep in when software touches your words, so that what remains sounds like
you. Keep writing. Keep telling people what you have seen. Nobody else can.

---

A skill that writes, edits, and audits marketing and SEO content so it reads like a
knowledgeable person wrote it, and so every claim on the page is true. Works with ChatGPT,
Claude, [Claude Code](https://claude.com/claude-code), Codex, Cursor, or any AI tool that
accepts instructions; it is plain language, not code.

Built for agencies publishing real businesses' websites. Beyond the usual anti-AI-slop
editing (buzzwords, setup phrases, colon drama, importance puffery, mic-drop endings), it
enforces rules generic de-sloppers don't:

- **Factual integrity.** Never fabricate stats, results, credentials, or testimonials.
  Unknown facts get `[VERIFY]` markers, and markers never ship to production.
- **YMYL care** for legal, medical, and financial content.
- **Local means local.** City pages must contain facts true only of that city. If a paragraph
  survives a find-and-replace to another town, it fails.
- **Client quotes are read-only** and appear once per page.
- **Zero em dashes.**

## Install

The quickest way: paste this into Claude Code, Codex, Cursor, or your coding agent of choice:

```text
Install the /slopless skill from https://github.com/xeo-studio/slopless
```

Or install with the skills CLI (supports Claude Code, Codex, Cursor, and more):

```sh
npx skills add xeo-studio/slopless --skill slopless
```

Manual install for Claude Code, project-level (loads for one repo):

```bash
git clone https://github.com/xeo-studio/slopless /tmp/slopless
mkdir -p .claude/skills && cp -r /tmp/slopless/skills/slopless .claude/skills/
```

Global (all projects): copy to `~/.claude/skills/` instead.

Any other model (ChatGPT Projects, Gemini, a custom GPT): paste the contents of
[`skills/slopless/SKILL.md`](skills/slopless/SKILL.md) into the system prompt or custom
instructions, and [`eval.md`](skills/slopless/eval.md) alongside it if the tool allows a
second file. The skill is plain instructions; nothing about it requires a specific model.

## Use

Write new content under the rules:

```text
/slopless write a service page for a mobile dog grooming business in Austin
```

Edit a draft (minimum change, voice preserved, "What changed" included):

```text
/slopless (your draft)
```

Audit without rewriting; returns named patterns with quotes and fixes:

```text
/slopless is this slop? (your draft)
```

## The slop it catches

1. **Binary contrasts.** "It's not luck. It's strategy."
2. **Throat-clearing.** "Here's the thing," "Let's be honest," "The honest answer:"
3. **Colon drama.** "The best part: it compounds."
4. **Importance puffery.** "marks a pivotal moment," "a testament to"
5. **Participial tails.** "...highlighting our commitment to excellence"
6. **Hidden verbs.** "made a decision" instead of "decided"
7. **Unnamed authority.** "experts agree," "studies show"
8. **Synonym cycling.** "the firm... the practice... the office," all one company
9. **Dramatic fragments.** "Fast. Fair. Effective."
10. **Mic-drop endings.** "In the end, it's not about houses. It's about stories."
11. **Metronome rhythm.** Every sentence 15 to 25 words, forever.
12. **Templatic empathy.** "We understand how stressful this can be."
13. **Forced sunshine.** A bad fact instantly neutralized with "...but don't worry!"
14. **Buzzwords.** Delve, seamless, elevate, robust, transformative, and friends.

And the checks generic de-sloppers skip:

- **Invented facts.** Stats, testimonials, and credentials no one can back up get flagged
  `[VERIFY]`, and markers never ship to production.
- **Copy-paste localness.** A city page that survives a find-and-replace to another city fails.
- **Quote integrity.** Client quotes are never reworded, and appear once per page.
- **Reader's-world examples.** Scenarios the audience would recognize from their own week.
- **Em dashes.** Zero.

## Grounded in research

The rules are not vibes. The banned-word list, the participial-tail and nominalization
patterns, and the sentence-rhythm checks map to published corpus studies of how LLM text
measurably differs from human writing (Kobak et al. 2024; Liang et al., ICML 2024;
Reinhart et al., CMU 2024; Munoz-Ortiz et al. 2023). See
[skills/slopless/RESEARCH.md](skills/slopless/RESEARCH.md) for the findings and how each
maps to a rule.

## License

Source-available under the Xeo Studio Customer License: you can read and
evaluate the code freely; using it in your business requires an active
service agreement with [Xeo Studio](https://getxeo.com). The license ends
when the customer relationship does. See [LICENSE](LICENSE).
