# Technical limitations, privacy, and review gates

Sources: PDF pp.1–2, 32–41, 43–44, 52–53, 55–74; static inspection only.

## Availability

The report is the only supplied source-code artifact; original project photographs and CareGuard screenshots were supplied later. The report contains a relatively substantial controller listing but only fragments of vision and training code. CareGuard, the safety module, model weights, data, dependency versions, and full database definitions are missing. The appendix listing is not a complete runnable system.

## Static controller findings

- Geofence and stationary threads independently open the same GPS serial port; contention or split readings are possible.
- Stationary detection requires exact coordinate equality, so GPS jitter can reset its timer. It does not prove helmet removal.
- `fetchone()` selects one matching reminder; handling multiple medicines in one minute, completion state, missed events, and timezone behavior is not defined.
- Object Mode lasts 60 seconds without receiving a detection-completion signal. It does not establish medication intake.
- Process handles are not polled for child failure. Termination exceptions are ignored, with no force-stop fallback after timeout.
- HTTP failures are swallowed, status codes are not checked, and no retry/queue is shown. Whether local writes plus server handling duplicate records depends on unavailable backend code.
- Paths and interpreter environments are hardcoded; the safety script uses generic `python3` rather than the two explicit vision interpreters.
- Thread-shared reminder state has no explicit synchronization.

These are review observations, not reproduced runtime failures. The historical extraction intentionally does not repair them.

## Conflicting descriptions

The flowchart's five-minute no-detection fallback differs from the appendix's fixed 60 seconds. The conclusion's simultaneous pipelines differ from process switching. The reminder column is `name` in one excerpt and `medicine` in the appendix. The prose's GPS-shutdown configuration spelling differs from its screenshot. Dataset-source prose says GitHub while code uses Kaggle tooling.

The displayed LCD overlays do not prove an optical see-through AR assembly. Training preparation does not prove new dlib network training. Proposed Flutter, voice-assistant features, improved face models, and battery management are not implemented features established here.

## Privacy decisions

The original PDF is unchanged, remains outside public documentation folders, and is ignored by `.gitignore`. It contains student IDs, signatures, identifiable faces, phone numbers, and location coordinates. Its metadata also retains an old template title. Do not stage or publish it unchanged.

The report's face and CareGuard screenshots remain unextracted. Separately supplied CareGuard screenshots are included with the owner's confirmation that their location and coordinates are arbitrary demonstration data. The front-view project photograph is cropped to remove poster names; other approved photographs remain unchanged. Actual databases, embeddings, datasets, weights, credentials, and logs are excluded. The extracted controller uses `0.0` placeholders for both original site coordinates; this deliberate publication change is documented in its header and source inventory.

No explicit passwords or API tokens were found in the inspected report. That does not replace reviewing recovered source. Client requests use local HTTP without visible authentication headers; server authentication, authorization, TLS, retention, and access policies are unknown. The excerpts load `pickle` assets, which should only come from trusted sources.

No license is assigned. Confirm team code ownership and external asset/dataset permissions before redistribution. Listing standards in the report is not evidence of certification or compliance. The project is not presented as a clinically validated device.

## Review before publication

**Publication blocker:** permission to redistribute team-authored source, including code-excerpt images, has not been established. Confirm that permission before publishing the current collection. The owner's authorization to include the supplied project photographs and demonstration screenshots does not establish rights to every team-authored or third-party asset; confirm any remaining ownership restrictions for report-derived materials as well. Do not add a license without resolving ownership and licensing scope.

Identifiable face demonstrations remain withheld. Missing application files limit reproducibility but do not prevent an accurately labeled documentation portfolio. Review every staged file: `.gitignore` alone is not a privacy guarantee, and it does not protect files uploaded manually through a web interface.
