# System architecture

## Evidence and scope

Sources: report PDF pp.19–22, 31–34, 40–54, 63, and 69–74. Page numbers include the cover. The selected alternative uses local processing on Raspberry Pi 4; the ESP32/cloud alternative was not selected.

The original architecture expresses design intent. The appendix provides the strongest inspectable evidence for controller behavior. Neither alone verifies all end-to-end functionality.

## Hardware-to-software path

The CSI camera supplies frames to the active vision process. Face excerpts use Picamera2, OpenCV, HOG face detection, and dlib embeddings. Known identities come from `encodings.pickle`; additional profile fields are queried from `relations.db`. OpenCV draws results for the HDMI LCD.

Medication detection uses a YOLO model exported to ONNX, with ONNX Runtime output processing, NMS, and reported SORT tracking. Its complete input preprocessing, label mapping, target filtering, and tracking implementation are unavailable.

GPS communicates through UART. The controller opens `/dev/ttyS0` at 9600 baud and accepts valid `$GPRMC` or `$GNRMC` messages. It uses Haversine distance and a configured 0.3 km radius to determine geofence state.

## Controller lifecycle

1. Initialize SQLite tables and start daemon threads for geofencing, stationary-location monitoring, and console input.
2. Start `facial_recognition.py` using the `face_rec` environment.
3. Poll for a reminder matching the local system hour and minute.
4. Log/post a reminder alert, stop the face process, and start `obj_1.py` using the `obj` environment, passing the medicine name as an argument.
5. Wait 60 seconds, stop medication detection, and restart face recognition.
6. On `KeyboardInterrupt`, attempt to stop both vision processes.

Console input `r` sets a manual trigger whose target is the literal `manual_trigger`. Whether the missing object module accepts that value is unknown.

The diagram on PDF pp.32–33 describes a five-minute no-detection fallback; the appendix instead uses a fixed 60-second duration without reading detection outcomes. The conclusion's claim of simultaneous AI pipelines conflicts with this process-switching implementation.

## Persistence

| Asset | Visible structure or use |
| --- | --- |
| `reminders.db` / `reminders` | `id`, `medicine`, `hour`, `minute` |
| `reminders.db` / `gps_log` | `id`, `latitude`, `longitude`, `inside_geofence`, `recorded_at` |
| `reminders.db` / `alerts` | `id`, `type`, `message`, `created_at` |
| `reminders.db` / `faces` | `id`, `name`, `relation`, `added_at` |
| `relations.db` / `relations` | Excerpt selects `relationship`, `phone_number`, and `info` using `name`; full schema missing |
| `encodings.pickle` | Serialized `encodings` and `names` |

The controller requests SQLite WAL mode. No migration or synchronization mechanism connecting the two databases and embeddings is shown. A chapter-three reminder excerpt selects `name`, while the appendix uses `medicine`; these versions must not be merged without verification.

## HTTP integration boundary

The controller uses `http://localhost:5000` and a two-second request timeout:

| Endpoint | JSON fields | Evidence |
| --- | --- | --- |
| `POST /api/gps` | `latitude`, `longitude`, `inside_geofence` | Client call present |
| `POST /api/alert` | `type`, `message` | Client call present |

Visible alert types include `geofence_breach`, `geofence_return`, and `reminder`. Records are written to SQLite before the HTTP request. The server code, response contract, frontend refresh mechanism, and any remote access configuration are unavailable. Port 5000 does not establish Flask.

The proposed reverse path lets caregivers update schedules. A dashboard image supports reminder presentation, but the update implementation cannot be inspected. Local inference does not establish that map tiles or remote caregiver access function offline.

## Safety and reliability boundaries

Stationary monitoring compares consecutive coordinates for exact equality and invokes missing `safetyM.py` after five minutes. This is not direct helmet-removal sensing. The two GPS threads independently open the same serial port, and no shared reader is implemented in the appendix. See [limitations](limitations.md) for further static-review findings.
