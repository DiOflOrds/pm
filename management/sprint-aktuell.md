# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 12** (2026-08-17, Takt 60 Min, Start 11:27, Kennung
   `2026-08-17T1130-cowork-s12`). Der Zähler steht in `pm/management/sprints.jsonl`.
2. **Sprint 12 war der beschlossene HMI-Sprint — und der Beschluss hat gehalten.**
   Geschlossen: `projects/p12/T-0004`, `pm/T-0060`, `pm/T-0058`, Klammer `pm/T-0039`.
   Zwei der fünf HMI-Aufgaben sind erledigt, **B025 wurde in keinem Ticket mehr als Grund
   geführt.**
3. **⚠⚠ Der HMI-Sprint konnte seine eigene Abnahme nicht erfüllen.** Die DoD von
   `pm/T-0058` und `pm/T-0060` verlangt wörtlich *„JS-Test; scheitert nachweislich gegen
   den Vorstand"*. Gemessen im Bestand: **741 Python-Tests, 0 JS-Tests** bei **1.524
   Zeilen `app.js`** — während SWR-098/099/100 Nachweise an JavaScript verlangen.
   > **Eine Teststrecke, die es nicht gibt, meldet dasselbe wie eine, die grün ist:
   > nichts.** Fünf Sprints lang war „Tests grün" wahr — für die Tests, **die es gab**.

   Dritte Gestalt derselben Familie in drei Sprints: SWR-122 (Prüfung ohne Leser),
   SWR-125 (Regel ohne Prüfung), jetzt **Fläche ohne Prüfung**.
4. **Gebaut: ADR-008 + SWR-128.** Renderentscheidungen wandern nach
   `backend/static/regeln.js` (ohne DOM, ohne Netz), geprüft mit Nodes **eingebautem**
   Runner — **kein npm, kein package.json, keine Abhängigkeit**. ADR-002 („no build")
   bleibt damit gültig; es wird nicht widerrufen, sondern **eingelöst** — sein eigener Satz
   lautete *„bei wachsendem Frontend-Scope neu bewerten"*.
5. **⚠ Die Werkzeugfrage ist NICHT vom Team entschieden worden.** Ob Node Voraussetzung
   des Projekts wird, ist ein **neues externes Werkzeug** → **Klasse A** → Decision Request
   **`projects/p12/T-0007`** (Optionen A/B/C, Default `B-node-optional`, Frist 2026-08-24).
   Bis dahin zählt `übersprungen` **nicht** als Befund: ein Werkzeug, über das niemand
   entschieden hat, darf den Lauf des Menschen nicht blockieren.
6. **⚠ Und `übersprungen` ist nicht `ok`.** `js_tests.lauf()` kennt **drei** Zustände; der
   teuerste Test der Strecke ist der, der genau das verlangt. Wer nur zwei kennt, verbucht
   das Nichtlaufen als Erfolg — und genau so blieb „null JS-Tests" fünf Sprints unsichtbar.
7. **✅ `pm/T-0060` (SWR-129): der Brief ist im HMI ein Verlauf.** Beiträge mit Absender und
   Zeit, farblich nach Urheber, **Antwortfeld je Brief**, und der durch eine Nachfrage
   wieder geöffnete Brief trägt ein eigenes Schild. ⚠ Der Urheber wird aus der
   **Nutzerregistry** aufgelöst, nicht aus einem Vergleich mit `brief.von`: der Mensch darf
   beim Senden einen anderen registrierten Nutzer wählen — die Registry ist ein Fakt, der
   Namensvergleich wäre eine Annahme (B038). Die Gegenprobe dazu wird gegen die naive Regel
   rot.
8. **✅ `pm/T-0058` (SWR-130): die Nachricht erscheint ohne Reload — auch wenn der Commit
   scheitert.** Der 900-ms-Timer ist weg; nachgeladen wird, was `GET /api/briefkasten`
   liefert (kein zweiter Inhaltszustand, B033). Im 503-Fall wird **ebenfalls** nachgeladen
   und der Brief trägt „gespeichert, noch nicht verbucht" — die Datei liegt auf der Platte,
   **bevor** git läuft (SWR-121), und eine Liste, die sie verschweigt, behauptet das
   Gegenteil.
9. **✅ Klammer `pm/T-0039` geschlossen** — beide Teile erledigt (`T-0059` Sprint 11,
   `T-0060` Sprint 12). Vier Verschiebungen, eine Zerlegung, jetzt vollständig: der
   Auftraggeber kann im selben Brief weiterkommentieren **und sieht seine Nachfrage**.
10. **⚠ `pm/T-0054` nach ZWEI Verschiebungen zerlegt statt nach vier.** Sprint 11 zerlegte
    `pm/T-0028` beim vierten Mal und schrieb dazu die Erkennungsfrage *„auf welche anderen
    offenen Fälle trifft dieser Satz gerade zu?"* (`L-2026-08-17x`). Antwort dieses Laufs:
    auf `pm/T-0054`, und die Naht steht wörtlich im Ticket selbst („eine Liste … und der
    Knopf daneben"). Neu: `pm/T-0064` (Liste, Sprint 13), `pm/T-0065` (Knopf, Sprint 14).
11. **⚠⚠ Eine Zusage an den Auftraggeber ist NICHT eingelöst.** Sprint 11 schrieb ihm
    wörtlich: *„Offen: der Endpunkt, der die Kacheln liefert, und die Detailseiten. Beide
    im Oberflächen-Lauf als Nächstes."* Der Oberflächen-Lauf war dieser. `p11/T-0008` ist
    **dritte Verschiebung**, `p11/T-0009` zweite. Das steht im Ticket, im Bericht und in
    der Agenda — Verzug wird laut, nicht leise.
12. **⚠ Ein zweiter Routine-Lauf schrieb heute 10:25–11:21 gleichzeitig in dieselben
    Repos** (Befundbericht 11:05, kein Commit dieses Laufs). Aufgenommen als
    **`platform/T-0013`**: `sprint_register.beginne()` ist idempotent je *Kennung*, kennt
    aber keinen Fall für **zwei verschiedene** Läufe. *Ein Register ohne Endezeitpunkt kann
    Überlappung nicht sehen.* Dieser Lauf hat vor dem ersten Schreiben **vier
    Kontrollmessungen** gebraucht, bis die HEADs still standen.
13. **⚠ Ein Schreibversuch hat in diesem Lauf eine Datei zerstört** — `preflight.py` wurde
    von einem Patch-Skript mit ungültigem `newline`-Wert auf **0 Bytes** gekürzt, *bevor*
    die Ausnahme flog. Ohne Folgen, weil auf einer Arbeitskopie gearbeitet wurde. Dieselbe
    Klasse wie `abschluss.cmd` in Sprint 1. Verankert als `L-2026-08-17y`: **Temp-Datei
    schreiben, dann `os.replace`.**
14. **752 Python-Tests grün** (+11), **16 JS-Tests grün** (+16, von null), Matrix **130
    SWRs / 0 Lücken**.

## Sprint-Plan

*Sprint 12 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. Verschieben
nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder blockiert. **Fest geplant** ist
Sprint 13; ab Sprint 14 ist die Nummer eine **Reihenfolge**, keine Zusage.*

*Keine Kalenderdaten in der Fälligkeitsspalte (SWR-125). Ein Datum steht nur dort, wo ein
**Mensch** wartet — bei `p12/T-0007` (DR, Frist 2026-08-24).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| projects/p12/T-0004 | pl | dieser Sprint | **erledigt** | **ADR-008**: Renderregeln ohne DOM (`regeln.js`), Runner ohne Paket (`node --test`), Zustand **immer** gemeldet. Drei Optionen einzeln bewertet. **SWR-128**, 13 Python-Zusicherungen. ⚠ Die Werkzeugfrage ist Klasse A und **nicht hier** entschieden → DR `p12/T-0007`. |
| pm/T-0060 | dev | dieser Sprint | **erledigt** | **SWR-129**: Brief als Verlauf, Antwortfeld je Brief, Nachfrage sichtbar. Urheber aus der Nutzerregistry (nicht aus `brief.von`). 11 JS-Zusicherungen, davon 5 Gegenproben. |
| pm/T-0058 | dev | dieser Sprint | **erledigt** | **SWR-130**: sofortiges Nachladen statt 900-ms-Timer; im 503-Fall „gespeichert, noch nicht verbucht" statt „gescheitert". 3 JS-Zusicherungen, 2 davon Gegenproben. |
| pm/T-0039 | pl | dieser Sprint | **erledigt** | **Klammer geschlossen** — `T-0059` (Sprint 11) und `T-0060` (Sprint 12) sind beide erledigt. Der CR aus `pm/N-0031` ist vollständig. |
| projects/p12/T-0007 | mensch | **Frist 2026-08-24** | offen (DR) | **Neu.** Darf Node Voraussetzung werden? Optionen A/B/C, Default `B-node-optional`. ⚠ Kostet nichts und blockiert nichts — bis zur Antwort meldet der Preflight „übersprungen". |
| platform/T-0013 | cm | Sprint 13 | offen | **Neu, aus dem Nebenläufigkeitsbefund 11:05.** Sprintregister braucht ein **Ende**; `beginne()` verweigert bei laufendem Sprint. ⚠ Vor dem Bauen die Taktabstände **messen** — 07:10 / 09:14 / 10:04 / 11:27 sind nicht gleichmäßig 60 Min. Erste Terminierung. |
| pm/T-0064 | pl | Sprint 13 | offen | **Neu, erster Teil von `T-0054`.** Projektübergreifende Liste der offenen Aufgaben, lesend, aus `aggregation`. ⚠ **Nicht auf drei gekürzt** wie die Kachel — der Zweck ist, dass der Auftraggeber alles sieht. Renderregeln nach ADR-008. |
| pm/T-0065 | chg | Sprint 14 | offen | **Neu, zweiter Teil von `T-0054`.** Knopf setzt `geplant_sprint`, `blocked_by: [T-0064]`. Die drei Festlegungen stehen bereits. |
| pm/T-0054 | chg | Sprint 14 | **zerlegt** | ⚠ **Zwei Verschiebungen statt vier** — die Naht stand im Ticket („eine Liste … und der Knopf daneben"). Klammer trägt den Termin des letzten Teils. |
| pm/T-0052 | pl | Sprint 13 | offen | **3. Verschiebung, erster Grund dieser Art:** der HMI-Sprint musste zuerst seine Abnahmefähigkeit herstellen (0 JS-Tests). ⚠ Verfallsdatum: gilt nur für Sprint 12. **Beim vierten Mal wird zerlegt** — Naht zwischen „Für dich: Entscheidungen" und „Für dich: Handlungen". |
| pm/T-0063 | chg | Sprint 13 | offen | Charter-Entwurf + Gründungs-DR aus dem geprüften Steckbrief. `blocked_by: [T-0062]` erfüllt. **Erste Terminierung.** |
| pm/T-0061 | cm | Sprint 13 | offen | `sprint_widerspruch` hat nach SWR-125 keinen möglichen Fall mehr. ⚠ Vor der Entscheidung **messen**, ob die Prüfung je angeschlagen hat. **Erste Terminierung.** |
| pm/T-0028 | chg | Sprint 13 | **zerlegt** | **Klammer**, Termin des letzten Teils (`T-0063`). Keine Verschiebung — sie enthält selbst nichts. |
| projects/p11/T-0008 | dev | Sprint 13 | offen | ⚠⚠ **3. Verschiebung — und dem Auftraggeber in Sprint 11 zugesagt.** Nicht eingelöst; steht so im Ticket und im Bericht. **Bei der nächsten Berührung zerlegen**: Endpunkt (lesend) / Widget-Konfiguration (schreibend). |
| projects/p11/T-0009 | dev | Sprint 14 | offen | **2. Verschiebung.** Sachlich hinter `T-0008` — deshalb Sprint 14 und nicht 13: ein Ticket auf demselben Sprint wie seine Voraussetzung behauptet, beides gehe in einem Lauf. |
| projects/p11/T-0003 | pl | Sprint 14 | offen | **Klammer** über `T-0007`/`T-0008`/`T-0009`, nachgezogen auf `T-0009`. Keine Verschiebung. |
| projects/p12/T-0005 | pl | Sprint 13 | offen | ADR-Delta + Vollständigkeitsnachweis, `blocked_by: [T-0004]` — **ab jetzt erfüllt**. |
| projects/p12/T-0006 | pl | Sprint 14 | offen | Umstellung, Tests, G4, `blocked_by: [T-0005]`. |
| projects/p12/T-0003 | pl | Sprint 14 | **zerlegt** | **Klammer**, Termin des letzten Teils. |
| promt-team/T-0001 | dev | Sprint 13 | offen | ⚠ **3. Verschiebung.** Naht für die nächste Berührung benannt: (a) erheben, (b) auswerten. Der Auftraggeber wartet darauf — `promt-team/N-0001`, und *„ohne Baseline kein Optimierungslauf"* ist sein eigener Satz. |
| promt-team/T-0002 | test | Sprint 13 | offen | **2. Verschiebung**, gleicher Grund, gleiches Verfallsdatum. |
| promt-team/T-0003 | dev | Sprint 13 | blocked | `blocked_by` T-0001/T-0002. ⚠ Steht damit wieder auf **demselben** Sprint wie seine Blocker — derselbe stille Widerspruch, den Sprint 11 hier gefunden hat. **Muss in Sprint 13 auf 14 gezogen werden, sobald die Blocker terminiert sind.** |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — **kein offener Brief**, weder beim Start noch beim Abschluss (beide Male geprüft, Lehre aus Sprint 11). |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert (`L-2026-08-17y`, `L-2026-08-17z`). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight, Tests, Matrix — **und ab jetzt die JS-Strecke**. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Widget-Vertrag — dieser Lauf hat den Cockpit-Payload **nicht** verändert, der Vertrag bleibt v2.4. ⚠ Gegen die Regel 5 aus `L-2026-08-17w` ausdrücklich **geprüft**, nicht angenommen. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`) und laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033); genau deshalb nehmen `plan_drift`, `status_drift`,
`sprint_vergangen` und `unterminiert` sie aus.

**Rollenzuweisungen in diesem Sprint (D006).** `projects/p12/T-0004` blieb bei `pl` — es
ist eine Architekturentscheidung mit Gate, kein Bauweg. `platform/T-0013` ist an `cm`
gegangen (Prüfstrecken- und Werkzeugfläche, dieselbe Begründung wie `platform/T-0011` und
`T-0012`). `pm/T-0064` liegt bei `pl` (Ansicht auf den Plan), `pm/T-0065` bei `chg` (es
ändert Ticketfelder) — dieselbe Trennung wie bei `pm/T-0053` / `pm/T-0062` in Sprint 10/11.

## Sprint-Abschluss (Sprint 12, 2026-08-17)

**Geplant beim Start:** 14 offene Sachtickets + 6 Takt-Pflichten, **kein offener Brief**.
Der Beschluss aus Sprint 11 machte die fünf HMI-Tickets zur Arbeit dieses Laufs.

**Im Lauf dazugekommen:** vier Tickets — `projects/p12/T-0007` (DR, Klasse A),
`platform/T-0013` (Nebenläufigkeitsbefund), `pm/T-0064` und `pm/T-0065` (Zerlegung von
`pm/T-0054`).

**Geschlossen:** `projects/p12/T-0004`, `pm/T-0060`, `pm/T-0058`, `pm/T-0039` und die sechs
Takt-Pflichten — **zehn Stück**. Alle vier Sachtickets über den legalen Weg
(`open → in_progress → in_review → done`) mit je drei Commits.

**Verschoben, mit Grund und Verfallsdatum:** neun Sachtickets nach Sprint 13/14, drei
weitere als Klammer nachgezogen (keine Verschiebung). ⚠ **Drei davon sind dritte
Verschiebungen** (`pm/T-0052`, `p11/T-0008`, `promt-team/T-0001`) — bei allen dreien ist
die Zerlegungsnaht **jetzt** benannt, statt sie beim vierten Mal zu suchen.

**Nicht eingelöst:** die Zusage aus Sprint 11 an den Auftraggeber, `p11/T-0008` und
`p11/T-0009` in diesem Lauf zu bauen.

**Verifikation (nach allen Änderungen des Laufs gemessen, nicht davor):**
Preflight **STARTKLAR**, **752 Python-Tests** grün, **16 JS-Tests** grün, Matrix **130
SWRs / 0 Lücken**, unterminiert 0, Kalenderfristen 0, Plan-Drift 0, überfällig 0,
Statusdrift 0, Statusübergänge seit Stichtag 0, Altbestand 52 (unverändert).
Briefkasten: **beim Start kein offener Brief, beim Abschluss erneut geprüft.**
