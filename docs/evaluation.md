# Prototype evaluation

Sources: PDF pp.55–64. These results are reported by the graduation project, not reproduced during repository preparation. No extracted project code was executed.

## Test scope

The report describes 18 face-recognition cases and 20 medication-detection cases. Face cases include registered/unregistered identities and photos displayed on a secondary screen. Medication cases include target/non-target packages under varying conditions. These 38 cases are not 38 patients or a clinical trial.

| Count or metric | Face recognition | Medication detection |
| --- | ---: | ---: |
| True positives | 10 | 12 |
| False positives | 6 | 4 |
| True negatives | 2 | 3 |
| False negatives | 0 | 1 |
| Total | 18 | 20 |
| Precision | 62.5% | 75.0% |
| Recall | 100.0% | 92.3% |
| Specificity | 25.0% | 42.9% |
| Accuracy | 66.7% | 75.0% |
| F1 as printed | 76.9% | 82.7% |

Using `2TP / (2TP + FP + FN)`, medication F1 is `24/29`, approximately 82.76%, rounding to 82.8% at one decimal place. The printed value is retained and distinguished from this arithmetic check.

## Interpretation

High recall coexists with substantial false-positive rates. In the face cases, six unregistered inputs were assigned known identities. Medication errors include confusing a negative-control package with a known class. These results demonstrate prototype behavior and limitations, not safe autonomous decisions.

The report lists Relaxion as a negative control while discussing seven supported medicines; the dashboard additionally shows Betadine. Without the final `data.yaml` and model label mapping, the final supported class set is unresolved.

![Original medication example](../assets/images/medication-detection.jpg)

## Timing and validation limits

The discussion claims 54–72 FPS on Raspberry Pi. Medication screenshots show counters in that range, while face screenshots include approximately 20.5 FPS and 8 FPS. No timing implementation, sample duration, input/inference resolution record, or distinction between rendering and inference rate is provided. Do not cite this as a verified end-to-end benchmark.

Training screenshots provide partial progress evidence, not a complete final validation artifact. No per-case test ledger, confidence intervals, raw predictions, exported confusion matrix, or reproducible training run is supplied. Full-image bounding-box labels visible in preparation code warrant further review.

There are no quantified GPS accuracy, alert-delivery latency, battery-runtime, thermal, ergonomics, or clinical-benefit results. Any future tests should be clearly separated from the original report's evaluation.
