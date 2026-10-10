# CareGuard web application

Sources: PDF p.63, Figure 4.7, and controller PDF pp.69–74. Contribution context additionally comes from the repository owner.

## Visible interface

The CareGuard screenshot contains a map with Leaflet/OSM attribution, location/update information, a “Today's Reminders” table, and navigation labels for Dashboard, Map, Reminders, Faces, and Alerts. Reminder rows show medicine, time, and labels such as Done, Now, and Upcoming.

This documents a caregiver interface, but one screenshot does not prove every navigation target, editing operation, notification route, or authentication feature works. The image simultaneously shows “No GPS Fix” and coordinates; those coordinates cannot be treated as proof of a current valid position. A Done label does not establish medication ingestion or camera-confirmed completion.

## Integration that can be inspected

The Python controller writes reminders-related alerts and GPS records to SQLite and sends JSON to local `/api/gps` and `/api/alert` endpoints. See [architecture](architecture.md) for payload fields. The controller does not launch the web server.

The broader design intends caregiver schedule updates to feed device reminders. Backend routes, database access code, HTML/CSS/JavaScript, polling or streaming, and the mapping between UI status and controller state are not present in the report. A native Flutter mobile application is not demonstrated.

## Contribution and engineering value

The repository owner developed CareGuard by defining its requirements and features, directing AI-assisted implementation through prompts, and iteratively refining the generated application. The owner also adapted and integrated teammate-provided software modules using AI-assisted workflows, participated in physical hardware assembly, and contributed to integrated testing and troubleshooting. A teammate transferred and ran the prepared code on the Raspberry Pi; they collaborated on operation with the prototype and CareGuard. See [my contributions](my-contributions.md) for the owner-supplied account and attribution boundaries.

The application is presented as one part of the integrated engineering system. Recovering its original source would allow a stronger account of the device-to-dashboard workflow, data validation, and implementation decisions.

## Publication and missing evidence

The report-derived dashboard image remains unextracted. The README now includes two separately supplied original CareGuard screenshots: the dashboard and reminder list. The owner confirms that their location and coordinates are arbitrary demonstration data and authorizes retaining them. No interface content or displayed results were altered. See the [asset inventory](../assets/README.md) for provenance; the report screenshot discussed above is distinct from these additional screenshots.

Missing materials include original frontend/backend files, dependency versions, schemas or migrations, authentication/access details, and evidence of successful schedule updates and alert delivery. Remote network access, HTTPS, and production hosting are not claimed.
