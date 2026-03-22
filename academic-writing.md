# Academic Writing — Passing AI Detection While Staying Scholarly

Tested on QuillBot's AI Detector. AI-style academic paragraph scored 100% AI. Rewritten academic version scored 80% human / 17% AI.

## What Works in Academic Prose

### 1. Specific Numbers Over Vague Claims
- ❌ "achieved remarkable performance metrics"
- ✅ "scored 0.95 AUC for cardiomegaly on ChestX-ray14"
- ✅ "a 12-point gain in balanced accuracy"
- ✅ "fewer than 10,000 annotated examples"

### 2. Name Real Things
- ❌ "recent studies have demonstrated"
- ✅ "Park and Kim (2022) saw..."
- ❌ "diverse clinical settings"
- ✅ "three community hospitals running older imaging hardware"
- ❌ "underserved populations"
- ✅ "a safety-net hospital in rural Mississippi"

### 3. Have Opinions (Academic Writing Allows This)
- ✅ "The assumption that features transfer cleanly is questionable"
- ✅ "Augmentation strategies deserve more scrutiny than they typically receive"
- ✅ "We know this, yet deployment decisions rarely account for it"
- ✅ "Benchmark performance is necessary but insufficient"

Academic writing is not the same as neutral writing. Strong claims backed by evidence read as human.

### 4. Use Concrete Analogies
- ❌ "features may not generalize across domains"
- ✅ "features learned from photographs of dogs and cars don't transfer cleanly to histopathology slides"

### 5. Vary Sentence Length Aggressively
Mix within paragraphs:
- Short: "The gap is not surprising."
- Medium: "Benchmark performance is necessary but insufficient."
- Long: "A ResNet model that scored 0.95 AUC for cardiomegaly on ChestX-ray14 dropped to 0.78 sensitivity at three community hospitals running older imaging hardware."

### 6. Use Semicolons
Academic writing uses semicolons more than any other genre. AI avoids them. This alone is a strong signal.

- ✅ "ImageNet pretraining helps; Park and Kim (2022) saw a 12-point gain"
- ✅ "The regulatory framework was not designed for this; neither was the clinical workflow"

### 7. Casual Insertions in Formal Prose
A light touch of informality within otherwise academic text reads as authentically human:
- "almost reflexive at this point"
- "if you consider that"
- "nobody has resolved what it means to..."
- "looks nothing like what a rural clinic produces"

Don't overdo this — one or two per section is enough.

## What to Avoid in Academic AI Writing

### Transition Word Stacking
- ❌ "Moreover... Furthermore... Additionally... In conclusion..."
- ✅ Just move to the next point. The logic should carry the reader.

### The Template Abstract
- ❌ "This paper delves into the multifaceted implications of..."
- ✅ Start with what you found or what problem you're solving

### Nominalizations
- ❌ "The implementation of the strategy resulted in an improvement"
- ✅ "Implementing the strategy improved..."

### Empty Qualifiers
- ❌ "comprehensive," "significant," "remarkable," "noteworthy"
- ✅ Say what makes it significant: "a 12-point improvement" is remarkable without the word

### The Hedge Stack
- ❌ "It is important to note that this may potentially suggest..."
- ✅ "This suggests..." or better, "The data show..."

## Tested Results (QuillBot AI Detector)

| Version | AI % | Human % |
|---|---|---|
| Standard AI academic paragraph | 100% | 0% |
| First rewrite (specifics added) | 62% | 38% |
| Second rewrite (voice + opinion + structure) | 17% | 80% |

The biggest gains came from:
1. Replacing vague claims with specific data points
2. Adding genuine analytical voice and opinions
3. Varying sentence structure dramatically
4. Using semicolons
5. Naming real datasets, models, places, and researchers

---

*Test your own rewrites on QuillBot, GPTZero, or Turnitin to calibrate.*
