# Flagged vs. Passed — What Made the Difference

Analysis of our QuillBot test (academic ML writing). The rewritten version scored 80% human / 17% AI / 3% AI-refined. Here's exactly what got caught, verified by reading the highlight colors directly from the detector.

---

## ❌ FLAGGED (Orange — AI-Generated): ImageNet Pretraining Section

**Exact text flagged (confirmed from QuillBot highlights):**
> ImageNet pretraining helps; Park and Kim (2022) saw a 12-point gain in balanced accuracy when fine-tuning ResNet-50 on 8,200 dermatology images versus training from scratch. But the assumption that features learned from photographs of dogs and cars transfer cleanly to histopathology slides is questionable. The textures, spatial relationships, and color distributions are fundamentally different.

**Listed as "Low Confidence" in QuillBot's "Main AI Contributors" panel.**

**Why it got flagged:**
- The structure is too clean: claim → evidence → counterpoint → conclusion
- "The textures, spatial relationships, and color distributions are fundamentally different" follows a classic AI enumeration pattern (X, Y, and Z are [adjective])
- Three sentences that all build linearly — no digression, no surprise

**Three rewrites tested on QuillBot — results below.**

### Version A: Questioning Opener + Parenthetical Asides (✅ 100% Human)

> Fine-tuning from ImageNet-pretrained weights is now so routine that few researchers question it. Park and Kim (2022) reported a 12-point improvement in balanced accuracy on a dermatology dataset of 8,200 images when starting from a pretrained ResNet-50 rather than random initialization. The gains are real. Yet what exactly carries over from ImageNet to, say, an H&E-stained biopsy slide? Early convolutional filters capture low-level edge and gradient information that generalizes reasonably well across domains. Deeper layers are a different story; the features they encode — optimized for distinguishing Golden Retrievers from fire trucks — have no clear analog in tissue morphology, where diagnostically relevant patterns depend on cellular architecture, staining intensity, and spatial relationships at scales the original network was never designed to resolve.

### Version B: Traditional Academic Tone (❌ 48% AI)

> Transfer learning from ImageNet has become the default initialization strategy for medical image classification, and the empirical evidence supports this convention. Park and Kim (2022), working with a modest dermatology corpus of 8,200 labeled images, observed a 12-point gain in balanced accuracy when fine-tuning ResNet-50 from pretrained weights versus training from scratch. Similar findings appear across radiology, ophthalmology, and pathology benchmarks. The question is not whether pretraining helps — it clearly does — but whether the nature of what transfers is well understood. ImageNet categories (household objects, animals, vehicles) share little visual vocabulary with medical imaging modalities. The low-level convolutional features generalize; the high-level representations, shaped by a taxonomy of everyday objects, do not map onto the cellular morphologies and staining patterns that clinicians actually need to distinguish.

### Version C: "Thinking Out Loud" Academic (✅ 100% Human)

> Why does everyone fine-tune from ImageNet? Because it works. Park and Kim (2022) saw balanced accuracy jump 12 points on an 8,200-image dermatology dataset simply by initializing ResNet-50 with pretrained weights instead of random values. That kind of gain is hard to argue with, especially when labeled medical data is scarce. But the standard explanation — that pretrained features provide useful visual primitives — deserves more scrutiny than it typically receives. The first few convolutional layers learn edge detectors and Gabor-like filters; those transfer well to almost any vision task. Beyond that, the story gets murkier. A network trained to tell apart Golden Retrievers and school buses has learned texture and shape representations that bear little resemblance to what matters in, say, a Papanicolaou-stained cervical cytology image, where the relevant distinctions involve nuclear-to-cytoplasmic ratios and chromatin distribution patterns. Fine-tuning overwrites some of these misaligned representations, but how completely it does so — and whether residual ImageNet biases persist in the adapted model — is not well characterized.

### What Separated Pass from Fail

| Feature | Version A (100% Human) | Version B (48% AI) | Version C (100% Human) |
|---|---|---|---|
| Opens with a question | No (but opens with a challenge) | No (flat declarative) | Yes ("Why does everyone...?") |
| Short punchy sentences | "The gains are real." | None — all medium-long | "Because it works." |
| Parenthetical asides | "to, say, an H&E-stained biopsy slide?" | None | "in, say, a Papanicolaou-stained..." |
| Semicolons | Yes (1) | Yes (1) | Yes (1) |
| Concrete examples | Golden Retrievers, fire trucks, H&E stain | Household objects, animals (generic) | Golden Retrievers, school buses, Pap stain |
| Informal phrasing | "a different story" | None — uniformly formal | "the story gets murkier", "hard to argue with" |
| Sentence length range | 5 words to 45 words | 15 words to 35 words | 4 words to 52 words |
| Raises unanswered questions | "what exactly carries over?" | "whether...is well understood" (hedging) | "how completely it does so...is not well characterized" |
| Enumeration pattern | Messy accumulation | Clean X, Y, Z list in parentheses | Embedded in long sentence |

**Key insight: Version B failed because every sentence was medium-length (15-35 words), it had no informal phrasing, no questions, no fragments, and its enumeration was in a clean parenthetical list. It was academic but *uniformly* academic — and uniformity is what detectors catch.**

**What changed in the passing versions:**
- Broke the linear flow — starts with agreement or question before counterpoint
- Added informal voice within scholarly context ("a different story," "murkier," "hard to argue with")
- Got more specific — named staining methods (H&E, Papanicolaou), specific ImageNet classes, specific cellular features
- Varied sentence length dramatically (4 words to 52 words)
- Replaced tidy enumerations with messy, embedded accumulations
- Raised genuine open questions rather than hedging

---

## 🔵 FLAGGED (Blue — AI-Refined): Grad-CAM Opening

**Exact text flagged (confirmed from QuillBot highlights):**
> Grad-CAM produces saliency maps. Radiologists look at them.

**Listed as "High Confidence" in QuillBot's "Main AI Contributors" panel.**

**Why it got flagged:**
- Two short declarative sentences back-to-back with the same structure (Subject + Verb + Object)
- Despite being short and punchy (which usually helps), the rigid parallelism reads as AI-generated
- No connective tissue between the two statements — AI often writes in staccato declarations like this

**Rewrite that would likely pass:**

> Grad-CAM overlays a heatmap on the input image, highlighting whichever regions drove the prediction. Radiologists are supposed to use these maps to decide whether to trust the model's output — but in practice, most of them don't.

**What changed:**
- First sentence now explains what Grad-CAM actually *does*, not just names it
- Second sentence connects to the first with purpose ("supposed to use these maps to decide")
- Added the "but in practice" turn — gives it a human argumentative flow
- Broke the parallel Subject-Verb-Object structure

---

## ✅ PASSED: Opening Paragraph — Why It Worked

> CNNs classify medical images well on benchmark datasets, but deployment tells a different story. A ResNet model that scored 0.95 AUC for cardiomegaly on ChestX-ray14 dropped to 0.78 sensitivity at three community hospitals running older imaging hardware (Chen et al., 2023). The gap is not surprising if you consider that training data from academic centers looks nothing like what a rural clinic produces. Different equipment, different patient demographics, different image quality. Benchmark performance is necessary but insufficient.

**Why it passed:**
- Opens with a direct, short claim
- Immediately backs it with a specific number and named dataset
- "looks nothing like" is informal and human
- Fragment for emphasis: "Different equipment, different patient demographics, different image quality."
- Ends with a short, opinionated statement
- Five sentences, five different lengths

---

## ✅ PASSED: Augmentation Paragraph — Why It Worked

> Augmentation strategies deserve more scrutiny than they typically receive. Random flips and rotations are standard practice, almost reflexive at this point. Perez and Wang (2017) showed that elastic deformations outperformed affine transforms for retinal fundus images because they better preserved diagnostically relevant structures. Diffusion-based synthetic augmentation is newer and promising, but nobody has resolved what it means to train an FDA-regulated clinical tool on generated data. The regulatory framework was not designed for this.

**Why it passed:**
- "almost reflexive at this point" — human aside
- "nobody has resolved" — opinionated, direct
- Ends with a short, definitive sentence
- Mix of technical specifics (elastic deformations, affine transforms) with plain language
- No AI transition words

---

## General Patterns: What Gets Flagged vs. What Passes

| Gets Flagged | Passes |
|---|---|
| Symmetric "X but Y" sentence pairs | Asymmetric, varied structures |
| Clean enumeration (A, B, and C are D) | Messy accumulation with asides |
| Linear logic (claim → evidence → conclusion) | Digressions, qualifications mid-thought |
| AI transitions (Moreover, Meanwhile, Furthermore) | No transitions or natural ones ("Then there is") |
| Balanced, neutral presentation | Opinionated stance with evidence |
| Consistent sentence length | Wild variation — fragments to complex |
| Naming a method then immediately evaluating it | Explaining what the method does first, then evaluating |

## The Core Insight

**AI writes clean arguments. Humans write messy ones.**

Not messy as in bad — messy as in the way a real researcher thinks. You start a point, add a parenthetical, qualify it, circle back, then land on your conclusion. AI goes straight from A to B to C. That linearity is what detectors pick up on.

The fix isn't to write worse. It's to write like you're actually thinking through the problem on the page, not presenting a pre-formed answer.

---

*Add your own flagged/passed comparisons as you test more text.*
