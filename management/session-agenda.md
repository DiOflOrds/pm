# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

*Stand: 2026-08-16, Routine-Session (D004, alle 30 Min). **P10-Intake vollzogen** (B018): `projects/p10` steht — Projektauftrag, STK-020, SWR-077–081 (`draft`), Sprint-0-Plan, D000, board-check-Workflow fürs Sammel-Repo; **G1-DR `p10/T-0002` liegt in deiner Inbox** (Frist 23.08., Default G1a). Beim ersten verschachtelten Projekt fiel ein blinder Fleck auf: Preflight und Matrix sahen nur Top-Level-Ordner — als Befund `p9/T-0007` sofort behoben (gemeinsame Discovery, 6 neue Tests, B019). **194 Tests, Matrix 81/0, 0,00 € API.** Briefkasten: keine offenen Briefe. Reihenfolge für die nächste Session:*

0. **`pm/T-0012` (N-0015): Kopfbereich zeigt nur aktive Projekte/Teams, direkt anklickbar** — höchste Priorität, wurde in dieser Session vom P10-Intake verdrängt. Serverseitige Gruppenableitung (damit Kopf und Cockpit nie auseinanderlaufen), abgeschlossene Projekte unter „weitere (n)" erreichbar, Deep-Links (`#/board/p3`) unverändert. Requirements-first als Nachtrag auf der P9-Fläche.
1. **Briefkasten zuerst** — alle Projekte/Teams (Cockpit zeigt offene Briefe). *Zwei Briefe kamen mitten in dieser Session an und sind erledigt (B020): `pm/N-0017` Cockpit-Klartext für wiederkehrende Aufgaben (pm/T-0014), `platform/N-0001` board-check rot durch Push-Reihenfolge (pm/T-0013, `in_review` bis grüner Lauf).*
2. **P10 Sprint 1 — erst nach deiner G1-Antwort** (`p10/T-0002`, Default G1a greift am 23.08.): ADR-007 (zweiter Schreibpfad auf Tickets neben der Skript-Route), Backend-Schreibendpunkt mit Validierung/Fingerprint/Commit, Label-Feld in `board.py` + Board-Filter, Editor im HMI, PIN-Gate, Tests, G4 (Baseline `p10-v1.0`).
3. **team-mail-Takt (T-0001):** fälligen Digest prüfen (der Autopilot erzeugt ihn i. d. R. selbst um 07:30) und als SLA-Stichprobe bewerten — Zustellvermerk am Dateiende. *Heutiger Tages-Digest liegt zugestellt vor (B011) — in dieser Session nichts fällig.* Offene Vortages-Punkte im Postfach: Vedaco-„Doppelzahlung" (Phishing-Verdacht), Enpal-Termin, M-net-Umstellung, Google-Sicherheitswarnung. *Handeln tut hier ausschließlich der Mensch (F17).*
4. **Fällige pm-Takt-Tickets** — Intake-Queue, Agenda fortschreiben; PUSH-ANFORDERUNG.txt am Session-Ende schreiben (Runbook Kap. 11).
5. **Offene Stichproben des Auftraggebers nachhalten** (nur erinnern, nie selbst abhaken):
   - **Neu (B018):** G1-Entscheidung `p10/T-0002` — 3 Min Lesen im Requirements-Tab (Projekt p10, nach Push); zwei Rückfragen darin wollen ausdrücklich deine Antwort („neues Projekt" als Label statt Typ? Tickets im HMI auch anlegen/löschen?).
   - P9-Cockpit: 3 Stichproben aus `p9/T-0004` (Gruppen, Einklappen, Aufgaben-Links) — vorher Server per ⟳ neu starten.
   - Aus B010: Konfigurator öffnen → **KI-Modell** auswählen und **KI-Hinweis** eintragen, speichern, „Jetzt zusammenfassen" laufen lassen und den Digest inhaltlich bewerten.
   - Aus B013: **Selbst-Neustart** — Mission Control über `mission-control.cmd` starten (einmal manuell neu starten, damit die neue Fassung läuft), dann prüfen, ob der Server nach einer Session von allein hochkommt und die Seite nachlädt.
   - Aus B014: **Takt-Kennzeichnung** — Board von `pm` öffnen: T-0001/T-0002 „wiederkehrend: je Session", T-0003 einmalig.
6. **Einmalig nötig (Mensch), sonst bleibt P10 ungeprüft in der CI:** im GitHub-Repo `DiOflOrds/projects` das Secret **PLATFORM_READ_TOKEN** hinterlegen (dieselbe Lese-PAT wie bei p0–p9/pm) — der neue board-check-Workflow prüft dort jeden Projektordner. Lokal läuft der Check bereits über den Preflight.
7. **pm/T-0010** (board-check-Flake) bleibt `in_review`, bis ein GitHub-Actions-Lauf nach dem Fix grün gemeldet ist — lokal ist board-check grün.
8. **Pilotreview:** team-mail ab 2026-08-29 (B002) — Digest-Format-Feedback, B003 (Werkzeug-Promotion), CR-Kandidat Markdown-Renderer für Briefe/Reports.
9. **Betriebs-Backlog** — BB-5 PAT-Erneuerung ab 2026-09-05 (ab 1.9. aktiv erinnern).

*Hinweis (D004): Diese Agenda wird automatisch alle 30 Min von der Cowork-Routine-Session abgearbeitet (solange die App offen ist) — Briefe genügen, Ankündigungen im Chat sind nicht mehr nötig.*

*Beobachtung 2026-08-16 (für die Retro/LeLe): Zwei Routine-Sessions können sich überlappen. Erkennungsmerkmal ist ein `.git/index.lock`, das die eigene Arbeit blockiert; Auflösung siehe Runbook Kap. 3 (Preflight erneut, ggf. Cowork-Löschrecht erteilen). Regel: erst Repo-Status prüfen, dann schreiben — nie doppelt verbuchen.*

*Lesson 2026-08-16 (aus p9/T-0007, für die Retro/LeLe): Wenn eine Anforderung „die Werkzeuge sollen X unterstützen" sagt, ist sie erst erfüllt, wenn jede Kopie der betroffenen Logik nachgezogen — besser: zu einer zusammengeführt — ist. DoD-Prüffrage: „Gibt es diese Auflösung noch ein zweites Mal im Repo?"*

*Einsprüche des Menschen gegen Agenda-Prioritäten: einfach im Briefkasten/Chat hinterlassen — wird als neue Log-Zeile verbucht.*
