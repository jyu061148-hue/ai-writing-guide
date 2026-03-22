# Sentence-by-Sentence Audit of the 0% AI Paragraph

Evaluating every sentence for journal-appropriate tone. Flagging anything that would not appear in a published ML paper.

## The 0% Version (no semicolons, no dashes)

**S1:** "Convolutional networks trained on small medical imaging datasets face a well-known optimization difficulty: with fewer than 10,000 labeled examples, deep architectures tend to overfit before learning generalizable representations."
- **Tone check:** Appropriate for journal. Technical, specific, no fluff.
- **Verdict:** PASS

**S2:** "ImageNet pretraining offers a partial remedy, with reported accuracy gains on the order of 10 to 15 points across dermatology, chest radiography, and ophthalmology (Park and Kim, 2022; Raghu et al., 2019; Zhou et al., 2021)."
- **Tone check:** Appropriate. "Partial remedy" is slightly informal but acceptable in ML papers. "On the order of" is standard scientific phrasing.
- **Possible improvement:** "provides a partial solution" instead of "offers a partial remedy" for slightly more formal register.
- **Verdict:** PASS (minor tweak possible)

**S3:** "The performance benefit is consistent across studies."
- **Tone check:** Short but grammatically complete. Appropriate for journal writing.
- **Verdict:** PASS

**S4:** "What is less clear is the mechanism."
- **Tone check:** Appropriate. This construction appears in published papers. Not the same as "What remains poorly understood" (which got flagged separately).
- **Verdict:** PASS

**S5:** "Yosinski et al. (2014) demonstrated that early convolutional layers acquire domain-general features, including edge detectors and oriented gradients, that transfer reliably across visual tasks."
- **Tone check:** Appropriate. Standard citation + finding format.
- **Verdict:** PASS

**S6:** "Deeper layers present a different situation."
- **Tone check:** Appropriate. Short, clear, creates rhythm break.
- **Verdict:** PASS

**S7:** "Their learned representations encode distinctions among the thousand object categories in ImageNet, and these distinctions have no clear counterpart in clinical imaging, where diagnostic accuracy depends on nuclear pleomorphism, chromatin distribution, and glandular architecture at the cellular scale."
- **Tone check:** Appropriate. Technical, specific, domain-expert vocabulary.
- **Verdict:** PASS

**S8:** "Whether fine-tuning overwrites these mismatched representations or merely adjusts them cannot be determined from aggregate accuracy on held-out test sets alone."
- **Tone check:** Appropriate. Methodological critique.
- **Verdict:** PASS

**S9:** "Raghu et al. (2019) offered indirect evidence by showing that smaller architectures trained from scratch can, in certain medical tasks, match the accuracy of fine-tuned ImageNet models, raising the possibility that the deeper pretrained features contribute less to downstream performance than the field has generally assumed."
- **Tone check:** Appropriate. "The field has generally assumed" is standard academic framing.
- **Verdict:** PASS

## Previously Flagged Sentences That Were Too Casual

| Sentence | Problem | Fix |
|---|---|---|
| "These transfer well." | Too short, too casual for journal | "These features transfer reliably." or embed in longer sentence |
| "These gains are reproducible and, at this point, expected." | "At this point" is conversational | "These gains are reproducible and well documented." |
| "What remains poorly understood is the nature of the transfer itself." | "What remains X is Y" is AI pattern | "What is less clear is the mechanism." or reframe entirely |
| "The story gets murkier." | Colloquial | Remove entirely |
| "Hard to argue with." | Colloquial | Remove entirely |
| "Golden Retrievers and school buses" | Too informal for journal | Use "ImageNet object categories" or "everyday object classes" |
| "A different story." | Fragment, too casual | "Deeper layers present a different situation." |

## New Techniques From Research (Formal Perplexity Boosters)

These increase perplexity (less predictable text) while staying academic:

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

### 5. Precise vocabulary swaps (that increase perplexity)
- "show" -> "demonstrate," "indicate," "reveal," "suggest" (vary each use)
- "use" -> "employ," "adopt," "apply" (context-dependent)
- "important" -> "critical" (but avoid "pivotal," "crucial" which are AI-flagged)
- "problem" -> "difficulty," "limitation," "shortcoming"
- "help" -> "facilitate," "support," "mitigate"

### 6. Vary citation integration style within the same paragraph
- Narrative: "Yosinski et al. (2014) demonstrated that..."
- Parenthetical: "...across multiple benchmarks (Park and Kim, 2022; Raghu et al., 2019)"
- Embedded: "...as shown by recent probing experiments (Li et al., 2024)..."
- Mixing these within a single paragraph increases burstiness.

### 7. Use "although," "while," "despite" clause starters
These create complex sentences that vary the rhythm without informal language.

## Words and Phrases to Avoid in Journal Writing

### Too casual for journals:
- "at this point" -> "to date" or remove
- "now" -> omit or use "currently" sparingly
- "actually" -> omit
- "a lot" -> "substantially" or "considerably"
- "big" -> "substantial," "considerable"
- "get" -> "obtain," "acquire," "achieve"
- "thing" -> name the specific thing
- "kind of" / "sort of" -> omit or use "somewhat"

### AI-flagged words to also avoid:
- "delve" / "tapestry" / "landscape" / "harness" / "leverage" / "underscore"
- "pivotal" / "crucial" / "groundbreaking" / "transformative"
- "foster" / "embark" / "commendable" / "noteworthy"

### Safe formal alternatives:
- "demonstrate" (not "show" every time)
- "indicate" / "suggest" (for weaker claims)
- "reveal" (for discoveries)
- "examine" / "investigate" (not "look at")
- "facilitate" (not "help")
- "mitigate" (not "reduce" every time)
- "robust" (use sparingly, but acceptable in ML papers for model evaluation)
