# Software stack and model assets

Sources: PDF pp.26–27, 35–42, 46–53, 63, and 69–74.

| Layer | Evidence-supported technology | Qualification |
| --- | --- | --- |
| Device OS | Raspberry Pi OS 64-bit | Exact deployed image/version not established |
| Development | Python 3, virtual environments, Thonny | No complete version manifest |
| Camera | Picamera2 | Image excerpts show capture and preview configuration |
| Image processing | OpenCV, NumPy | Used by vision excerpts |
| Face recognition | `face_recognition`, dlib HOG detector, 128-D embeddings | Tolerance 0.6 appears in code |
| Medication training | Ultralytics YOLOv8n | Screenshot uses 50 epochs, image size 640, batch 16 |
| Deployment | ONNX Runtime | Model file unavailable |
| Postprocessing | NMS and reported SORT | Complete tracker source and dependency chain unavailable |
| Data | SQLite, `pickle` | Private databases and embeddings intentionally excluded |
| Device integration | `pyserial`, `pynmea2`, `requests` | Visible imports and use in controller |
| Process control | Python `subprocess`, `threading`, `signal`, `time` | Standard-library controller logic |
| Data preparation | `kagglehub`, PIL/Image, `imutils.paths` | Visible in report snippets; preparation scripts incomplete |
| Web map | Leaflet / OSM attribution | Visible in CareGuard screenshot; frontend source missing |

## Model preparation

Face preparation uses a pretrained embedding model to encode identity-labeled images into `encodings.pickle`. This is not evidence of training the dlib neural network from scratch. The report describes dataset splitting and threshold evaluation, but does not include a complete reproducible procedure.

YOLO screenshots show loading `yolov8n.pt`, training against `data.yaml`, using `runs/detect/train-6/weights/best.pt`, and exporting ONNX. Deployment prose names `yolov8n.onnx`; its exact relationship to the trained export cannot be verified without the files.

The dataset-loading screenshot uses Kaggle tooling while the surrounding prose says GitHub. The annotation excerpt uses a full-image bounding box (`0.5 0.5 1.0 1.0`). Dataset provenance, licensing, split integrity, and localization-label quality need review before claiming reproducibility or generalization.

## Requirements versus implemented stack

Edge Impulse, TensorFlow Lite, Flutter, GPSD, and Pygame Mixer appear in early requirements. Their final use is not established by available implementation evidence. The local web service's port does not identify its backend framework.

No `requirements.txt`, lockfile, or installation sequence is supplied in this repository: versions and the complete dependency set are unknown. Original environment paths in the controller document the prototype setup; they are not portable installation instructions.
