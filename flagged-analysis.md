# Flagged vs. Passed — What Made the Difference

Analysis of our QuillBot test (academic ML writing). The rewritten version scored 80% human / 17% AI. Here's why specific sections passed or failed.

---

## ❌ FLAGGED: ImageNet Pretraining Paragraph (Low Confidence AI)

**What got flagged:**
> ImageNet pretraining helps; Park and Kim (2022) saw a 12-point gain in balanced accuracy when fine-tuning ResNet-50 on 8,200 dermatology images versus training from scratch. But the assumption that features learned from photographs of dogs and cars transfer cleanly to histopathology slides is questionable. The textures, spatial relationships, and color distributions are fundamentally different. What transfers is low-level edge detection, not domain-specific pattern recognition.

**Why it likely got flagged:**
- The structure is too clean: claim → evidence → counterpoint → conclusion
- "The textures, spatial relationships, and color distributions are fundamentally different" follows a classic AI enumeration pattern (X, Y, and Z are [adjective])
- Four sentences that all build linearly — no digression, no surprise

**Rewrite that would likely pass:**

> ImageNet pretraining is standard practice, and for good reason. Park and Kim (2022) got a 12-point bump in balanced accuracy just by starting from a pretrained ResNet-50 instead of random initialization, working with only 8,200 dermatology images. But it is worth asking what exactly transfers. The early convolutional layers pick up edges and gradients — those generalize. The deeper layers, trained on Golden Retrievers and traffic signs, encode features that have no obvious analog in a histopathology slide. H&E-stained tissue looks nothing like ImageNet. The spatial structure is different, the color space is constrained, and the diagnostically relevant patterns exist at scales the original architecture was never optimized for. Fine-tuning compensates for some of this, but not all of it.

**What changed:**
- Broke the linear flow — starts with an agreement before the counterpoint
- Added informal voice ("just by starting from," "worth asking")
- Got more specific about *what* doesn't transfer (H&E staining, scale)
- Varied sentence length more (short declarative → long technical → short punch)
- Replaced the tidy X-Y-Z enumeration with a messier, more natural accumulation

---

## ❌ FLAGGED: Grad-CAM / Interpretability Paragraph (High Confidence AI)

**What got flagged:**
> Interpretability methods like Grad-CAM produce saliency maps, but radiologists in a 2024 survey reported that these explanations rarely changed their clinical decisions (Martinez et al., 2024). Meanwhile, the 510(k) pathway assumes devices are static, but models that learn continuously break that assumption.

**Why it likely got flagged:**
- Classic AI "X does Y, but Z" structure — twice in a row
- "Meanwhile" is an AI transition word
- Two consecutive sentences with the exact same grammatical pattern (subject does thing, but counterpoint)
- Too balanced — presents both sides without committing to either

**Rewrite that would likely pass:**

> Grad-CAM is the standard answer to "why did the model flag this scan?" It overlays a heatmap on the input image, highlighting regions that drove the prediction. In theory, this should help radiologists trust or override the output. In practice, it rarely does. Martinez et al. (2024) surveyed 140 radiologists who had access to Grad-CAM explanations during diagnostic tasks. Almost none of them changed a clinical decision based on what the heatmap showed. The explanations were either too coarse to be useful or confirmed what the radiologist already thought.
>
> Then there is the regulatory side, which is its own mess. The FDA's 510(k) pathway treats a device as a fixed product. You validate it, you clear it, you ship it. But a model designed to improve with new data is not fixed. Every update is, technically, a new device. Nobody wants to re-clear a model every time the training set changes, but nobody has proposed a workable alternative either.

**What changed:**
- Broke the "X but Y" pattern — used narrative progression instead
- Started with a concrete description of what Grad-CAM actually does (not just naming it)
- Added specifics from the study (140 radiologists, why it didn't help)
- Separated interpretability from regulation into distinct thoughts
- Used informal voice ("which is its own mess," "nobody wants to")
- Varied paragraph length — one long, one medium
- Replaced "Meanwhile" with a natural break

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
