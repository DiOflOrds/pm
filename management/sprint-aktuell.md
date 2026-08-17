# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 5** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **⚠ Der Auto-Wächter am Host lief seit dem 17.08. bei JEDEM Lauf ins Leere** — alle
   15 Minuten, rund zweihundert Mal. `board.py` starb im `board-check` von `pm` an einer
   Kodierung; `abschluss.cmd` kam nie bis zum Push. Behoben: **`platform/T-0007`**.
3. **Damit ist die Begründung der letzten drei Sprints widerlegt.** „Der Beleg kommt von
   selbst" war falsch: er konnte nicht kommen. Der Beweis lag in `abschluss-auto.log` im
   Arbeitsordner — und `PUSH-ANFORDERUNG.txt` mit **zwei** Zeilen war das Signal, das die
   Organisation sich am 16.08. selbst aufgeschrieben hatte.
4. **`p11/T-0005` ist erledigt** — und der Layout-Entwurf hat die Frage umgedreht: nicht
   die Kachelzahl sprengt das Budget, sondern **ein Feld** (`letzte_baseline`, bis zu
   300 Zeichen, ohne Grenze im Vertrag).
5. **492 Tests grün** (+6), Matrix **108 SWRs / 0 Lücken**, Preflight STARTKLAR, **kein
   offener Brief** (48), unterminiert 0, überfällig 0.

## Sprint-Plan

*Sprint 5 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 6 (HORIZONT 2); ab Sprint 7 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0007 | cm | dieser Sprint | **erledigt** | **Nicht geplant gewesen — im Startcheck gefunden.** Git-Ausgabe wird fest als UTF-8 gelesen (33 Aufrufstellen, 15 Dateien); ein Lesefehler wird ein **Befund** statt eines Absturzes. 6 Tests, Suite 486 → 492. |
| projects/p11/T-0005 | pl | dieser Sprint | **erledigt** | Layout-Entwurf `architecture/layout-entwurf-fhd.md`. 7 Spalten × 3 Reihen passen — aber nur außerhalb des 62rem-Korridors. DR `p11/T-0006` vorgelegt. |
| projects/p11/T-0006 | pl | dieser Sprint | **vorgelegt** | **Neu.** DR an den Auftraggeber: Dashboard verlässt den Textkorridor (LAY-a/b/c, Frist 19.08., Default LAY-a). Wartet auf den Menschen — keine Teamarbeit offen. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, **kein offener**; DR-Rohdaten gegengeprüft, nichts Unverbuchtes. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: L-2026-08-17j und L-2026-08-17k sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, 492 Tests grün, Matrix 108/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Vertrag unverändert v2. Neuer Bedarf aus P11 als `team-dashboard/T-0002` aufgenommen. |
| team-dashboard/T-0002 | pl | Sprint 6 | offen | **Neu, Rollenzuweisung nach D006.** `letzte_baseline` trägt Tag **und** Annotation unter einem Namen und hat keine Längengrenze (300 Zeichen bei p1). Gefunden in `p11/T-0005`, zuständig ist der Vertragsinhaber. Frist 19.08. |
| platform/T-0008 | cm | Sprint 6 | offen | **Neu, gefunden wegen T-0007.** In `p10`/`p11`/`p12` (verschachtelt in `projects`) läuft die Status-Übergangsprüfung ins Leere — lautlos. Nicht mitgebaut: B025, und die Korrektur schaltet eine nie gelaufene Prüfung ein (braucht Urteil, nicht nur Fix). |
| platform/T-0004 | cm | Sprint 6 | in_review | SWR-107. Beleg weiterhin offen, **aber der Grund ist jetzt behoben statt vermutet**. Frist 18.08. reißt — als Werkzeugdefekt gemeldet, nicht als „wartet auf den Host". |
| pm/T-0043 | prob | Sprint 6 | offen | `p3`/`p5` rot. Derselbe Weg zum Beleg war blockiert, ist es nicht mehr. Kein `blocked` (Verweis ginge über Repo-Grenzen, B047). Frist 19.08. |
| projects/p11/T-0003 | pl | Sprint 6 | offen | Restumfang: Konfiguration, Detailseiten, Mail-Widget, Tests je SWR, G4 als Inbox-DR. **Erste Bauhandlung hängt an `p11/T-0006`** (Rahmenbreite) und an `team-dashboard/T-0002` (Feldgrenze). Frist 20.08. |
| pm/T-0036 | pl | Sprint 7 | offen | Ändert das `BOARD.md`-Format, gebündelt mit `pm/T-0038` (B053). |
| pm/T-0038 | pl | Sprint 7 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| pm/T-0039 | pl | Sprint 8 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 9 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 10 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe. Vorgemerkt: dieselbe Zerlegungsfrage wie bei p11/T-0003. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033).

**Rollenzuweisungen in diesem Sprint (D006):** `team-dashboard/T-0002` geht von `pl`/P11
an `pl`/DASH-RED — der Fund kam beim Layout-Entwurf, die Zuständigkeit liegt beim
Vertragsinhaber. `platform/T-0008` geht an `cm`, weil es Werkzeugfläche ist.

---

## Sprint-Abschluss (Sprint 5, 2026-08-17)

**Geplant beim Start:** 15 nicht geschlossene Aufgaben, davon **8 in diesem Sprint**
(2 Sachtickets — `p11/T-0005` und, aus dem Startcheck, `platform/T-0007` — plus 6
Takt-Pflichten). Im Lauf kamen **4** Tickets dazu: `platform/T-0007`, `platform/T-0008`,
`p11/T-0006`, `team-dashboard/T-0002`.

**Geschlossen:** `platform/T-0007` (neu entstanden und im selben Sprint geschlossen),
`projects/p11/T-0005` und die sechs Takt-Pflichten. `p11/T-0006` ist **vorgelegt** — für
das Team ist daran nichts mehr offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `platform/T-0004` und `pm/T-0043` — Sprint 6. **Der Grund hat sich geändert und das ist
  der Punkt:** drei Sprints lang lautete er „wartet auf einen Hostlauf, der von selbst
  kommt". Er lautet jetzt „der Hostlauf war defekt, der Defekt ist behoben, der Beleg
  entsteht beim nächsten Wächterlauf". Das ist eine **widerlegbare Vorhersage**: bleibt
  `abschluss-auto.log` bei derselben Meldung, ist die Diagnose aus `T-0007` falsch und
  beide Tickets werden wiedereröffnet.
* `platform/T-0008` — Sprint 6. Nicht mitgebaut, zwei dokumentierte Gründe: B025 (dieser
  Sprint hat bereits 16 Dateien in `platform` angefasst) und weil die Korrektur eine nie
  gelaufene Prüfung **einschaltet** — was dabei auftaucht, ist Sprintinhalt und kein
  Beifang.
* `team-dashboard/T-0002` — Sprint 6, Frist 19.08. Vertragsfrage, gehört dem
  Vertragsinhaber.
* `projects/p11/T-0003` — Sprint 6. Der Restumfang steht, aber die erste Bauhandlung
  hängt an zwei Entscheidungen dieses Sprints (Rahmenbreite, Feldgrenze). Frist 20.08.
  gewahrt.
* `pm/T-0036`, `pm/T-0038`, `pm/T-0039`, `pm/T-0028`, `projects/p12/T-0003` — je eine
  Nummer nach hinten, weil Sprint 6 die vier Folgetickets dieses Laufs trägt. Ab Sprint 7
  ist die Nummer ausdrücklich Reihenfolge und keine Zusage.

**Der DR, der nicht gestellt wurde.** Die Planung dieses Sprints sah einen Inbox-DR an den
Auftraggeber vor („bitte einen Hostlauf auslösen", Frist von `platform/T-0004` läuft am
18.08. ab). Er ist **hinfällig geworden**, bevor er geschrieben war: die Ursache war kein
Mensch, sondern ein Werkzeug. Das steht hier, weil ein nicht gestellter DR sonst spurlos
verschwindet — und weil die Reihenfolge lehrreich ist: **erst nachsehen, dann eskalieren.**

## Was dieser Sprint über die Planung gelernt hat

**Der geplante Sprintinhalt war nicht der wertvollste.** Geplant waren `p11/T-0005` und
zwei Zeilen „keine Handlung". Gefunden wurde ein Defekt, der seit dem 17.08. **jeden**
Push der Organisation verhindert hat — im Startcheck, beim Nachsehen an einer Stelle, an
der drei Sprints nicht nachgesehen hatten.

**Zum vierten Mal in fünf Sprints kam der Ertrag aus dem gründlichen Durchgehen**, nicht
aus dem Bauen: Sprint 3 fand B064 beim Feldabgleich, Sprint 4 fand die falsche Annahme im
eigenen Ticket, Sprint 5 fand zwei Werkzeugdefekte beim Lesen eines Protokolls und beim
Nachfragen, was ein `None` alles heißen kann.

**Und ein Muster im Planen selbst.** Ein Ticket, das in drei aufeinanderfolgenden Sprints
dieselbe Zeile bekommt, meldet nicht Geduld, sondern eine ungeprüfte Annahme. Sprint 3 hat
das sogar vorhergesagt („damit es beim dritten Mal auffällt") — und beim dritten Mal ist
es nicht aufgefallen, weil die Zeile dieselbe blieb. **Neu als Planning-Regel:** die
**zweite** Wiederholung eines Wartegrundes ist der Auslöser für eine Prüfung der Quelle,
nicht für einen weiteren Vermerk (L-2026-08-17j Regel 2).

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (Sprint 4, 2026-08-17)

**Geplant:** 15 nicht geschlossene Aufgaben beim Start, davon **8 in diesem Sprint**
(2 Sachtickets + 6 Takt-Pflichten); im Lauf kamen durch die Zerlegung 2 Tickets dazu, eines
davon in diesem Sprint.
**Geschlossen:** `platform/T-0006`, `projects/p11/T-0004` (neu entstanden und im selben
Sprint geschlossen), `team-dashboard/T-0001` (Fassung v2; Takt läuft weiter) und die
fünf übrigen Takt-Pflichten.
**Neu entstanden:** `projects/p11/T-0004` (geschlossen) und `projects/p11/T-0005`.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `platform/T-0004` und `pm/T-0043` — **derselbe** fehlende Beleg wie in Sprint 3: ein
  `CI-STATUS.md` nach 01:17. *(Sprint 5 hat diese Begründung widerlegt — der Wächter lief
  und scheiterte; siehe oben.)*
* `projects/p11/T-0003` (Rest) und `projects/p11/T-0005` — zerlegt statt verschoben,
  Frist 20.08. gewahrt.
* `pm/T-0036`, `pm/T-0038`, `pm/T-0039`, `pm/T-0028`, `projects/p12/T-0003` — unverändert
  in der Reihenfolge.

**Was Sprint 4 an der Planung geändert hat.** Neu als Regel verankert: **jeder Sprint, der
eine Sperre auflöst, fasst den Termin des gesperrten Tickets an** (L-2026-08-17i). Ohne
das überlebt eine Verschiebung ihren Anlass.

## Zahlen

| | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 |
|---|---|---|---|---|
| Tickets gesamt | 246 | 248 | 250 | **254** |
| nicht geschlossen | 15 | 15 | 15 | **15** |
| Tests | 463 | 471 | 486 | **492** |
| Matrix | 107 / 0 | 107 / 0 | 108 / 0 | **108 / 0** |
| offene Briefe | 0 | 0 | 0 | **0** |
| unterminiert / überfällig | 0 / 0 | 0 / 0 | 0 / 0 | **0 / 0** |

**„Nicht geschlossen" steht zum dritten Mal auf 15, und wieder ist es Zufall:** zwei
geschlossen (`platform/T-0007`, `p11/T-0005`), zwei neu offen (`platform/T-0008`,
`team-dashboard/T-0002`), einer vorgelegt und einer aus der Vorwoche gezählt. Die Zahl
steht hier ausgeschrieben, damit sie nicht als Stillstand gelesen wird (B041 Regel 3).
