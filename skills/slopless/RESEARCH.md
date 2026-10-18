# Why these rules: the evidence

Slopless rules are grounded in peer-reviewed analyses of how LLM text measurably differs
from human writing. Each finding below maps to specific rules in SKILL.md and checks in
eval.md.

## Lexical signatures → "Words that get cut"

- Kobak et al., "Delving into LLM-assisted writing in biomedical publications through
  excess vocabulary" (arXiv:2406.07016). Analyzed 15M+ PubMed abstracts (2010-2024).
  "Delves" appeared in ~25x more 2024 papers than the pre-LLM trend predicts;
  "showcasing" and "underscores" rose ~9x. Estimated at least 13.5% of 2024 abstracts
  were LLM-processed.
- Liang et al., "Monitoring AI-Modified Content at Scale" (ICML 2024, arXiv:2403.07183).
  In AI-conference peer reviews, words like "commendable," "meticulous," and "intricate"
  became 10-35x more likely per sentence after ChatGPT's release.

## Grammatical signatures → "Participial tails," "Nominalization stacking"

- Reinhart et al., "Do LLMs write like humans? Variation in grammatical and rhetorical
  styles" (arXiv:2410.16107, Carnegie Mellon). Instruction-tuned models (GPT-4o, Llama 3)
  use present participial clauses at 2-5x the human rate and nominalizations at 1.5-2x.
  These are among the most robust machine signatures found to date.

## Rhythm and uniformity → "Metronome sentences," "Identical shapes"

- Munoz-Ortiz et al., "Contrasting Linguistic Patterns in Human and LLM-Generated News
  Text" (arXiv:2308.09067). Human sentence-length distributions are far more scattered;
  LLM output clusters in a narrow band. Human text also shows greater vocabulary variety.
- "Distinguishing Chatbot from Human" (arXiv:2408.04647). GPT sentences trend longer and
  uniformly long, favoring complex multi-clause structures, while human writing spans a
  wider complexity range.

## Emotional flatness → "Emotional flatness" section

- Guo et al., "How Close is ChatGPT to Human Experts?" (arXiv:2301.07597, the HC3 corpus).
  ChatGPT answers are more formal, less emotional, and more objective than human experts';
  humans convey feeling through subjective expression and punctuation, while the model
  substitutes connectives and logical-flow adverbs.
- Munoz-Ortiz et al. (arXiv:2308.09067). Human news text carries stronger negative emotion
  (fear, disgust) and less joy than LLM text.
- "Human Variability vs. Machine Consistency" (arXiv:2412.03025). Human texts are more
  emotional overall; anger in particular is more prevalent in human writing.
- ICWSM 2026 study of climate posts across Gemma, Llama 3/3.3, and Claude: models
  systematically attenuate negative emotion, shifting toward neutral or positive, with
  reduced emotional intensity.
- "AI generates well-liked but templatic empathic responses" (arXiv:2604.08479). Raters
  like AI empathy, but it is formulaic, which is the basis for the templatic-empathy rule:
  specific acknowledgment beats portable sympathy.

## What this means for detection claims

None of these methods can prove a single page was AI-written; they describe corpus-level
statistical signatures. That is why slopless audit mode names concrete patterns with
quotes instead of issuing an "AI score." The goal is not beating detectors. Removing these
patterns makes writing better by human standards: more specific, more varied, more alive.
