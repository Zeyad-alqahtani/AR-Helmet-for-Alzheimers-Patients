# Source inventory and reproducibility

The only supplied source-code artifact was the 74-page graduation report; additional original project photographs and application screenshots are catalogued separately in the asset inventory. No source attachments were embedded in the report. All page numbers below count the cover as page 1.

## Extracted controller

| Local file | Source | Purpose | Completeness |
| --- | --- | --- | --- |
| [`main_controller_report.py`](../source/controller/main_controller_report.py) | PDF pp.69-74 / printed pp.68-73; original filename not stated | Process switching, reminders, GPS, geofence, alerts, stationary trigger | Substantial appendix listing with imports/functions/main block; incomplete system because dependencies and child scripts are missing |

The transcription removes page furniture, normalizes trailing whitespace/line endings, and adds provenance comments. The two site-coordinate constants are replaced with `0.0` placeholders for publication; no original coordinates are included. One extracted NUL in a corrupted docstring is represented as a literal escape. Other encoding defects and the original logic are preserved. No behavioral repairs, missing functions, or dependencies were invented.

A syntax-only AST parse succeeded. No imports or project code were executed; this does not verify operation.

## Original image-based code excerpts

The following files preserve original embedded code screenshots. Several contain cropped lines or undefined surrounding variables. They were intentionally not guessed into complete Python modules. Full-page context was reviewed in the report; an image alone is not proof of a complete implementation.

| Extracted image | PDF page | Purpose | Completeness |
| --- | ---: | --- | --- |
| [`pdf-p35-Im12.jpg`](../source/report-excerpts/pdf-p35-Im12.jpg) | 35 | Dataset download / YAML / split excerpts | Partial original image; not an executable file |
| [`pdf-p35-Im13.jpg`](../source/report-excerpts/pdf-p35-Im13.jpg) | 35 | Dataset download / YAML / split excerpts | Partial original image; not an executable file |
| [`pdf-p35-Im14.jpg`](../source/report-excerpts/pdf-p35-Im14.jpg) | 35 | Dataset download / YAML / split excerpts | Partial original image; not an executable file |
| [`pdf-p36-Im15.jpg`](../source/report-excerpts/pdf-p36-Im15.jpg) | 36 | Full-image labels / YOLO training call | Partial original image; not an executable file |
| [`pdf-p36-Im16.jpg`](../source/report-excerpts/pdf-p36-Im16.jpg) | 36 | Full-image labels / YOLO training call | Partial original image; not an executable file |
| [`pdf-p37-Im19.jpg`](../source/report-excerpts/pdf-p37-Im19.jpg) | 37 | YOLO prediction excerpt | Partial original image; not an executable file |
| [`pdf-p38-Im21.jpg`](../source/report-excerpts/pdf-p38-Im21.jpg) | 38 | ONNX export / face dataset and detection excerpts | Partial original image; not an executable file |
| [`pdf-p38-Im22.png`](../source/report-excerpts/pdf-p38-Im22.png) | 38 | ONNX export / face dataset and detection excerpts | Partial original image; not an executable file |
| [`pdf-p38-Im23.png`](../source/report-excerpts/pdf-p38-Im23.png) | 38 | ONNX export / face dataset and detection excerpts | Partial original image; not an executable file |
| [`pdf-p38-Im24.png`](../source/report-excerpts/pdf-p38-Im24.png) | 38 | ONNX export / face dataset and detection excerpts | Partial original image; not an executable file |
| [`pdf-p38-Im25.png`](../source/report-excerpts/pdf-p38-Im25.png) | 38 | ONNX export / face dataset and detection excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im26.png`](../source/report-excerpts/pdf-p39-Im26.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im27.png`](../source/report-excerpts/pdf-p39-Im27.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im28.png`](../source/report-excerpts/pdf-p39-Im28.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im29.png`](../source/report-excerpts/pdf-p39-Im29.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im30.png`](../source/report-excerpts/pdf-p39-Im30.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p39-Im31.png`](../source/report-excerpts/pdf-p39-Im31.png) | 39 | Face embeddings / labels / matching excerpts | Partial original image; not an executable file |
| [`pdf-p40-Im32.png`](../source/report-excerpts/pdf-p40-Im32.png) | 40 | Face matching / camera / serialization excerpts | Partial original image; not an executable file |
| [`pdf-p40-Im33.png`](../source/report-excerpts/pdf-p40-Im33.png) | 40 | Face matching / camera / serialization excerpts | Partial original image; not an executable file |
| [`pdf-p40-Im34.png`](../source/report-excerpts/pdf-p40-Im34.png) | 40 | Face matching / camera / serialization excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im35.png`](../source/report-excerpts/pdf-p41-Im35.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im36.png`](../source/report-excerpts/pdf-p41-Im36.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im37.png`](../source/report-excerpts/pdf-p41-Im37.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im38.png`](../source/report-excerpts/pdf-p41-Im38.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im39.png`](../source/report-excerpts/pdf-p41-Im39.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im40.png`](../source/report-excerpts/pdf-p41-Im40.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p41-Im41.png`](../source/report-excerpts/pdf-p41-Im41.png) | 41 | Face deployment excerpts | Partial original image; not an executable file |
| [`pdf-p42-Im42.png`](../source/report-excerpts/pdf-p42-Im42.png) | 42 | Face display-loop excerpts | Partial original image; not an executable file |
| [`pdf-p42-Im43.png`](../source/report-excerpts/pdf-p42-Im43.png) | 42 | Face display-loop excerpts | Partial original image; not an executable file |
| [`pdf-p51-Im63.png`](../source/report-excerpts/pdf-p51-Im63.png) | 51 | Embedding load excerpt | Partial original image; not an executable file |
| [`pdf-p52-Im64.png`](../source/report-excerpts/pdf-p52-Im64.png) | 52 | Camera / face matching / profile query / ONNX / tracking excerpts | Partial original image; not an executable file |
| [`pdf-p52-Im65.png`](../source/report-excerpts/pdf-p52-Im65.png) | 52 | Camera / face matching / profile query / ONNX / tracking excerpts | Partial original image; not an executable file |
| [`pdf-p52-Im66.png`](../source/report-excerpts/pdf-p52-Im66.png) | 52 | Camera / face matching / profile query / ONNX / tracking excerpts | Partial original image; not an executable file |
| [`pdf-p52-Im67.png`](../source/report-excerpts/pdf-p52-Im67.png) | 52 | Camera / face matching / profile query / ONNX / tracking excerpts | Partial original image; not an executable file |
| [`pdf-p52-Im68.png`](../source/report-excerpts/pdf-p52-Im68.png) | 52 | Camera / face matching / profile query / ONNX / tracking excerpts | Partial original image; not an executable file |
| [`pdf-p53-Im69.png`](../source/report-excerpts/pdf-p53-Im69.png) | 53 | Scheduling / process-control excerpts | Partial original image; not an executable file |
| [`pdf-p53-Im70.png`](../source/report-excerpts/pdf-p53-Im70.png) | 53 | Scheduling / process-control excerpts | Partial original image; not an executable file |
| [`pdf-p54-Im71.png`](../source/report-excerpts/pdf-p54-Im71.png) | 54 | Display loop excerpt | Partial original image; not an executable file |

## Referenced but unavailable materials

| Original name / component | Evidence location | Availability and purpose |
| --- | --- | --- |
| `facial_recognition.py` | pp.38-42, 51-52; named p.69 | Complete face recognition file missing; only excerpts |
| `obj_1.py` | p.52; named pp.69, 72 | Complete medication detector missing |
| `safetyM.py` | pp.69, 73 | Invocation only; implementation and audio absent |
| CareGuard frontend/backend | p.63; client calls p.71 | No source files or confirmed backend framework |
| `encodings.pickle` | pp.39-41, 51 | Face embeddings/names missing; private asset, excluded |
| `relations.db` | p.52 | Profile query only; database/full schema missing |
| `reminders.db` | pp.53, 69-70 | Controller schema available, original database absent and excluded |
| `data.yaml` | pp.35-36 | Generation/training references only; complete file absent |
| `yolov8n.pt` | p.36 | Base weights referenced, not supplied |
| `runs/detect/train-6/weights/best.pt` | pp.37-38 | Trained weights referenced, not supplied |
| `yolov8n.onnx` | p.42 | Deployment name in prose; binary and correspondence to export unverified |
| Training data and annotations | pp.35-40 | Missing; final splits, class mapping, rights, and logs unresolved |
| SORT implementation and supporting dependencies | p.52 | No complete tracker definition or version manifest |
| `/boot/firmware/config.txt` | pp.43-44 | Partial screenshot, not the original configuration file; not recreated |

A file-picker screenshot on p.51 contains additional filenames, but does not establish their contents or their role in the final system. No replacement files were created for those names.

## Verification boundary

Portfolio checks cover documentation links, asset presence, selected image review, source-transcription comparison, and preservation of the original PDF. They do not validate device wiring, model accuracy, application behavior, source completeness, or clinical suitability. No packages were installed, extracted project code executed, Git repository initialized, or material published during portfolio preparation. Redistribution permission for team-authored source and code-excerpt images remains a publication blocker.
