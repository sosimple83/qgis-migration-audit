# QGIS 4.2 LTR Migrations-Audit Tool

Ein vollautomatisierter n8n-Workflow zur Durchführung von Migrations-Audits für QGIS 4.2 LTR. Das Tool bewertet Systemparameter, berechnet einen Readiness-Score (0-20 Punkte), generiert einen HTML-Report und steuert das automatisierte PDF-Rendering sowie den E-Mail-Versand für Leads.

## Architektur
`Webhook` -> `Code Node (Core Logic & Defensive Programming)` -> `If-Node (Routing)` -> `PDFShift / Dead-Letter`

## Features
* **Robuste Daten-Normalisierung:** Null-Pointer-Schutz und Typ-Sicherheit im JavaScript-Code.
* **Dead-Letter-Handling:** Trennung von validen und korrupten Payloads.
* **Lead-Qualifier:** Automatisierte Risikoeinstufung für GIS-Arbeitsplätze und Behörden-Infrastrukturen.

## Installation in n8n
1. Neues Workflow in n8n anlegen.
2. Inhalt der `workflow.json` in den Editor importieren.
3. Credentials für SMTP und PDFShift (API-Key) hinterlegen.
4. Workflow aktivieren.