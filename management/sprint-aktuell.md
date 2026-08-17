# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 17** (2026-08-17, Start 16:49, Kennung
   `2026-08-17T1650-cowork-s17`). ⚠ **Dieser Lauf hat den Sprint nicht eröffnet, sondern
   übernommen.** Die Registerzeile stand um 16:49 in der Datei und war **nicht committet**;
   seit dem Ende von Sprint 16 (17:10) hat **kein** Repo einen Commit bekommen. Der Lauf,
   der die Zeile schrieb, ist zwischen dem Schreiben und seinem ersten Commit abgebrochen.
   > **Ein Lauf, der zwischen Registerzeile und erstem Commit stirbt, hinterlässt einen
   > Sprint, der laufend aussieht und nichts hervorgebracht hat.**

   Die richtige Antwort darauf ist **nicht** eine Übernahme mit neuer Nummer, sondern der
   **idempotente Wiedereintritt**, den `beginne()` seit SWR-136 ausdrücklich vorsieht
   („ein Lauf, der zweimal startet, erhöht den Zähler nicht"). Sprint 17 bleibt Sprint 17.
2. **Planung: 24 offene Tickets aller 17 Repos gesichtet und terminiert.** Sieben Tickets
   trugen noch eine Nummer aus Sprint 16 oder 18 und sind nachgezogen (`platform/T-0016`,
   `pm/T-0028`, `pm/T-0054`, `p11/T-0008`, `p12/T-0005`, `p12/T-0006`,
   `promt-team/T-0003`) — Default nach `pm/D006` ist **dieser** Sprint.
3. **Zwei Tickets stehen bei der VIERTEN Berührung** (`pm/T-0063`, `pm/T-0065`). Beide
   sagen in ihrem eigenen Text, dass sie **keine Naht** haben und eine erfundene Zerlegung
   schlimmer wäre als der Bau. Damit ist die Antwort dieses Sprints eine **Entscheidung**
   und keine vierte Verschiebung.
4. **`platform/T-0016` steht bei der DRITTEN Berührung** und hat seine Naht **benannt**:
   DoD 2 (Payload trägt den Zustand, Backend + Vertrag v2.5) und DoD 3/4 (Ansicht
   umstellen, Zähltest auf 0). Der erste Teil ist ohne den zweiten nutzbar, der zweite
   ohne den ersten nicht.

## Sprint-Plan (Planungsstand, Sprint 17)

*Sprint 17 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0065 | chg | dieser Sprint | geplant | ⚠ **4. Berührung.** Das Ticket sagt selbst: **keine Naht**. Also bauen oder ablehnen — geplant ist **bauen** (Knopf je Zeile setzt `geplant_sprint`, über den vorhandenen HMI-Schreibweg). Klasse B. |
| platform/T-0016 | cm | dieser Sprint | geplant | ⚠ **3. Berührung**, Naht **benannt**. DoD 2 zuerst (Payload trägt den Zustand, Vertrag v2.5), dann DoD 3/4. Altbestand bei 3 eingefroren, bis der Zähltest auf 0 gezogen ist. |
| pm/T-0063 | chg | dieser Sprint | geplant | ⚠ **4. Berührung.** **Klasse A** (Team-Gründung) — die Lieferung ist ein **Charter-Entwurf + Gründungs-DR in die Inbox**, nicht eine Gründung. Wir entscheiden das nicht selbst. |
| projects/p12/T-0009 | pl | dieser Sprint | geplant | Teil b von `T-0005`. `blocked_by: [T-0008]` **erfüllt**. ADR-Delta + die Regel gegen einen zweiten Renderpfad **als Zähltest**. |
| promt-team/T-0007 | test | dieser Sprint | geplant | Goldset-**Fälle** je Rolle. Blocker (`T-0006`, Format) seit Sprint 16 erfüllt. |
| projects/p11/T-0012 | dev | dieser Sprint | geplant | Deep-Links auf `<projekt>/T-xxxx`, nie auf die Nummer allein. Die Gegenprobe (doppelt vorkommende Nummer) ist die Substanz. |
| projects/p11/T-0011 | dev | dieser Sprint | geplant | Widget-Konfiguration mit Persistenz (schreibend). `blocked_by` erfüllt. |
| projects/p11/T-0013 | dev | dieser Sprint | offen | `blocked_by: [T-0012]` — wird mit `T-0012` frei, deshalb **dieser** Sprint und nicht Sprint 18. |
| projects/p12/T-0006 | pl | dieser Sprint | offen | `blocked_by` zieht auf `T-0009` nach; wird mit ihm frei. |
| promt-team/T-0003 | dev | dieser Sprint | blocked | `blocked_by` T-0001 (erfüllt) / T-0002 (Klammer über `T-0007`) — wird mit `T-0007` frei. |
| platform/T-0001 | cm | jeder Sprint | geplant | Takt: Werkzeug- und Plattformpflege, Testlauf, Matrix. |
| pm/T-0001 | pl | jeder Sprint | geplant | Takt: Session-Agenda fortschreiben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten geprüft — **0 offen** (55 Briefe, alle `beantwortet`). |
| pm/T-0003 | coach | jeder Sprint | geplant | Takt: LeLe **sofort** verankern (D005), noch in diesem Lauf. |
| team-dashboard/T-0001 | pl | jeder Sprint | geplant | Takt: Widget-Vertrag — der **Bump auf v2.5** aus der Entscheidung von Sprint 16 ist hier fällig. |
| team-mail/T-0001 | dev | wartet-auf-Mensch | geplant | Takt: Digest — fällig **ab IMAP-Einrichtung**, und die ist eine Handlung des Menschen. |
| pm/T-0028 | chg | Klammer | **zerlegt** | Klammer über `T-0062` (erledigt) / `T-0063`. Termin am letzten Teil nachgezogen. |
| pm/T-0054 | chg | Klammer | **zerlegt** | Klammer über `T-0064` (erledigt) / `T-0065`. Termin am letzten Teil nachgezogen. |
| promt-team/T-0002 | test | Klammer | **zerlegt** | Klammer über `T-0006` (erledigt) / `T-0007`. |
| projects/p11/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0007`–`T-0013`. |
| projects/p11/T-0008 | dev | Klammer | **zerlegt** | Klammer über `T-0010` (erledigt) / `T-0011`. Termin nachgezogen. |
| projects/p11/T-0009 | dev | Klammer | **zerlegt** | Klammer über `T-0012` / `T-0013`. |
| projects/p12/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0004`–`T-0009`. |
| projects/p12/T-0005 | pl | Klammer | **zerlegt** | Klammer über `T-0008` (erledigt) / `T-0009`. Termin nachgezogen. |

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected` und warten auf eine **Handlung des Menschen**. Sie erscheinen seit SWR-138
im Abschnitt „Für dich: Handlungen".
