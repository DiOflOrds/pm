# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 18** (2026-08-17, Start 19:03, Kennung `2026-08-17T1905-cowork-s18`).
   ⚠ **Dieser Lauf hat zuerst eine fremde Buchung nachgetragen.** Sprint 17 hatte seine
   Arbeit um 18:50 abgeschlossen und committet, aber **bewusst kein `ende`** gebucht, weil
   eine zweite Session in denselben Repos arbeitete. Beide Läufe endeten; niemand schloss
   ihn.
   > **Das Register kennt „läuft" und „abgebrochen". Für „fertig, aber aus Rücksicht nicht
   > gebucht" hat es kein Wort — und der automatische Weg wählt dann das falsche.**

   `beginne()` hätte Sprint 17 beim zweiten Anlauf als **`abgebrochen: true`** geschlossen.
   Das wäre eine **falsche Angabe** gewesen: Sprint 17 hat vier Sachtickets geschlossen und
   SWR-144 bis SWR-147 hervorgebracht. Geschlossen wurde er deshalb mit `beende()` **ohne**
   Abbruchmarke und mit einer Notiz, die die **Messung** nennt (Schreibspur unbewegt, alle
   17 Repos clean). Verankert als `L-2026-08-17ay`.
2. **✅ Das seit Sprint 17 dringlichste Sachticket der Organisation ist gebaut**, nicht zum
   zweiten Mal verschoben: `promt-team/T-0007` (**SWR-149**) liefert **51 belegte
   Goldset-Fälle** — CM 23, DEV 28 — und die gemessene Baseline. Damit ist die **Klammer
   `promt-team/T-0002` nach FÜNF Berührungen geschlossen**.
3. **⚠⚠ Und der Befund dieses Tickets war einer an seiner eigenen DoD.** Sie verlangt
   wörtlich *„real heißt: aus dem Bestand belegt, nicht ausgedacht"* — und dieser Satz stand
   seit Sprint 15 **nur im Ticket**.
   > **Keine Prüfung liest einen Satz. Ein Lauf hätte 51 plausibel formulierte Fälle
   > schreiben und die DoD als erfüllt melden können — und nichts hätte widersprochen.**

   Gebaut ist `herkunft` als **Pflichtfeld mit Belegstelle**, gegen den Bestand aufgelöst.
   ⚠ Die **Stelle** ist die eigentliche Prüfung: *eine Datei existiert auch für einen
   erfundenen Fall.* Alle 51 Fälle belegen sich mit einer Stelle — zugesichert.
4. **⚠⚠ Eine Messung, die die DoD NICHT verlangt hat, hat die eigene Arbeit dieses Laufs
   widerlegt.** Die **Trennschärfe**: von 46 textbasierten Prüfungen des ersten Entwurfs
   gingen **41** auch in **fremden** Artefakten des Sets auf.
   > **Eine Prüfung, deren Suchtext überall steht, geht auf, ohne etwas zu unterscheiden.
   > Ein Goldset aus solchen Prüfungen ist kein Maßstab, sondern ein Maß für die
   > Beliebigkeit seiner Suchtexte — und es war grün.**

   Geschärft auf **2 von 40**, **vor dem ersten Commit**. Die Zahl wird **berichtet und
   nicht erzwungen**: eine Prüfung über eine **Konvention** soll überall aufgehen.
5. **⚠⚠ Der Bericht sagt VOR seiner Tabelle, dass seine hohe Quote KEIN gutes Zeugnis ist.**
   Die Prüfausdrücke sind aus den Artefakten **abgeleitet**; dass sie dort aufgehen, ist zum
   Teil **Bauart und nicht Befund**. Was fehlt, ist **benannt statt geschätzt**: die
   Erfolgsquote eines **frischen** Laufs je Rolle. Sie braucht einen Provider, kostet Geld
   und ist **Klasse A** → `promt-team/T-0009` liegt als Inbox-DR beim Menschen.
6. **✅ `projects/p11/T-0012` bei der ZWEITEN Verschiebung gebaut** (**SWR-150**). ⚠ Der
   Befund war nicht der fehlende Link, sondern der **zweite Bauplatz**: **neun** Stellen in
   `app.js` setzten die Route selbst zusammen, und in **sieben** davon war die Beschriftung
   `x.ref` — die Kennung **vom Server**.
   > **Ein Link, dessen Aufschrift der Server liefert und dessen Ziel die Ansicht
   > zusammenbaut, ist zwei Aussagen über dasselbe Ticket. Solange beide gleich sind, merkt
   > es niemand.**

   Und sie sind nicht theoretisch verschieden: **68 Ticketnummern gibt es in mehr als einem
   Projekt**, `T-0002` allein in **17** — gemessen. Eine nackte Nummer ergibt jetzt
   **keinen** Link.
7. **✅ `projects/p12/T-0009` liefert ADR-P12-001** — die Regel gegen den zweiten Renderpfad
   als **Zähltest** und nicht als Vorsatz. Damit ist auch die **Klammer `p12/T-0005`**
   geschlossen, und `SWR-097`–`SWR-100` haben zum ersten Mal **Prüfungen**.
   ⚠ Der Bestand liefert den Beweis selbst: `tlinks(String(text).replace(/\*\*/g, ""), …)` —
   *ein Aufrufer, der Markup wegwirft, damit der Renderer nicht daran scheitert, hat die
   Lücke repariert statt sie zu melden.*
8. **⚠ Zwei Zähltests dieses Laufs halten bewusst den HEUTIGEN Zustand fest** („der
   Inline-Pass kennt die Ticketnummer heute **nicht**"). Sie werden rot, sobald `p12/T-0006`
   baut — **und das ist ihr Zweck**: sie sagen dem Lauf, der es tut, dass er den Altbestand
   mitzunehmen hat, statt dieselbe Erkennung zweimal stehen zu lassen.
   > **Ein Altbestand, der als Warnung dasteht, wächst. Einer, der als Zahl dasteht, kann
   > nur sinken.**
9. **⚠ Eine Zusicherung dieses Laufs ist an ihrem eigenen Kommentar rot geworden.** Der
   Zähltest über das Routenpräfix suchte dateiweit und fand das **Beispiel in der Erklärung
   darüber**. *Eine Textsuche kann eine Erklärung nicht von ihrem Gegenstand unterscheiden —
   und die Erklärung steht nun einmal genau dort, wo der Gegenstand ist.* **Fünfter
   Fehlalarm derselben Art in zwei Tagen.** Gemessen wird jetzt die **Zuweisung im Code**.
10. **1069 Python-Tests, davon 1 rot** (der Altbefund über drei unzulässige Übergänge aus
    den Sprints 13 und 15 — **keiner aus diesem Lauf**), **78 JS-Tests grün** (von 73),
    Matrix **150 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs
    **0**. ⚠ **Nicht startklar**, und das bleibt die richtige Meldung.

## Sprint-Plan (Abschlussstand)

*Sprint 18 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 19; ab Sprint 20 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| promt-team/T-0007 | test | dieser Sprint | **erledigt** | ✅ **SWR-149.** 51 belegte Fälle (CM 23, DEV 28), Format **v2** mit auflösbarer Herkunft, gemessene Baseline. ⚠ Die Trennschärfe hat den ersten Entwurf widerlegt (41 von 46) und ihn vor dem Commit auf 2 von 40 geschärft. |
| projects/p11/T-0012 | dev | dieser Sprint | **erledigt** | ✅ **SWR-150.** 2. Verschiebung eingelöst statt einer dritten. **Ein** Bauplatz statt neun; nackte Nummer ergibt keinen Link. |
| projects/p12/T-0009 | pl | dieser Sprint | **erledigt** | ✅ **ADR-P12-001.** Die Regel gegen den zweiten Renderpfad ist eine **Prüfung**: Altbestand `tlinks`-Aufrufe eingefroren bei **4**. SWR-097–100 haben Tests. |
| promt-team/T-0002 | test | Klammer | **erledigt** | ✅ Klammer nach **fünf** Berührungen geschlossen (`T-0006` + `T-0007`). |
| projects/p12/T-0005 | pl | Klammer | **erledigt** | ✅ Klammer geschlossen (`T-0008` + `T-0009`). |
| pm/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten **zweimal** geprüft, beide Male **0 offen**. |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: **fünf** Lessons SOFORT verankert (`L-2026-08-17au` bis `ay`), verteilt auf test/cm. |
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: 1069 Python-Tests (1 rot, Altbefund), 78 JS-Tests grün, Matrix 150/0. ⚠ Die Suite läuft in **Blöcken** — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag unverändert bei **v2.6** — dieser Lauf hat keine Vertragsfläche berührt. |
| team-mail/T-0001 | dev | jeder Sprint | offen | ⚠ Der Digest für den 17.08. fehlt weiter. Diese Sandbox hat die Zugangsdaten nicht (Datenklasse `geheim`); die Rückfrage steht seit Sprint 17 in `team-mail/N-0003` und ist **nicht** beantwortet. **Kein „wartet auf dich"** — es wartet auf eine Umgebung mit Zugangsdaten. |
| promt-team/T-0009 | pl | **beim Menschen** | offen | ⚠ **Neu, Inbox-DR (Klasse A).** Wie messen wir die Erfolgsquote eines **frischen** Rollenlaufs, wenn sie Geld kostet? Optionen A/B/C, Frist **2026-08-19**, Default **A** (Ollama, 0 €). |
| promt-team/T-0003 | dev | Sprint 19 | blocked | ⚠ `blocked_by` **ausgetauscht statt geleert**: `T-0001`/`T-0002` sind erfüllt, aber es fehlt die eine Zahl aus S0. Steht jetzt auf **`T-0009`** — der Wartegrund ist ein **Feld** und kein Fließtext. |
| projects/p11/T-0011 | dev | Sprint 19 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Bei der **vierten** greift `L-2026-08-17x`: dann wird gebaut, nicht zerlegt — es hat **keine Naht**, und das steht im Ticket. |
| projects/p11/T-0013 | dev | Sprint 19 | offen | `blocked_by: [T-0012]` ist mit SWR-150 **erfüllt** — ab Sprint 19 terminiert, nicht blockiert. ⚠ Ein PIN-Lesegate ist eine **Zugriffsentscheidung** (B025). |
| projects/p11/T-0014 | pl | Sprint 19 | offen | ⚠ **1. Terminierung.** Eine **Entscheidung**, kein Bau. Diesen Lauf **nicht** stillschweigend entschieden: einen Endpunkt ohne Leser abzuräumen wäre eine Entscheidung ohne Entscheider. |
| projects/p12/T-0006 | pl | Sprint 19 | offen | ⚠ **1. Verschiebung**, `blocked_by` mit ADR-P12-001 **erfüllt**. Die Vorlage ist vollständig — **und die Zusage ist eine Zahl**: `ALTBESTAND_TLINKS_AUFRUFE` muss von **4** auf **0**. |
| platform/T-0020 | cm | Sprint 19 | offen | ⚠ **1. Verschiebung**, Grund im Ticket: **drei Fragen vor dem Bauen**. Dieser Lauf hat die erste beantwortet — der eingefrorene Zähler ist zweimal angewandt statt behauptet. |
| promt-team/T-0008 | test | Sprint 20 | offen | ⚠ **Neu**: Goldset für die **übrigen zehn** aktiven Rollen. Die Lücke ist **benannt** und nicht stiller Rest. ⚠ Sprint 20, weil es Läufe braucht, die es selbst nicht erzeugt. |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0014` — folgt ihrem letzten Teil (Sprint 19). |
| projects/p11/T-0008 | dev | Klammer | nachgezogen | Klammer über `T-0010` (done) / `T-0011`. |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Klammer über `T-0012` (**done**) / `T-0013`. |
| projects/p12/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0004`–`T-0009`; offen ist nur noch `T-0006`. |

⚠ **Eine Klammer zählt nicht als verschoben.** Sie war nie an der Reihe — sie wartet auf
ihren letzten Teil. Die Verschiebungszählung läuft an den **Teilen** (`L-2026-08-17x`).

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected` und warten auf eine **Handlung des Menschen**. Sie erscheinen seit SWR-138 im
Abschnitt „Für dich: Handlungen".

## Sprint-Abschluss (Sprint 18, 2026-08-17)

**Geschlossen:** `promt-team/T-0007`, `projects/p11/T-0012`, `projects/p12/T-0009` — **drei
Sachtickets**, dazu die **zwei** Klammern `promt-team/T-0002` (nach fünf Berührungen) und
`p12/T-0005`, sowie **fünf** Takt-Pflichten.

**Im Lauf dazugekommen:** `promt-team/T-0008` (die zehn übrigen Rollen, benannte Lücke) und
`promt-team/T-0009` (**Inbox-DR, Klasse A**).

**Neue Anforderungen:** **SWR-149** und **SWR-150** — zwei. Dazu **ADR-P12-001**, das
`SWR-097`–`SWR-100` zum ersten Mal Prüfungen gibt.

**Verifikation:** **1069 Python-Tests, 1068 grün / 1 rot** (der Altbefund über drei
unzulässige Übergänge — **keiner aus diesem Lauf**), **78 JS-Tests grün** (von 73), Matrix
**150 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs **0**,
Plan-Drift 0, Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: zwei aus Sprint 13 (`platform/T-0014`, `pm/T-0064`) und
einer aus Sprint 15 (`pm/T-0052`), **alle unverändert**. Nichts geglättet, kein Test
angepasst, um grün zu werden.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Sprint 17 hat einen Werkzeugfehler **ausgelöst** (SWR-145). Sprint 18 hat etwas anderes
getan: er hat eine **Messung gebaut, die seine eigene Arbeit widerlegt hat**.

> **Das Goldset war mangelfrei, belegt, vollständig — und seine Prüfungen unterschieden
> nichts. Ohne die Trennschärfe wäre es als Maßstab in den Bestand gegangen, und das
> Eval-Gate hätte darauf gemessen.**

Dazu zwei Zusicherungen, die ihre Verfasser korrigiert haben: der Präfix-Zähltest an seinem
eigenen Kommentar (fünfter Fehlalarm derselben Art), und die Board-Validierung, die das
Frontmatter des neuen Inbox-DR beim ersten Wurf zu Recht abgelehnt hat (`frist` kein Datum,
`default` kein Token aus `optionen`).

⚠ Die Erkennungsfrage aus Sprint 16 — *welche unserer inzwischen über 1000 Zusicherungen
prüfen etwas, das die Testdatei selbst eingerichtet hat?* — bleibt **unbeantwortet** und
steht weiter in `L-2026-08-17ai`. Dieser Lauf hat sie **nicht** beantwortet; er hat aber in
allen neuen Zusicherungen gegen den **wirklichen** Bestand gemessen statt gegen Attrappen,
und das ist an `_WURZEL` in den drei neuen Testdateien nachzählbar.

### Was in Sprint 19 zuerst kommt

1. **`projects/p12/T-0006`** — die Umstellung auf **einen** Renderweg. Die Vorlage ist
   vollständig, und die Zusage ist eine Zahl: `ALTBESTAND_TLINKS_AUFRUFE` von 4 auf 0.
2. **`projects/p11/T-0011`** — **dritte** Verschiebung hinter sich; bei der vierten greift
   `L-2026-08-17x`, und das Ticket sagt im Voraus, dass es keine Naht hat.
3. **`projects/p11/T-0013`** — Blocker mit SWR-150 erfüllt, und es schließt die Klammer
   `p11/T-0009`.
4. **`promt-team/T-0009`** verbuchen, sobald die Antwort da ist — daran hängt der
   Erstauftrag des promt-teams.
