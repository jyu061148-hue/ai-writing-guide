# How AI Detectors Work — Know What You're Up Against

## Core Metrics

### Perplexity
How "surprising" the word choices are. AI text is *predictable* — each word follows statistically from the last. Human text is more varied and unexpected.

- **Low perplexity** = predictable = flagged as AI
- **High perplexity** = surprising word choices = reads as human

### Burstiness
How much sentence length and structure *varies*. AI writes uniform sentences. Humans mix short and long, simple and complex.

- **Low burstiness** = uniform = flagged as AI
- **High burstiness** = varied = reads as human

## Major Detection Tools

### Turnitin
- Used by most universities
- Analyzes sentence structure, vocabulary complexity, stylistic consistency
- Claims <1% false positive rate (for submissions >20% AI)
- Now detects paraphrased/spun AI text
- Provides sentence-level highlighting showing which parts look AI-generated

### GPTZero
- Widely used, free tier available
- ~9% false positive rate (2026 testing)
- Struggles more with short texts and very long texts
- Uses perplexity + burstiness scoring

### Originality.ai
- Paid tool, popular with content marketers
- Tests against multiple AI models (GPT-4, Claude, etc.)

## What Triggers False Positives (Flagging Human Text as AI)

These things can get *your own writing* falsely flagged:

1. **Over-editing with Grammarly** — especially "Rewrite" and "Rephrase" features. These smooth out your natural voice.
2. **Overly formal academic phrasing** — standardized, template-y writing
3. **Consistent sentence structure** — not enough variation
4. **Short submissions** — detectors need enough text to analyze
5. **Non-native English patterns** — known bias in detectors against ESL writers
6. **Using AI for outlining then writing yourself** — the structure can carry AI patterns even if words are yours

## What Detectors Can't Catch Well

- Text that's been genuinely rewritten with human voice and specifics
- Mixed human/AI text where AI was used for brainstorming only
- Domain-specific technical writing (detectors are trained mostly on general text)
- Text with strong personal voice, opinions, and specific examples

## Practical Defense

1. **Keep your drafts** — save iterations so you can show your writing process
2. **Pre-check if allowed** — run through GPTZero before submitting
3. **Don't panic if flagged** — false positives happen. Multiple detectors give different results.
4. **The best defense is good writing** — specific details, varied structure, genuine voice. These naturally defeat detectors because they're what makes writing *actually human*.

---

*Update this as detection tools evolve — this is a fast-moving space.*
