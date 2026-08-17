# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 16** (2026-08-17, Start 15:41, Kennung
   `2026-08-17T1541-cowork-s16`). **Ein** Lauf. ⚠ Und die Eröffnung ist die **erste
   Anwendung von SWR-136 im Regelfall**: `beginne()` hat nachgesehen, ob ein Sprint ohne
   `ende` läuft, keinen gefunden und eröffnet. Sprint 15 hatte sich selbst beendet.
2. **Briefkasten bei Sprintbeginn: 0 offen** (57 Briefe in 6 Briefkästen geprüft).
3. **Alle 24 nicht abgeschlossenen Tickets aller 17 Repos sind terminiert** — kein Ticket
   ohne Termin. ⚠ Vier weitere Tickets stehen auf `rejected` (`p0/T-0008`, `p0/T-0047`,
   `p0/T-0072`, `p1/T-0018`); `rejected` ist ein **Endzustand** (die Übergangsmatrix führt
   von dort nur nach `open` zurück), sie sind deshalb keine offene Arbeit und stehen
   trotzdem unten, damit die Zahl nachvollziehbar bleibt.

## Sprint-Plan (Planning-Stand 15:45, Fortschreibung im Lauf)

*Sprint 16 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 17; ab Sprint 18 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier. Diese Tabelle ist die
Sicht, das Ticket ist der Ort (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0017 | cm | **dieser Sprint (zuerst)** | geplant | ⚠⚠ **Die Reparatur des Buchungsfehlers aus Sprint 15.** Statuswechsel und Commit als **ein** Vorgang, inkl. Nebenbefund an SWR-134 (Räumung **zwischen** `add` und `commit`). Dringlichkeit **gemessen**: zweimal in einem Lauf eingetreten. |
| promt-team/T-0006 | test | dieser Sprint | geplant | Teil a von `T-0002`. Goldset-**Format**; Gegenprobe: ein Fall ohne `fehlschlag_erkannt_an` wird **abgelehnt**, nicht vorbelegt. |
| promt-team/T-0005 | dev | dieser Sprint | geplant | Teil b von `T-0001`. Erhebung an der Quelle **und** Auswertung — die Baseline, auf die der Auftraggeber seit `promt-team/N-0001` wartet. |
| projects/p11/T-0012 | dev | dieser Sprint | geplant | Teil a von `T-0009`. Deep-Links auf `<projekt>/T-xxxx`, Kennung **vom Server**; Gegenprobe mit doppelt vorkommender Nummer. |
| projects/p11/T-0011 | dev | dieser Sprint | geplant | `blocked_by: [T-0010]` seit Sprint 14 **erfüllt**. ⚠ Persistenz ist hier das **Gegenteil** von SWR-133 — der Unterschied ist zu begründen, nicht zu behaupten. |
| pm/T-0065 | chg | dieser Sprint | geplant | `blocked_by: [T-0064]` **erfüllt**. **3. Verschiebung, wenn es nicht fällt.** ⚠ Im Ticket steht ausdrücklich, dass es **keine** Naht hat. |
| pm/T-0063 | chg | dieser Sprint | geplant | `blocked_by: [T-0062]` **erfüllt**. ⚠ **Klasse A** (Team-Gründung): das Ergebnis ist eine **Vorlage an den Menschen**, keine Gründung. |
| projects/p12/T-0005 | pl | dieser Sprint | geplant | **4. Verschiebung, wenn es nicht fällt.** `blocked_by: [T-0004]` seit Sprint 12 erfüllt; der Vollständigkeitsnachweis (SWR-099) ist seit der Teststrecke führbar. |
| platform/T-0016 | cm | dieser Sprint (Teil 1) | geplant | ⚠ **Blockiert, nicht verschoben** — und `blocked_by` kann es nicht sagen (repo-übergreifend, Befund Sprint 15). In diesem Sprint fällt **die Vertragsfrage** an `team-dashboard/T-0001` (B066, Versions-Bump); der Code folgt erst danach. |
| promt-team/T-0007 | test | Sprint 17 | offen | Teil b von `T-0002`, `blocked_by: [T-0006]` — **echt blockiert**, deshalb auf den Sprint nach dem Blocker. |
| projects/p11/T-0013 | dev | Sprint 17 | offen | Teil b von `T-0009`, `blocked_by: [T-0012]` — echt blockiert. PIN-Lesegate am **Endpunkt**, nicht in der Ansicht. |
| projects/p12/T-0006 | pl | Sprint 17 | offen | `blocked_by: [T-0005]` — echt blockiert. |
| promt-team/T-0003 | dev | Sprint 18 | blocked | `blocked_by: [T-0001, T-0002]` — hinter den letzten Teilen beider Zerlegungen. |
| promt-team/T-0001 | dev | Klammer | **zerlegt** | Klammer über `T-0004` (erledigt) / `T-0005`. Kein eigener Arbeitsanteil; trägt den Termin des letzten Teils. |
| promt-team/T-0002 | test | Klammer | **zerlegt** | Klammer über `T-0006` / `T-0007`. |
| pm/T-0028 | chg | Klammer | **zerlegt** | Klammer über `T-0062` (erledigt) / `T-0063`. |
| pm/T-0054 | chg | Klammer | **zerlegt** | Klammer über `T-0064` (erledigt) / `T-0065`. |
| projects/p11/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0007`–`T-0013`. |
| projects/p11/T-0008 | dev | Klammer | **zerlegt** | Klammer über `T-0010` (erledigt) / `T-0011`. |
| projects/p11/T-0009 | dev | Klammer | **zerlegt** | Klammer über `T-0012` / `T-0013`. |
| projects/p12/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0004`–`T-0006`. |
| pm/T-0001 | pl | jeder Sprint | Takt | Session-Agenda fortschreiben. |
| pm/T-0002 | pl | jeder Sprint | Takt | Briefkasten prüfen — Start **und** Abschluss (SWR-131). |
| pm/T-0003 | coach | jeder Sprint | Takt | Lessons **sofort** verankern (D005), nicht am Sprintende sammeln. |
| platform/T-0001 | cm | jeder Sprint | Takt | Preflight, Python-Tests, JS-Tests, Trace-Matrix. |
| team-dashboard/T-0001 | pl | jeder Sprint | Takt | Widget-Vertrag — ⚠ **offen bei diesem Takt**: die Vertragsfrage aus `platform/T-0016`. |
| team-mail/T-0001 | dev | jeder Sprint | Takt | Digest — fällig ab IMAP-Einrichtung, die aussteht. |

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected`. Alle vier warten auf eine **Handlung des Menschen** und keine davon ist von
uns terminierbar — sie tauchen seit SWR-138 im Abschnitt „Für dich: Handlungen" auf.

## Sprint-Abschluss (Sprint 16)

*Wird am Ende dieses Laufs gefüllt.*
