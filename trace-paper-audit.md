# TRACE Paper AI Detection Audit

Testing each section of the TRACE paper on QuillBot AI Detector.

## Results Summary

| Section | AI % | Flagged Text |
|---|---|---|
| Abstract | 13% | Opener: "ECoG has emerged as a high-fidelity neural recording modality...offering superior...compared to" |
| Intro P1-P2 | 47% | Entire P1 flagged: "BCIs are among the most promising technologies...Stroke affects more than..." ECoG paragraph passed. |
| Intro P3-P4 (technical gap) | 0% | Rewritten: opened with technical gap instead of clinical stats |
| Related Work (Dataset 4 history) | 0% | Clean as-is. Domain-specific, data-heavy. |
| Results | 0% | Clean as-is. Packed with numbers. |
| Discussion | 0% | Clean as-is. Specific to TRACE findings. |
| Conclusion | 0% | Clean as-is. |

## Flagged Patterns Found So Far

1. **"X has emerged as a Y, offering Z compared to W"** -- AI definition/introduction pattern
2. **"X are among the most promising technologies for Y"** -- AI hype opener
3. **"Stroke affects more than X million people"** -- generic epidemiological stat framing
4. **"Upper limb weakness is seen in more than..."** -- passive + generic stat

## What Passed

- ECoG technical description with specific measurements (1 cm spacing, 40-300 Hz, SNR)
- Specific model results (0.645 mean Pearson, per-subject breakdowns)
- Technical architecture descriptions

## Rewrites That Passed (0% AI)

### Abstract (13% -> 0%)

**Original opener (flagged):**
> "Electrocorticography (ECoG) has emerged as a high-fidelity neural recording modality for motor brain-computer interfaces (BCIs), offering superior spatial resolution and signal stability compared to non-invasive techniques."

**Problem:** "has emerged as" + "offering X compared to Y" is AI pattern

**Rewrite (0% AI):**
> "Electrocorticography (ECoG) records local field potentials from the cortical surface with spatial resolution and signal stability that non-invasive modalities such as scalp EEG cannot match, making it a strong candidate for motor brain-computer interfaces (BCIs). Convolutional architectures have driven recent advances in ECoG motor decoding, but their reliance on local receptive fields limits their ability to capture long-range temporal dependencies in continuous motor signals. We propose TRACE (Transformer for Real-time Accurate Cortical ECoG Motor Decoding), a transformer-based architecture that applies multi-head self-attention across ECoG electrode channels and time to model distributed spatiotemporal patterns of cortical motor activity. On the BCI Competition IV Dataset 4, TRACE achieves a mean Pearson correlation of 0.645 across subjects with channel dropout regularization, outperforming a U-Net FingerFlex baseline (0.597). Evaluation on a nine-patient subset of the Miller ECoG Library, spanning finger flexion, joystick tracking, and mouse tracking tasks, demonstrates that the attention-based approach generalizes across subjects and motor paradigms."

**Key changes:**
- Replaced "has emerged as" with direct description of what ECoG does
- Removed "offering X compared to Y" pattern
- Cut the generic ML motivation sentence ("Machine learning applications continue to gain...")
- Moved straight from modality description to the technical gap (CNNs vs long-range deps)

### Intro P1-P2 (47% -> 0%)

**Original (47% AI flagged):**
> "Brain-computer interfaces (BCIs) are among the most promising technologies for restoring motor function via direct decoding of neural signals, with potential to benefit more than 5 million people living with paralysis in the United States. Stroke affects more than 12 million people worldwide every year..."

**Problem:** Generic clinical motivation with stacked epidemiological stats. This is exactly what AI writes for any biomedical paper intro.

**Rewrite (0% AI):**
> "Convolutional architectures remain the dominant approach for decoding continuous finger movements from electrocorticography (ECoG), but their reliance on local receptive fields limits their capacity to model long-range temporal dependencies in motor signals. ECoG electrode grids placed on the cortical surface record local field potentials at 1 cm inter-electrode spacing with high signal-to-noise ratio, and power modulations in the 40 to 300 Hz band track ongoing finger and hand movements with sufficient fidelity for trajectory-level decoding. The U-Net-inspired FingerFlex architecture, for example, achieved a mean Pearson correlation of 0.62 across three subjects on the BCI Competition IV Dataset 4, the standard public benchmark for this task. Whether attention-based architectures can improve on these results by capturing temporal structure beyond the convolutional receptive field has not been systematically evaluated on ECoG data, despite the success of transformers in scalp EEG motor imagery classification. This gap motivates TRACE, a transformer encoder that applies multi-head self-attention across electrode channels and time to model distributed spatiotemporal patterns of cortical motor activity."

**Key changes:**
- Removed all epidemiological stats (5 million paralysis, 12 million stroke)
- Opened with the technical gap directly
- Led with specific benchmark numbers (0.62 correlation, Dataset 4)
- Ended with a clear gap statement + what TRACE does about it
- NOTE: The clinical motivation (paralysis/stroke stats) can be moved to later in the intro or discussion if needed for the submission, but it should not be the opener

## Sections That Passed Without Changes (0% AI as-is)

- Related Work (Dataset 4 benchmark history)
- Results (per-subject correlations, per-finger breakdowns)
- Discussion (TRACE capacity analysis, Miller variability)
- Conclusion

**Pattern:** Sections packed with specific numbers, domain-specific terminology, and your own experimental findings pass cleanly. Sections with generic motivation text get flagged.
