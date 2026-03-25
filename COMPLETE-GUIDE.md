# Complete Guide: Writing Academic Prose That Passes AI Detection

Everything learned from 30+ QuillBot AI Detector trials on academic ML writing. Covers the formula, the pitfalls, sentence-level patterns, and how to use QuillBot for testing.

---

## Table of Contents

1. [How to Use QuillBot AI Detector](#how-to-use-quillbot-ai-detector)
2. [The Core Problem](#the-core-problem)
3. [The Formula That Works](#the-formula-that-works)
4. [What to Avoid](#what-to-avoid)
5. [Opening Sentences](#opening-sentences)
6. [Citation Patterns](#citation-patterns)
7. [Sentence-Level Patterns](#sentence-level-patterns)
8. [Paragraph Structure](#paragraph-structure)
9. [Word-Level Swaps](#word-level-swaps)
10. [Section-by-Section Risk Map](#section-by-section-risk-map)
11. [Topic Dependency](#topic-dependency)
12. [Formal Perplexity Boosters](#formal-perplexity-boosters)
13. [Tested Examples: Before and After](#tested-examples-before-and-after)
14. [Quick Checklist](#quick-checklist)

---

## How to Use QuillBot AI Detector

**URL:** https://quillbot.com/ai-content-detector

**Steps:**
1. Go to the URL above
2. Click on the text editor area (the large contenteditable box)
3. Paste your text (Cmd+V or use the "Paste text" button)
4. Wait for the word count to appear at the bottom of the editor
5. Click the "Detect AI" button at the bottom
6. Wait 10-20 seconds for results

**Reading the results:**
- **AI-generated %** (orange): Text the detector thinks was written by AI
- **Human-written & AI-refined %** (blue/purple): Text that looks like AI output that was edited by a human
- **Human-written %** (white): Text the detector thinks a human wrote

**Highlighted text in the editor:**
- Orange highlighted = flagged as AI-generated
- Blue highlighted = flagged as AI-refined
- White/no highlight = passed as human

**"Main AI Contributors" panel** on the right shows which specific sentences triggered the detection, with confidence levels (Low, Moderate, High).

**Tips for using the detector:**
- Test sections individually, not the whole paper at once (isolates problems)
- If you get 0% on all sections individually, the full paper will likely pass too
- The detector needs at least ~50 words to give meaningful results
- Results can vary slightly between runs on the same text (run twice if borderline)

---

## The Core Problem

AI detectors measure two things:

1. **Perplexity** (how predictable the word choices are). AI text is predictable because it picks the most statistically likely next word. Low perplexity = flagged as AI.

2. **Burstiness** (how much sentence length and structure varies). AI writes uniform sentences. Low burstiness = flagged as AI.

The challenge for academic writing: scholarly prose is inherently more formal and structured than casual writing, which makes it look more like AI output. The goal is to increase perplexity and burstiness while staying within journal-appropriate tone.

---

## The Formula That Works

These rules produced 0% AI detection on QuillBot across multiple topics and sections of a real IEEE paper.

### Constraints (what NOT to use)
- No em dashes or en dashes of any kind
- No semicolons
- No contractions ("do not" not "don't")
- No sentence fragments (every sentence needs subject + verb)
- No rhetorical questions
- No colloquialisms or informal language
- No "now," "actually," "at this point"
- No AI buzzwords (delve, tapestry, landscape, harness, leverage, pivotal, crucial, groundbreaking, transformative, foster, embark, noteworthy, commendable)

### Rules (what TO do)
1. **Open with the problem or a specific data point, not a broad claim**
2. **Use colons to introduce specific data immediately after a claim**
3. **Pack multiple citations into parenthetical groups** instead of giving each its own sentence
4. **Include at least one short complete sentence per paragraph** (5-8 words, must have subject + verb)
5. **Use "for instance" or "for example" to pivot into domain-specific detail**
6. **End paragraphs with a specific methodological critique**, not "further research is needed"
7. **Avoid defining terms in the opener** ("X, a phenomenon referred to as Y" is an AI pattern)
8. **Vary sentence length dramatically** (range of 6 to 40+ words within a paragraph)
9. **Vary sentence openers** (do not start three sentences the same way)
10. **Use domain-specific technical vocabulary** (nuclear pleomorphism, chromatin distribution, etc.)

---

## What to Avoid

### Sentence patterns that get flagged every time

| Pattern | Example | AI Score |
|---|---|---|
| "X has emerged as a Y, offering Z compared to W" | "ECoG has emerged as a high-fidelity modality, offering superior resolution" | 13% |
| "X are among the most promising technologies for Y" | "BCIs are among the most promising technologies for restoring motor function" | 47% |
| "X, a phenomenon referred to as Y" | "fabricated facts, a failure mode referred to as hallucination" | 24% |
| "What remains poorly understood is Y" | "What remains poorly understood is the nature of the transfer" | 5% |
| "The residual errors are not random." | Short AI-confident declaration | High confidence flag |
| "These results are not in dispute." | Short AI-confident declaration | 32% |
| "X is consistent with Y" | "a finding consistent with results in radiology" | 27% |
| "Author (year) reported X. Author (year) reported Y." | Stacked citation sentences | 14-17% |
| "Although X is well documented, Y has received little attention" | Classic AI gap-identification | 22% |
| "X consistently outperforms Y in Z settings" | Broad declarative opener | 54% |
| "Given the well-documented X" | AI framing pattern | 27% |
| "Ablation studies highlighted A, B, and C as key contributors" | Clean three-item enumeration | 4% |
| "some X, while others Y" | Parallel classification | 34% |
| Stacked epidemiological stats as opener | "More than 5 million... Stroke affects 12 million..." | 21-47% |
| Generic field-review text | "Cross-study comparison is complicated by inconsistent protocols" | 86% |

### Words to avoid entirely
- delve, tapestry, landscape, realm
- harness, leverage, foster, embark
- pivotal, crucial, groundbreaking, transformative, revolutionary
- noteworthy, commendable, showcasing
- underscore (use "highlight" or "show")
- comprehensive (use "thorough" or "detailed" or cut it)
- "it is important to note" (just state the thing)
- "in conclusion" / "in summary" (readers know it is the end)
- moreover, furthermore, additionally (use "also" or just move to the next point)

---

## Opening Sentences

The first sentence of any section is the highest-risk sentence in the paper. It is where detectors focus most and where AI patterns are most recognizable.

### What works (0% AI)
- **Problem-first:** "Convolutional networks trained on small medical imaging datasets face a well-known optimization difficulty: with fewer than 10,000 labeled examples, deep architectures tend to overfit before learning generalizable representations."
- **Direct technical description:** "Electrocorticography (ECoG) records local field potentials from the cortical surface with spatial resolution and signal stability that non-invasive modalities such as scalp EEG cannot match."
- **Data-first with colon:** "Fine-tuning from ImageNet weights yields consistent gains in medical image classification: 12 points of balanced accuracy on 8,200 dermatology images."

### What fails (13-54% AI)
- **Broad claim:** "ImageNet pretraining reliably improves classification accuracy in medical imaging" (34%)
- **"Has emerged" pattern:** "ECoG has emerged as a high-fidelity neural recording modality" (13%)
- **"Among the most promising":** "BCIs are among the most promising technologies" (47%)
- **"Given the well-documented":** "Given the well-documented accuracy gains" (27%)
- **Epidemiological stats:** "More than 5 million people live with paralysis" (21-47%)

### The rule
Open with what is specific (a number, a technical limitation, a concrete finding), not what is general (a broad claim about a field).

---

## Citation Patterns

### What works (0% AI)
**Parenthetical grouping:**
> "...with reported accuracy gains on the order of 10 to 15 points across dermatology, chest radiography, and ophthalmology (Park and Kim, 2022; Raghu et al., 2019; Zhou et al., 2021)."

### What fails (14-17% AI)
**Stacked citation sentences:**
> "Park and Kim (2022) measured a 12-point gain... Raghu et al. (2019) and Zhou et al. (2021) reported comparable margins..."

### The rule
When citing multiple studies that support the same point, group them in a single parenthetical rather than giving each its own sentence. When you need to discuss a specific study in detail, use narrative citation ("Raghu et al. (2019) offered indirect evidence by showing that...") but do not stack two narrative citations back to back.

---

## Sentence-Level Patterns

### Sentence length distribution matters
A paragraph that scores 0% AI typically has this kind of length profile:

| Sentence | Words |
|---|---|
| 1 (opening with data) | 30-40 |
| 2 (supporting detail) | 20-25 |
| 3 (short pivot) | 5-8 |
| 4 (technical elaboration) | 25-35 |
| 5 (domain example) | 30-40 |
| 6 (closing critique) | 25-35 |

The key is the short sentence (5-8 words) that breaks the pattern. Without it, the paragraph reads as uniformly medium-length and gets flagged.

### Short sentences that pass in journal writing
- "The performance benefit is consistent across studies." (8 words)
- "Deeper layers present a different situation." (6 words)
- "The distinction matters for deployment." (5 words)

### Short sentences that fail
- "These transfer well." (3 words, too casual)
- "The residual errors are not random." (6 words, AI-confident declaration)
- "These results are not in dispute." (6 words, AI-confident declaration)

### The rule
Short sentences must complete a thought and lead into the next sentence. They should not be standalone declarations of confidence. They work best as pivot points between two longer technical sentences.

---

## Paragraph Structure

### What works
1. Open with a specific finding or problem (not a broad claim)
2. Support with data in the next 1-2 sentences
3. Short pivot sentence to change direction
4. Technical elaboration with domain-specific vocabulary
5. Close with a specific limitation or methodological critique

### What fails
1. Open with a broad claim about a field
2. Stack 2-3 sentences of supporting evidence with similar structure
3. Pivot with "However" or "Nevertheless"
4. Present a balanced counterpoint
5. Close with "further research is needed"

### Enumeration
- **Fails:** "X highlighted A, B, and C as key contributors to Y" (clean three-item list)
- **Works:** "In ablation experiments, data scaling and skip connections contributed the largest individual gains, with architectural refinements providing additional improvement." (embedded, asymmetric)

---

## Word-Level Swaps

### Too casual for journals
| Avoid | Use instead |
|---|---|
| at this point | to date, or remove |
| now | omit or use "currently" sparingly |
| actually | omit |
| a lot | substantially, considerably |
| big | substantial, considerable |
| get | obtain, acquire, achieve |
| thing | name the specific thing |
| kind of / sort of | omit or use "somewhat" |
| help | facilitate, support, mitigate |
| show (every time) | rotate: demonstrate, indicate, reveal, suggest |
| look at | examine, investigate, analyze |

### Safe formal vocabulary (not AI-flagged)
- demonstrate, indicate, reveal, suggest (rotate these)
- examine, investigate, analyze
- facilitate, mitigate
- robust (use sparingly, acceptable in ML for model evaluation)
- "for instance" (safe pivot phrase)

### Parenthetical reformatting
Your own editing style (from the TRACE paper revisions) shows an effective pattern: convert parenthetical asides into inline phrasing.

| Before (parenthetical) | After (inline) |
|---|---|
| (0% = fully extended, 100% = fully curled) | where 0% indicates fully extended and 100% indicates fully curled |
| (short-term memory) | short-term memory |
| (e.g., outlier handling via Isolation Forest) | including outlier handling via Isolation Forest |
| (median and interquartile range per feature) | which normalizes using median and interquartile range per feature |
| (pre-norm ordering) | in pre-norm ordering |

This reduces the parenthetical density that can read as AI-generated and makes sentences flow more naturally.

---

## Section-by-Section Risk Map

Based on testing every section of an IEEE ML paper:

| Section Type | Risk Level | Why |
|---|---|---|
| Abstract opener | HIGH | "Has emerged as" and broad claim patterns |
| Introduction (clinical motivation) | HIGH | Epidemiological stats are generic AI text |
| Introduction (technical gap) | LOW | Specific to your contribution |
| Related Work (dataset description) | LOW | Factual, data-heavy |
| Related Work (field review/benchmarking) | VERY HIGH (86%) | Generic survey text is exactly what AI writes |
| Methods/Preprocessing | LOW | Highly technical, specific parameters |
| Architecture description | LOW | Technical, domain-specific |
| Results | LOW | Packed with numbers |
| Discussion (your findings) | LOW | Specific to your experiments |
| Limitations | LOW | Self-critical, specific |
| Conclusion (with specific results) | LOW | Data-heavy conclusions pass |
| Conclusion (broad future directions) | MEDIUM | "Future work includes..." can be generic |

### The pattern
- **High risk:** Any text that could apply to many papers in your field (generic motivation, field reviews, broad claims)
- **Low risk:** Text that is specific to YOUR paper (your numbers, your architecture, your experimental findings)

---

## Topic Dependency

The same writing formula scores very differently depending on the topic:

| Topic | Best Score Achieved |
|---|---|
| Transfer learning / medical imaging | 0% |
| ECoG motor decoding (niche) | 0% |
| LLM hallucination (hot AI topic) | 13% (best), 65% (worst) |

**Why:** Detectors are biased toward flagging topics that AI frequently discusses. For AI-adjacent topics (hallucination, prompt engineering, alignment, transformers in general), you need even more specific data points and domain expertise to avoid detection.

**Mitigation for hot topics:**
- Lead with specific numbers, not the topic name
- Avoid defining the phenomenon in the opener
- Use the most specific technical vocabulary possible
- Reference specific model names, dataset names, benchmark scores
- Avoid the word "hallucination" as the first noun in a paragraph

---

## Formal Perplexity Boosters

Techniques to increase perplexity (less predictable text) while staying academic:

### 1. Subordinate clause openers
Instead of: "The model failed. This was due to overfitting."
Use: "Although the model initially converged, subsequent evaluation revealed overfitting on the training distribution."

### 2. Nominalization for density
Instead of: "We analyzed the data and found evidence."
Use: "Analysis of the data provided evidence for..."

### 3. Embedded relative clauses
Instead of: "The method was proposed by Lee et al. It outperforms baselines."
Use: "The method proposed by Lee et al., which outperforms existing baselines, relies on..."

### 4. Prepositional phrase openers
Instead of: "The results show improvement."
Use: "In contrast to prior work, these results indicate improvement across..."

### 5. Vary citation integration style within a paragraph
- Narrative: "Yosinski et al. (2014) demonstrated that..."
- Parenthetical: "...across multiple benchmarks (Park and Kim, 2022; Raghu et al., 2019)"
- Embedded: "...as shown by recent probing experiments (Li et al., 2024)..."

Mixing these within a single paragraph increases burstiness.

### 6. Subordinating conjunctions
"Although," "while," "despite," "given that" create complex sentences that vary rhythm without informal language.

### 7. Vocabulary rotation
Do not use the same reporting verb twice in a paragraph. Rotate among: demonstrate, indicate, reveal, suggest, report, observe, measure, identify, show.

---

## Tested Examples: Before and After

### Example 1: Abstract opener (13% -> 0%)

**Before (13% AI):**
> Electrocorticography (ECoG) has emerged as a high-fidelity neural recording modality for motor brain-computer interfaces (BCIs), offering superior spatial resolution and signal stability compared to non-invasive techniques.

**After (0% AI):**
> Electrocorticography (ECoG) records local field potentials from the cortical surface with spatial resolution and signal stability that non-invasive modalities such as scalp EEG cannot match, making it a strong candidate for motor brain-computer interfaces (BCIs).

**What changed:** Replaced "has emerged as" with direct description. Replaced "offering X compared to Y" with "with X that Y cannot match."

### Example 2: Introduction (47% -> 0%)

**Before (47% AI):**
> Brain-computer interfaces (BCIs) are among the most promising technologies for restoring motor function via direct decoding of neural signals, with potential to benefit more than 5 million people living with paralysis in the United States. Stroke affects more than 12 million people worldwide every year, and many survivors experience long-term motor impairment.

**After (0% AI):**
> Convolutional architectures remain the dominant approach for decoding continuous finger movements from electrocorticography (ECoG), but their reliance on local receptive fields limits their capacity to model long-range temporal dependencies in motor signals. ECoG electrode grids placed on the cortical surface record local field potentials at 1 cm inter-electrode spacing with high signal-to-noise ratio, and power modulations in the 40 to 300 Hz band track ongoing finger and hand movements with sufficient fidelity for trajectory-level decoding.

**What changed:** Removed generic clinical motivation entirely. Opened with the technical gap. Clinical stats moved to later in the paragraph where they serve as supporting context, not the opener.

### Example 3: Reproducibility section (86% -> 0%)

**Before (86% AI):**
> Cross-study comparison in motor BCI is complicated by inconsistent evaluation protocols. EEG studies typically report classification accuracy for discrete tasks, whereas ECoG studies use correlation coefficients for continuous movement prediction, making direct comparisons between recording modalities difficult. This metric inconsistency obscures whether observed performance differences reflect algorithmic improvements or fundamental signal quality advantages.

**After (0% AI):**
> Comparing ECoG decoding results across studies is difficult in practice because evaluation protocols vary in ways that are rarely documented. EEG-based motor imagery work reports classification accuracy on discrete trial labels, while ECoG trajectory studies report Pearson correlation on continuous outputs, and neither metric translates directly to the other. A model that achieves 0.70 correlation on one benchmark cannot be ranked against a model reporting 92% accuracy on a different task without shared evaluation criteria.

**What changed:** Replaced abstract "metric inconsistency obscures whether" with a concrete example (0.70 correlation vs 92% accuracy). Made the problem tangible instead of theoretical.

### Example 4: Transfer learning paragraph (multiple iterations)

| Version | Strategy | Score |
|---|---|---|
| Original AI-style | "has emerged," "transformative," "delve," "pivotal" | 100% AI |
| First rewrite (informal) | Golden Retrievers, "the story gets murkier" | 0% but not journal-appropriate |
| Formal with semicolons | Problem-first, semicolons, "for instance" | 0% (with semicolons) |
| Formal without semicolons | Problem-first with colon, parenthetical citations | 0% (without semicolons) |
| Formal, traditional opener | "consistently outperforms" | 54% AI |
| Formal, "has emerged" | "has emerged as" | 34% AI |
| Formal, "given the" | "Given the well-documented" | 27% AI |

---

## Quick Checklist

Run through this before submitting any section:

### Word-level
- [ ] No dashes of any kind
- [ ] No semicolons (unless you decide to allow them)
- [ ] No contractions
- [ ] No AI buzzwords (delve, tapestry, harness, leverage, pivotal, etc.)
- [ ] No "now," "actually," "at this point"
- [ ] Reporting verbs rotated (not "show" every time)

### Sentence-level
- [ ] At least one short sentence (5-8 words) per paragraph
- [ ] No two consecutive sentences with the same structure
- [ ] No "X has emerged as Y" patterns
- [ ] No "What remains X is Y" patterns
- [ ] No stacked citation sentences (Author reported X. Author reported Y.)
- [ ] No parallel "some X, while others Y" classifications
- [ ] No "The X are not Y" confident declarations

### Paragraph-level
- [ ] Opens with a specific finding or problem, not a broad claim
- [ ] Citations grouped in parenthetical where possible
- [ ] Sentence lengths vary (range of 5 to 40+ words)
- [ ] Ends with a specific critique or finding, not "further research is needed"
- [ ] No clean three-item enumeration ("X highlighted A, B, and C as key contributors")

### Section-level
- [ ] No generic clinical motivation as the opener (move stats later)
- [ ] No generic field-review paragraphs (make them specific with examples)
- [ ] Results sections packed with your actual numbers
- [ ] Each section tested individually on QuillBot

### Final
- [ ] Test each section on QuillBot AI Detector individually
- [ ] Fix any flagged sentences using the patterns in this guide
- [ ] Retest after fixes
- [ ] Commit changes

---

*Last updated: 2026-03-25. Based on 30+ trials on QuillBot AI Detector.*
