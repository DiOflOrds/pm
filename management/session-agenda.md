# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

*Stand: 2026-08-16, Routine-Session (D004, alle 30 Min). **Agenda-Punkt 0 erledigt (B021): `pm/T-0012` ist umgesetzt** — der Kopfbereich zeigt anklickbare Einträge in den Cockpit-Gruppen, abgeschlossene Projekte hinter „weitere (n)", Ableitung serverseitig über eine gemeinsame Einstufung (`/api/navigation`, SWR-082 auf der P9-Fläche v1.3). Dazu Brief `pm/N-0018` erledigt (Team-Chat neueste zuerst, SWR-083, B022). **199 Tests, Matrix 83/0, 0,00 € API.** Briefkasten: keine offenen Briefe. Inbox: `p10/T-0002` (G1) wartet weiter auf den Menschen — Klasse A, wird vom Team nicht entschieden. Reihenfolge für die nächste Session:*

0. **Briefkasten zuerst** — alle Projekte/Teams (Cockpit zeigt offene Briefe). *`pm/N-0018` („beim teamchat sollen die neuesten zuerst kommen") kam während der Session an und ist erledigt: Verlauf neueste-zuerst, Schreibfeld nach oben mitgezogen (SWR-083, P4-Fläche v1.1, pm/T-0015, B022). Danach keine offenen Briefe mehr.*
1. **`pm/T-0012` erledigt (B021)** — offen bleibt nur die Stichprobe des Auftraggebers: Server neu starten, oben klicken, Deep-Link auf ein abgeschlossenes Projekt prüfen (siehe Punkt 5).
2. **P10 Sprint 1 — erst nach deiner G1-Antwort** (`p10/T-0002`, Default G1a greift am 23.08.): ADR-007 (zweiter Schreibpfad auf Tickets neben der Skript-Route), Backend-Schreibendpunkt mit Validierung/Fingerprint/Commit, Label-Feld in `board.py` + Board-Filter, Editor im HMI, PIN-Gate, Tests, G4 (Baseline `p10-v1.0`).
3. **team-mail-Takt (T-0001):** fälligen Digest prüfen (der Autopilot erzeugt ihn i. d. R. selbst um 07:30) und als SLA-Stichprobe bewerten — Zustellvermerk am Dateiende. *Heutiger Tages-Digest liegt zugestellt vor (B011) — in dieser Session nichts fällig.* Offene Vortages-Punkte im Postfach: Vedaco-„Doppelzahlung" (Phishing-Verdacht), Enpal-Termin, M-net-Umstellung, Google-Sicherheitswarnung. *Handeln tut hier ausschließlich der Mensch (F17).*
4. **Fällige pm-Takt-Tickets** — Intake-Queue, Agenda fortschreiben; PUSH-ANFORDERUNG.txt am Session-Ende schreiben (Runbook Kap. 11).
5. **Offene Stichproben des Auftraggebers nachhalten** (nur erinnern, nie selbst abhaken):
   - **Neu (B021):** **Kopfbereich** — Server neu starten, dann oben prüfen: stehen nur noch feste Teams, Projekt-Teams und aktive Projekte da, sind sie per Klick erreichbar, und öffnet ein Deep-Link auf ein abgeschlossenes Projekt (`#/board/p3`) die Liste „weitere" von allein? Auch auf dem Handy.
   - **Aus B018:** G1-Entscheidung `p10/T-0002` — 3 Min Lesen im Requirements-Tab (Projekt p10, nach Push); zwei Rückfragen darin wollen ausdrücklich deine Antwort („neues Projekt" als Label statt Typ? Tickets im HMI auch anlegen/löschen?).
   - P9-Cockpit: 3 Stichproben aus `p9/T-0004` (Gruppen, Einklappen, Aufgaben-Links) — vorher Server per ⟳ neu starten.
   - Aus B010: Konfigurator öffnen → **KI-Modell** auswählen und **KI-Hinweis** eintragen, speichern, „Jetzt zusammenfassen" laufen lassen und den Digest inhaltlich bewerten.
   - Aus B013: **Selbst-Neustart** — Mission Control über `mission-control.cmd` starten (einmal manuell neu starten, damit die neue Fassung läuft), dann prüfen, ob der Server nach einer Session von allein hochkommt und die Seite nachlädt.
   - Aus B014: **Takt-Kennzeichnung** — Board von `pm` öffnen: T-0001/T-0002 „wiederkehrend: je Session", T-0003 einmalig.
6. ~~Secret `PLATFORM_READ_TOKEN` für `DiOflOrds/projects` hinterlegen~~ **erledigt — lag schon vor** (bestätigt vom Auftraggeber, 2026-08-16). Der neue board-check-Workflow prüft dort jeden Projektordner ohne weiteres Zutun; erster Nachweis ist der Actions-Lauf nach dem nächsten Push.
7. **pm/T-0010** (board-check-Flake) bleibt `in_review`, bis ein GitHub-Actions-Lauf nach dem Fix grün gemeldet ist — lokal ist board-check grün.
8. **Pilotreview:** team-mail ab 2026-08-29 (B002) — Digest-Format-Feedback, B003 (Werkzeug-Promotion), CR-Kandidat Markdown-Renderer für Briefe/Reports.
9. **Betriebs-Backlog** — BB-5 PAT-Erneuerung ab 2026-09-05 (ab 1.9. aktiv erinnern). **Neuer CR-Kandidat (aus pm/T-0013):** `abschluss.cmd`, `abschluss-auto.cmd` und die `mission-control*.cmd` liegen **unversioniert** im Wurzelordner — heute wurde dort ein Fehler behoben, der bei einem Plattenschaden ersatzlos weg wäre. Vorschlag: Skripte nach `platform/infra/` versionieren und im Wurzelordner nur noch dünne Aufrufer lassen. Zweiter CR-Kandidat: Projekt-Workflows checken `platform` auf einem **Tag** statt `main` aus (macht die Werkzeugversion explizit statt zeitabhängig).

*Hinweis (D004): Diese Agenda wird automatisch alle 30 Min von der Cowork-Routine-Session abgearbeitet (solange die App offen ist) — Briefe genügen, Ankündigungen im Chat sind nicht mehr nötig.*

*Beobachtung 2026-08-16 (für die Retro/LeLe): Zwei Routine-Sessions können sich überlappen. Erkennungsmerkmal ist ein `.git/index.lock`, das die eigene Arbeit blockiert; Auflösung siehe Runbook Kap. 3 (Preflight erneut, ggf. Cowork-Löschrecht erteilen). Regel: erst Repo-Status prüfen, dann schreiben — nie doppelt verbuchen.*

*Lesson 2026-08-16 (aus p9/T-0007, für die Retro/LeLe): Wenn eine Anforderung „die Werkzeuge sollen X unterstützen" sagt, ist sie erst erfüllt, wenn jede Kopie der betroffenen Logik nachgezogen — besser: zu einer zusammengeführt — ist. DoD-Prüffrage: „Gibt es diese Auflösung noch ein zweites Mal im Repo?"*

*Einsprüche des Menschen gegen Agenda-Prioritäten: einfach im Briefkasten/Chat hinterlassen — wird als neue Log-Zeile verbucht.*
