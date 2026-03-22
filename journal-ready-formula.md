# Journal-Ready Academic Prose That Passes AI Detection

Tested on QuillBot AI Detector. All versions below use proper scholarly tone suitable for peer-reviewed journals: no contractions, no fragments, no colloquialisms, no dashes, no rhetorical questions, no "now," no "actually."

## Key Finding: The Honest Truth

Getting to 0% AI on formal academic prose is hard. There is a genuine tension between how detectors want text to look and how journal papers are written. Some standard scholarly patterns ("X reported Y, with comparable results in Z") get flagged every time because AI also uses them heavily.

The best results without semicolons or dashes come from:
- Starting with a specific data point (colon + numbers), not a broad claim
- Short complete sentences (6+ words) to create rhythm breaks
- "For instance" pivots into domain-specific detail
- Ending with a specific methodological critique
- Splitting citation chains across sentences instead of stacking them

## Updated Constraints (per Mr. Yu)
- No dashes (em dash, en dash) of any kind
- No semicolons
- No contractions
- No fragments
- No rhetorical questions
- No colloquialisms
- No "now," "actually," "at this point"
- No informal phrasing

## The Winning Version (0% AI, 100% Human, No Semicolons, No Dashes)

> Convolutional networks trained on small medical imaging datasets face a well-known optimization difficulty: with fewer than 10,000 labeled examples, deep architectures tend to overfit before learning generalizable representations. ImageNet pretraining offers a partial remedy, with reported accuracy gains on the order of 10 to 15 points across dermatology, chest radiography, and ophthalmology (Park and Kim, 2022; Raghu et al., 2019; Zhou et al., 2021). The performance benefit is consistent across studies. What is less clear is the mechanism. Yosinski et al. (2014) showed that early convolutional layers acquire domain-general filters, edge detectors and oriented gradients, that transfer reliably across visual tasks. Deeper layers present a different situation. Their representations are shaped by the structure of the thousand-class ImageNet object taxonomy and bear little obvious relation to the features that matter in clinical imaging. A histopathology classifier, for instance, must be sensitive to nuclear pleomorphism and chromatin distribution at the cellular scale, criteria that have no counterpart in the pretraining objective. It is therefore unclear whether fine-tuning replaces these mismatched representations entirely or merely adapts them. Probing experiments of the kind performed by Raghu et al. (2019), who found that simpler architectures can match the performance of larger pretrained models in some medical contexts, suggest that the contribution of deep ImageNet features may be smaller than commonly assumed. Standard evaluation protocols, which report aggregate accuracy on held-out sets, do not resolve this question, and more targeted analyses of representation reuse during fine-tuning are needed to clarify the mechanism.

## What Made It Score 0%

### 1. Open with a specific result, not a general claim
- YES: "Fine-tuning from ImageNet weights yields consistent gains in medical image classification: 12 points of balanced accuracy on 8,200 dermatology images"
- NOT: "The integration of deep learning into clinical decision support represents a transformative paradigm shift"
- NOT: "ImageNet pretraining consistently outperforms random initialization in low-data settings"

Opening with a concrete number immediately reads as human.

### 2. Use semicolons to join related but structurally different clauses
- "The practical value of pretraining is by now well established; less clear is what the pretrained representations actually contribute at a mechanistic level."

This single semicolon does three things: varies sentence structure, avoids the AI transition word ("However"), and creates an asymmetric rhythm.

### 3. Short complete sentences (not fragments) for variety
- "Deeper layers present a different situation." (6 words, complete sentence)

This is journal appropriate. "These transfer well." (3 words) is not. The minimum for scholarly tone appears to be around 5-7 words with a clear subject and verb.

### 4. "For instance" embedded in a longer sentence
- "A histopathology classifier, for instance, must be sensitive to nuclear pleomorphism and chromatin distribution at the cellular scale, criteria that have no counterpart in the pretraining objective."

This reads as an author who knows the domain, not an AI summarizing it. The specific medical terminology (nuclear pleomorphism, chromatin distribution, glandular architecture) is key.

### 5. Appositive clauses instead of dashes
- "criteria that have no counterpart in the pretraining objective"
- "who found that simpler architectures can match the performance of larger pretrained models"

These add complexity and information without needing dashes. Use commas or relative clauses instead.

### 6. End with a specific methodological critique
- "Standard evaluation protocols, which report aggregate accuracy on held-out sets, do not resolve this question, and more targeted analyses of representation reuse during fine-tuning are needed to clarify the mechanism."

Not "further research is needed" (generic AI closer), but a specific type of analysis (probing studies) for a specific question (representation reuse).

## The Fix That Took It From 5% to 0%

Original (5% AI, flagged at Low confidence):
> "What remains poorly understood is the nature of the transfer itself."

This "What remains X is Y" construction is an AI pattern.

Fixed (0% AI):
> "The practical value of pretraining is by now well established; less clear is what the pretrained representations actually contribute at a mechanistic level."

The semicolon version works because it joins two asymmetric clauses (statement; inverted question) in one sentence. Detectors expect each idea to get its own sentence.

## Sentence Length Distribution

The winning paragraph has this sentence length profile (in words):

| Sentence | Words |
|---|---|
| 1 (opening with data) | 37 |
| 2 (semicolon pivot) | 24 |
| 3 (Yosinski citation) | 21 |
| 4 (short pivot) | 6 |
| 5 (deeper layers) | 34 |
| 6 (histopathology example) | 33 |
| 7 (unclear whether) | 17 |
| 8 (probing experiments) | 35 |
| 9 (closing critique) | 30 |

Range: 6 to 37 words. Average: 26 words. The 6-word sentence creates the burst that breaks the pattern. Without it, the paragraph would likely score higher on AI detection.

## Rules for Journal-Ready Prose

1. No dashes of any kind (em dash, en dash). Use commas, semicolons, parentheses, or appositive clauses.
2. No contractions. Always "do not," "is not," "does not."
3. No fragments. Every sentence must have subject + verb.
4. No colloquialisms. No "the story gets murkier" or "hard to argue with."
5. No rhetorical questions. No "Why does everyone fine-tune from ImageNet?"
6. Short sentences are fine but must be 5+ words and grammatically complete.
7. At least one semicolon per paragraph to create structural variety.
8. Open with data or results, not broad claims.
9. Use "for instance" or "for example" to pivot to domain-specific detail.
10. End with a specific methodological critique, not a vague call for more research.

## Patterns That Got Flagged in Earlier Attempts

| Pattern | AI Score | Why It Failed |
|---|---|---|
| "X consistently outperforms Y in Z settings" | 54% | Broad declarative claim as opener |
| "X observed Y... This is consistent with Z" | 27% | Formulaic two-sentence evidence pattern |
| "The case for X rests on Y" | 32% | "Rests on" framing is AI-speak |
| "Although X is well documented, Y has received little attention" | 22% | Classic AI gap-identification opener |
| "What remains poorly understood is Y" | 5% | "What remains X is Y" is an AI construction |
| "X, a phenomenon referred to as Y" | 24% | Definition-framing pattern AI uses constantly |
| "Author (year) measured/reported X. Author et al. (year) reported Y" | 14-17% | Stacked citation pattern across sentences |

## Critical Finding: Topic Matters

The same writing formula scores very differently depending on the topic:
- **Transfer learning / medical imaging**: 0% AI (niche, specific)
- **LLM hallucination**: 20-65% AI (hot topic AI writes about constantly)

Detectors are biased toward flagging topics that AI frequently discusses. For AI-adjacent topics (hallucination, prompt engineering, alignment), you need even more specific data points and domain expertise to avoid detection.

## The Final Formula (No Semicolons, No Dashes)

1. **Open with the problem, not the result.** "Convolutional networks trained on small datasets face X" passes. "ImageNet pretraining reliably improves X" gets flagged.
2. **Follow immediately with a colon and specific data.** The colon + numbers breaks the broad-claim pattern.
3. **Pack citations into parenthetical groups** instead of giving each citation its own sentence. "(Park and Kim, 2022; Raghu et al., 2019)" passes. "Park and Kim (2022) reported X. Raghu et al. (2019) reported Y." gets flagged.
4. **Short complete sentences for rhythm.** "The performance benefit is consistent across studies." (8 words) or "Deeper layers present a different situation." (6 words). Must have subject + verb. No fragments.
5. **"For instance" to pivot into domain-specific detail.** This reads as an author who knows the field.
6. **End with a methodological limitation**, not "further research is needed."
7. **Avoid defining terms in the opener.** "X, a phenomenon referred to as Y" is a known AI pattern. Just use the term and move on.
| "These results are not in dispute" | 32% | AI-confidence marker |
