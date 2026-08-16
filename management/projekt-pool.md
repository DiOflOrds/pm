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

## Technik-Kandidaten (ASPICE-Backlog)

| # | Kandidat | Quelle |
|---|---|---|
| 6 | mail_digest → Katalog-Produkt (Promotion mit SWRs) | B003, Pilotreview 29.08. |
| 8 | JS-Frontend-Tests | P3-R1 |
| 9 | Schätz-Kalibrierung (E5-Auswertung automatisiert) | P2-R1 |
| 10 | Produkt-Architekturbilder | P3-R2 |
| 11 | Live-API-Chat (kostenpflichtig — Budget-DR nötig) | P4-Rest |
| 12 | B4 Integrationsstrategie · B8 Embedded-Vorbereitung · B10 VM | P0-Überhang |

## Realisiert (aus dem Pool herausgelaufen — Nummern werden nicht neu vergeben)

| # | Kandidat | Wohin | Beleg |
|---|---|---|---|
| 13 | **team-dashboard** — Dashboards verwalten/koordinieren + kompaktes Widget-Dashboard | Team `team-dashboard` (Gründung) **und** Projekt **P11 „Widget-Dashboard"** (Bau, `projects/p11`) — „verwalten" ist Daueraufgabe, „bauen" ist ein Projekt | pm/N-0027, pm/T-0031 → pm/D006 (TG-a, 15:21), pm/T-0033 → pm/D007 (G0a, 15:55) |

*Warum dieser Abschnitt und keine stille Löschung: Ein Kandidat, der aus der Liste verschwindet,
sieht aus wie ein Kandidat, den nie jemand wollte. Die Zeile steht hier, damit nachvollziehbar
bleibt, wohin der Wunsch gegangen ist (Lesson B029 — eine Zusage, die geräuschlos verschwindet,
fällt erst auf, wenn zum zweiten Mal danach gefragt wird).*
