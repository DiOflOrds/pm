# Projekt-Pool (pm/D005, 2026-08-16) — Kandidaten, per Zuruf/Knopf startbar

*Gepflegt vom PM-Team. Start: Knopf im HMI (CR T-0011) oder einfach „starte <Name>" — Gründung läuft dann als Ordner in `projects/` (D003). Reihenfolge = PM-Empfehlung.*

## Team-Kandidaten (aus deiner ursprünglichen Vision)

| # | Kandidat | Nutzen | Voraussetzung |
|---|---|---|---|
| 1 | **team-termine** — Kalender-/Termin-Team | Enpal-&-Co-Termine aus Mails erkennen, Terminliste je Woche im HMI/Digest | keine (nutzt Mail-Rohdaten) |
| 2 | **team-finanzen** — Rechnungs-/Ausgabenübersicht | Rechnungs-Mails sammeln, Monatsübersicht (nur lesen/berichten, Guardrail 1) | keine |
| 3 | **team-wissenschaft** — Analyse-Team (Profil dienstleistung) | Recherche-/Auswertungsaufträge auf Zuruf | keine |
| 4 | **team-steuer** — Belegsammlung fürs Steuerjahr | Belege aus Mails vorsortieren; Abgabe bleibt Mensch (Klasse A, sensibel/lokal) | Datenklassen-Review |
| 5 | **team-trading** — Marktanalyse (nur Analyse!) | Watchlist-Berichte per Ollama; Order = niemals KI (Guardrail 1) | Klasse-A-Freigabe Datenquelle |
| 13 | **team-dashboard** — Ein Team, dass die Projekt Dashboards verwaltet, koordiniert und updatet. Ich möchte gerne ein neues Dashboard nur für Projekt-Teams anlegen, die dort nur die relevanten Infos anzeigt in einer sehr kompakten weise. in diesem Dashboard sollen mehrere Projekte gleichzeitig angezeigt werden, als eine Art Widget. Das Dashboard soll nicht scrollbar sein, sodass es auf eine Seite passt FHD. Die Widgets sollen dann individuell und konfigurierbar und abschaltbar dargestellt werden. Es soll auf der Startseite diese widgets dargestellt werden aber auch fürac jedes projekt auch eine eigene Seite dargestellt werden können. Für das Mail-Team soll hier ein Widget mit Zusammenfassung von Tag der Mails auf der Startseite sein. Das Dashboard sollte irgendwann (langfristiges Ziel) auch vom Mensch Handy aus dem internet aufgerufen werden. | Ein extra Dashboard, damit die Teams dem Menschen die Ergebnisse und Status präsentiert. | Die Projekte haben eine Widget Kompatibilität |

## Technik-Kandidaten (ASPICE-Backlog)

| # | Kandidat | Quelle |
|---|---|---|
| 6 | mail_digest → Katalog-Produkt (Promotion mit SWRs) | B003, Pilotreview 29.08. |
| 7 | Markdown-Renderer auch für Briefe/Reports | P7-LeLe |
| 8 | JS-Frontend-Tests | P3-R1 |
| 9 | Schätz-Kalibrierung (E5-Auswertung automatisiert) | P2-R1 |
| 10 | Produkt-Architekturbilder | P3-R2 |
| 11 | Live-API-Chat (kostenpflichtig — Budget-DR nötig) | P4-Rest |
| 12 | B4 Integrationsstrategie · B8 Embedded-Vorbereitung · B10 VM | P0-Überhang |
