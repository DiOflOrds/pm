# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 16** (2026-08-17, Start 15:41, Kennung
   `2026-08-17T1541-cowork-s16`). **Ein** Lauf. Die Eröffnung ist die **erste Anwendung
   von SWR-136 im Regelfall**: `beginne()` hat nachgesehen, ob ein Sprint ohne `ende`
   läuft, keinen gefunden und eröffnet.
2. **✅ Die dringlichste Aufgabe ist erledigt: `platform/T-0017` (SWR-139) — ein
   Zustandswechsel ist EIN Vorgang.** `setze_status` schreibt **und** bucht; scheitert die
   Buchung, werden Ticketdatei **und** `BOARD.md` byteweise zurückgesetzt und der Fehler
   geworfen. Kein zweiter Wechsel auf einem unverbuchten Stand.
3. **✅✅ Und die Vorkehrung hat in DIESEM Lauf real gegriffen.** Bei `p12/T-0008` scheiterte
   eine Buchung an einer Sperre: der Wechsel wurde **zurückgenommen**, der Folgeschritt
   korrekt abgewiesen („unzulässiger Übergang"), nichts ging verloren.
   > **Der Unterschied zu Sprint 15 war diesmal keine Aufmerksamkeit, sondern eine
   > Vorkehrung — und sie ist zweimal an einem echten Fall eingetreten.**
4. **⚠⚠ Ein Fehler von SWR-134, gemessen IN PRODUKTION während des Laufs** (`platform/T-0018`,
   SWR-143): `entsperre` legte `backend/` statt `scripts/` in den Pfad, `import preflight`
   scheiterte, die Räumung lief **gar nicht** — außer der Aufrufer brachte den Pfad mit.
   > **Die Reparatur wirkte überall dort, wo der Aufrufer sie mitgebracht hat — also genau
   > dort nicht, wo SWR-134 sie hinbringen wollte.**

   ⚠ Der Fehlermodus ist der schlimmste dieser Bauart: **unsichtbar in der Teststrecke**
   (die Testdatei legt `scripts/` selbst in den Pfad) und sichtbar nur unter Last.
5. **✅ Die Baseline, auf die der Auftraggeber seit `promt-team/N-0001` wartet, ist
   gemessen — und sie ist leer** (`promt-team/T-0005`, SWR-140/141). 7 Läufe, **0** mit
   Token, **6 von 7** nicht zuordenbar. Der eine zuordenbare Lauf lief über **Ollama**.
   > **Ein Mittel über die Läufe, die zufällig gemeldet haben, ist kein Mittel über die
   > Läufe. Ohne seinen Nenner gedruckt ist es von einer vollständigen Messung nicht zu
   > unterscheiden.**

   Jede Zahl trägt deshalb `n_gemessen` **und** `n_gesamt`.
6. **✅ Die Token-Messung an der Quelle ist gebaut, ohne zu schätzen** (SWR-141). Ollama
   meldet **eine** Zahl, der Vertrag verlangt **zwei** — gelöst mit einer zweiten Messung
   ohne Erzeugung (`num_predict: 0`) und einer Subtraktion. ⚠ Fehlt **eine** der beiden,
   bleiben **beide** Felder leer.
7. **✅ Goldset-Format** (`promt-team/T-0006`, SWR-142): `fehlschlag_erkannt_an` als
   **strukturierte** Prüfung; ein Fall ohne sie wird **abgelehnt**, nicht vorbelegt.
8. **✅ Die Vertragsfrage aus `platform/T-0016` ist beantwortet** — die Blockade, die
   `blocked_by` in Sprint 15 nicht ausdrücken konnte. Entscheidung des Eigentümers
   (`team-dashboard/T-0001`, Klasse C): **Weg A**, der Payload trägt den Zustand, v2.5.
   > **Ein Ticket gegen B033 zu lösen, indem man einen neuen B033-Fall anlegt, ist keine
   > Lösung, sondern eine Verschiebung mit besserer Presse.**
9. **✅ `p12/T-0005` bei der VIERTEN Berührung zerlegt, Teil a gebaut** (`T-0008`): der
   Vollständigkeitsnachweis nach SWR-099 gegen **57 Briefe**, gegen den **echten** Renderer
   aus `app.js`. Ergebnis: **kein Nutzzeichen geht verloren.** ⚠ Die Naht stand **nicht**
   im Ticket und ist beim Schneiden hergeleitet — die Herleitung steht in `T-0008`.
10. **⚠⚠ Der erste rote Lauf dieses Nachweises war ein Fehler der MESSUNG, nicht des
    Renderers.** Er meldete an sieben Briefen fehlende Ziffern — die Marken der
    Nummernlisten.
    > **Was als „Markup" gilt, ist eine Entscheidung der Messung, und eine unsaubere macht
    > ein richtiges System rot.**

    Korrigiert wurde die **Ebene** (Zeilenstruktur statt Zeichenklasse), beide Richtungen
    eigens zugesichert.
11. **⚠ Drei bestehende Zusicherungen wurden von SWR-139 rot — und sie waren NICHT der Fall
    aus SWR-136.** Ihre Regel („nicht vorsorglich räumen") war **richtig** und nur zu weit
    gezogen. Verschärft statt gelöscht: gemessen wird ab jetzt die **Reihenfolge** und die
    **Wiederholung**, nicht die Abwesenheit. Der Unterschied steht in `L-2026-08-17aj`.
12. **⚠ Ein Zähltest wurde von seinem eigenen Gegenstand rot:** die Prüfung „kein
    Vorgabewert auf dem Weg" war eine **Textsuche** und fand sich im Kommentar, der genau
    diesen Fehler erklärt.
    > **Eine Textsuche kann eine Warnung nicht von ihrem Gegenstand unterscheiden.**
13. **⚠ Beinahe-Vorfall beim Bauen:** der erste Entwurf von SWR-139 schrieb eine **zweite**
    `status_in_head` unter demselben Namen. Python meldet das nicht; gefunden hat es
    `test_board.VerschachteltesRepoUebergangTest`.
    > **Eine zweite Antwort auf dieselbe Frage muss nicht widersprechen, um zu schaden —
    > es genügt, dass sie weniger weiß als die erste.**
14. **936 Python-Tests, davon 1 rot** (der Altbefund der drei unzulässigen Übergänge,
    **unverändert** — keiner davon aus diesem Lauf), **51 JS-Tests grün** (+6), Matrix
    **143 SWRs / 0 Lücken**, Briefkasten **0 offen** (Start und Abschluss).
    ⚠ **Nicht startklar**, und das ist die richtige Meldung: die drei Übergänge aus den
    Sprints 13 und 15 stehen unverändert da. **Kein Stichtag verschoben, keine Historie
    umgeschrieben, kein Test angepasst.**

## Sprint-Plan (Abschlussstand)

*Sprint 16 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 17; ab Sprint 18 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0017 | cm | dieser Sprint | **erledigt** | ✅ **SWR-139.** Ein Vorgang, Rücknahme bei gescheiterter Buchung (byteweise zugesichert), Verweigerung auf unverbuchtem Stand, Preflight als Leser. 15 Zusicherungen. ⚠ Zweimal in diesem Lauf real eingetreten und gehalten. |
| platform/T-0018 | cm | dieser Sprint | **erledigt** | ✅ **SWR-143, NEU aus einem Produktionsfehler dieses Laufs.** Die Räumung fand `preflight` nur, wenn der Aufrufer ihn mitbrachte. ⚠ In der Teststrecke unsichtbar. |
| promt-team/T-0005 | dev | dieser Sprint | **erledigt** | ✅ **SWR-140/141.** Auswertung **mit Abdeckung**, Token-Messung an der Quelle ohne Schätzung. 22 Zusicherungen. ⚠ Liefert die **benannte Lücke** statt einer Null. |
| promt-team/T-0001 | dev | dieser Sprint | **erledigt** | ✅ **Klammer geschlossen** (T-0004 + T-0005). Fünfmal berührt, in Sprint 15 zerlegt, hier geschlossen. |
| promt-team/T-0006 | test | dieser Sprint | **erledigt** | ✅ **SWR-142.** Goldset-Format, 15 Zusicherungen. ⚠ Die Gegenprobe (Ablehnung statt Vorbelegung) ist der Kern. |
| projects/p12/T-0008 | pl | dieser Sprint | **erledigt** | ✅ **SWR-099-Nachweis** über 57 Briefe gegen den **echten** Renderer. Kein Nutzzeichen verloren. ⚠ Der erste rote Lauf war ein Fehler der Messung. |
| projects/p12/T-0005 | pl | Klammer | **zerlegt** | ⚠ **4. Berührung, `L-2026-08-17x` angewandt.** Naht **hergeleitet**, nicht vorgefunden — die Herleitung steht in `T-0008`. Termin zieht auf Sprint 17 nach. |
| platform/T-0016 | cm | **Teil 1 erledigt** | offen | ✅ DoD 1: Vertragsfrage beantwortet (Weg A, v2.5). ⚠ **DoD 2–4 auf Sprint 17, 2. Verschiebung**, Naht im Ticket **benannt**. Altbestand bleibt bei 3 eingefroren. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag — die offene Vertragsfrage aus Sprint 15 ist **entschieden** (Klasse C, Weg A). |
| projects/p12/T-0009 | pl | Sprint 17 | offen | **Neu**, Teil b von `T-0005`. `blocked_by: [T-0008]`. ADR-Delta + die Regel gegen einen zweiten Renderpfad **als Zähltest**, nicht als Vorsatz. |
| pm/T-0063 | chg | Sprint 17 | offen | ⚠ **3. Verschiebung**, Grund im Ticket (Kapazität, nachzählbar). **Klasse A.** ⚠ Im Ticket steht, dass DoD 4 (ein Commit) eine Zerlegung entlang 1/2 **verbietet** — damit der nächste Lauf nicht danach sucht. |
| pm/T-0065 | chg | Sprint 17 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Es hat **keine** Naht; bei der vierten Berührung ist die Antwort eine Entscheidung, keine erfundene Zerlegung. |
| projects/p11/T-0011 | dev | Sprint 17 | offen | ⚠ **1. Verschiebung.** `blocked_by` erfüllt — terminiert, nicht blockiert. |
| projects/p11/T-0012 | dev | Sprint 17 | offen | ⚠ **1. Verschiebung.** Die Gegenprobe (doppelt vorkommende Ticketnummer) ist die Substanz. |
| promt-team/T-0007 | test | Sprint 17 | offen | `blocked_by: [T-0006]` **erfüllt** — terminiert, nicht blockiert. |
| projects/p11/T-0013 | dev | Sprint 17 | offen | `blocked_by: [T-0012]` — **echt blockiert**. |
| projects/p12/T-0006 | pl | Sprint 18 | offen | `blocked_by: [T-0005]`; der Blocker ist jetzt `T-0009` — nachgezogen hinter den letzten Teil. |
| promt-team/T-0003 | dev | Sprint 18 | blocked | `blocked_by` T-0001 (erfüllt) / T-0002 (offen). |
| promt-team/T-0002 | test | Klammer | **zerlegt** | Klammer über `T-0006` (erledigt) / `T-0007`. |
| pm/T-0028 | chg | Klammer | **zerlegt** | Klammer über `T-0062` (erledigt) / `T-0063`. |
| pm/T-0054 | chg | Klammer | **zerlegt** | Klammer über `T-0064` (erledigt) / `T-0065`. |
| projects/p11/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0007`–`T-0013`. |
| projects/p11/T-0008 | dev | Klammer | **zerlegt** | Klammer über `T-0010` (erledigt) / `T-0011`. |
| projects/p11/T-0009 | dev | Klammer | **zerlegt** | Klammer über `T-0012` / `T-0013`. |
| projects/p12/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0004`–`T-0009`. |
| pm/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten **zweimal** geprüft, beide Male **0 offen**. |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: `L-2026-08-17ai/aj/ak` **sofort** verankert. |
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: 936 Python-Tests (1 rot, Altbefund), 51 JS-Tests grün, Matrix 143/0. ⚠ Die Suite musste erneut in Blöcken laufen — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. |
| team-mail/T-0001 | dev | jeder Sprint | geplant | Takt: Digest — fällig ab IMAP-Einrichtung, die aussteht. |

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected` und warten auf eine **Handlung des Menschen**. Sie erscheinen seit SWR-138
im Abschnitt „Für dich: Handlungen".

## Sprint-Abschluss (Sprint 16, 2026-08-17)

**Geschlossen:** `platform/T-0017`, `platform/T-0018`, `promt-team/T-0005`,
`promt-team/T-0006`, `promt-team/T-0001` (Klammer), `projects/p12/T-0008` — **sechs
Sachtickets**, dazu DoD 1 von `platform/T-0016` und fünf Takt-Pflichten.

**Zerlegt:** `projects/p12/T-0005` bei der **vierten** Berührung.

**Im Lauf dazugekommen:** `platform/T-0018`, `projects/p12/T-0008`, `projects/p12/T-0009`
(drei, davon eines aus einem **Produktionsfehler dieses Laufs**).

**Neue Anforderungen:** **SWR-139** bis **SWR-143** — fünf.

**Verifikation:** **936 Python-Tests, 935 grün / 1 rot** (der Altbefund über die drei
unzulässigen Übergänge — **keiner aus diesem Lauf**), **51 JS-Tests grün** (von 45), Matrix
**143 SWRs / 0 Lücken**, Briefkasten **0 offen** (Start und Abschluss), entschiedene
unverbuchte DRs **0**, Plan-Drift 0, Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: zwei aus Sprint 13 (`platform/T-0014`, `pm/T-0064`) und
einer aus Sprint 15 (`pm/T-0052`), **alle unverändert**. Nichts geglättet.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Sprint 15 hat den Buchungsfehler zweimal gemacht und einmal gerettet — *durch
Aufmerksamkeit*. Sprint 16 hat die Vorkehrung gebaut, und sie ist im selben Lauf **zweimal
eingetreten**: bei `p12/T-0008` scheiterte die Buchung, der Wechsel wurde zurückgenommen,
der Folgeschritt korrekt abgewiesen.

> **Eine Vorkehrung, die im Lauf ihrer Entstehung greift, ist der einzige Beleg, den es
> für sie gibt.**

Und im selben Lauf hat sich gezeigt, wie leicht das Gegenteil passiert: SWR-143 ist ein
Fehler, der **einen ganzen Sprint lang grün getestet wurde**, weil die Testdatei die
Bedingung selbst herstellte, die sie prüfen sollte. Die Erkennungsfrage —
*welche unserer rund 936 Zusicherungen prüfen etwas, das die Testdatei selbst eingerichtet
hat?* — ist **unbeantwortet** und steht so in `L-2026-08-17ai`.

### Was in Sprint 17 zuerst kommt

1. **`platform/T-0016` DoD 2–4** — die Entscheidung liegt vor, die Umsetzung ist die
   zweite Verschiebung, und die Naht ist benannt.
2. **`pm/T-0063` und `pm/T-0065`** — beide bei der **dritten** Verschiebung; bei der
   vierten greift `L-2026-08-17x`, und beide Tickets sagen im Voraus, dass eine Zerlegung
   dort nicht die richtige Antwort wäre.
3. **`promt-team/T-0007`** (Goldset-Fälle) — der Blocker ist seit diesem Lauf erfüllt.
