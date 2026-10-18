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

A [Claude Code](https://claude.com/claude-code) skill that writes, edits, and audits marketing
and SEO content so it reads like a knowledgeable person wrote it, and so every claim on the
page is true.

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

Project-level (loads for one repo):

```bash
mkdir -p .claude/skills
cp -r skills/slopless .claude/skills/
```

Global (all projects): copy to `~/.claude/skills/` instead.

## Use

- Write: ask Claude to draft content; the skill applies automatically and self-checks
  against `skills/slopless/eval.md`.
- Edit: "de-slop this draft" / `/slopless` with a draft.
- Audit: "does this page read as AI?" returns named patterns with quotes and fixes, no rewrite.

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
