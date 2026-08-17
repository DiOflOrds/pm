# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 6** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **⚠ Der Wächter bricht weiter ab — aber an einer späteren Stelle, und das ist der
   Beleg.** Der erste Lauf nach der T-0007-Reparatur (03:59) kam bis
   `PREFLIGHT: STARTKLAR` und starb dann beim **Melden** eines Befundes statt beim
   **Lesen**. Behoben: **`platform/T-0009`**, 11 Tests, Suite 492 → **503**.
3. **⚠ Zwei Sätze aus Sprint 5 sind widerlegt.** Nicht „seit dem 17.08. kein einziger
   Push" und nicht „rund zweihundert Mal": das Protokoll zählt für den 17.08.
   **12 Läufe, 4 erfolgreiche Pushes, 9 Fehler** — und die Fehlserie beginnt um
   **02:14**, 20 Minuten nach dem Commit, der das Zeichen einbrachte. Die Diagnose war
   richtig, die Reichweite war geschätzt statt gezählt.
4. **⚠ Befund im Planen selbst: sieben Planzeilen sagten etwas anderes als ihr Ticket.**
   Sprint 5 hat fünf Aufgaben in dieser Datei „eine Nummer nach hinten" geschoben und
   die Ticketfelder nicht angefasst. Aufgelöst und ab jetzt geprüft (**SWR-109**).
5. **`platform/T-0008` erledigt — sein Verschiebungsgrund war messbar und leer.** Sprint 5
   hatte es mit *„was dabei auftaucht, braucht Urteil"* vertagt. Gemessen, ohne zu bauen:
   **0 Befunde**. Danach war die Korrektur eine Zeile.
6. **⚠ Der Wächterlauf um 04:29 ist DURCHGELAUFEN** — erster erfolgreicher Push seit
   01:31, `CI-STATUS.md` neu (04:32). Die Vorhersage aus `T-0009` ist damit **im selben
   Lauf eingetroffen und übererfüllt** (nicht `[3/5]`, sondern `[5/5]`). Der Bericht nennt
   erstmals Job und Schritt für die roten Repos → **`platform/T-0004` geschlossen**, und
   für `pm/T-0043` sind zwei Ursachen ausgeschlossen. **`platform` ist grün** — auch die
   Vorhersage aus Sprint 3 ist eingetroffen.
7. **514 Tests grün** (+22), Matrix **109 SWRs / 0 Lücken**, Preflight STARTKLAR, **kein
   offener Brief** (48), unterminiert 0, überfällig 0, **Plan-Drift 0**.

## Sprint-Plan

*Sprint 6 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 7 (HORIZONT 2); ab Sprint 8 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

*Die Fälligkeitsspalte und das Feld `geplant_sprint` im Ticket sagen dasselbe. Das ist
seit diesem Sprint keine Sorgfaltsfrage mehr, sondern geprüft: `sprint.plan_drift`
meldet jede Zeile, die von ihrem Ticket abweicht (SWR-109).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0009 | cm | dieser Sprint | **erledigt** | **Nicht geplant gewesen — im Startcheck gefunden.** Der Wächter starb am `print` eines Befundes. Zwei unabhängige Ursachen: die T-0007-Reparatur hat an den drei Stellen, an denen Python Python aufruft, eine funktionierende Kodierungspaarung zerstört; und 121 Ticketdateien tragen ein „→", das cp1252 nicht ausgeben kann. Neu `scripts/konsole.py`, 11 Tests, Suite 492 → 503. |
| pm/T-0044 | pl | dieser Sprint | **erledigt** | **Neu, im Sprint-Planning gefunden.** Sieben Planzeilen wichen von ihrem Ticket ab; `nicht_geplant` war zu Recht leer — Anwesenheit ist nicht Übereinstimmung. Tickets nachgezogen, Prüfung gebaut (SWR-109), 7 Tests, Suite 503 → 510. |
| platform/T-0008 | cm | dieser Sprint | **erledigt** | Übergangsprüfung lief in `p10`/`p11`/`p12` ins Leere — für 3 von 16 Einträgen hat SWR-002 nie geprüft. **Der Verschiebungsgrund aus Sprint 5 wurde gemessen statt geglaubt: 0 Befunde**, danach war die Korrektur eine Zeile (`rev-parse --show-prefix`). 4 Tests, Suite 510 → 514. |
| team-dashboard/T-0002 | pl | Sprint 7 | offen | `letzte_baseline` trägt Tag **und** Annotation unter einem Namen, ohne Längengrenze. **Einziger geplanter Sprintinhalt, der nicht erledigt wurde** — zwei ungeplante Befunde gingen vor (Grund im Abschluss). Frist 19.08. noch nicht gerissen. |
| projects/p11/T-0006 | pl | wartet-auf-Mensch | vorgelegt | DR an den Auftraggeber: Dashboard verlässt den Textkorridor (LAY-a/b/c, Frist 19.08., Default LAY-a). Für das Team ist daran nichts mehr offen. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, **kein offener**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: L-2026-08-17l und L-2026-08-17m sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, **514 Tests** grün, Matrix 109/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Vertrag unverändert v2; die offene Frage liegt in `T-0002`. |
| platform/T-0004 | cm | dieser Sprint | **erledigt** | SWR-107. **Der Beleg kam im Lauf an:** der Wächterlauf 04:29 ging durch, `CI-STATUS.md` (04:32) nennt für p3 und p5 Job **und** Schritt. Netzweg am Host nachgewiesen, alle fünf Zusicherungen geprüft, `p1`/HTTP 504 als echter Abruffehler korrekt behandelt. **Frist 18.08. gewahrt.** |
| pm/T-0043 | prob | Sprint 7 | offen | `p3`/`p5` rot. **Zwei Ursachen ausgeschlossen:** der rote Schritt („BOARD.md aktuell?") liegt **nach** dem platform-Checkout → **kein Secret-Problem, Klasse-A-Sorge entfällt**; und beide regenerieren heute byte-gleich bis auf die Stand-Zeile, die der Vergleich ignoriert. Der Zustand ist ein **Standbild vom 16.08.** — ohne Push kein neuer Lauf. Deshalb `BOARD.md` neu erzeugt und committet: der nächste Push **löst den entscheidenden Lauf aus**. Frist 19.08. |
| projects/p11/T-0003 | pl | Sprint 7 | offen | Restumfang: Konfiguration, Detailseiten, Mail-Widget, Tests je SWR, G4 als Inbox-DR. **Erste Bauhandlung hängt an `p11/T-0006`** (Rahmenbreite) und an `team-dashboard/T-0002` (Feldgrenze). Frist 20.08. |
| pm/T-0045 | pl | Sprint 7 | offen | **Neu, Nebenbefund aus `pm/T-0044`.** Ein offenes Ticket auf einem **vergangenen** Sprint meldet niemand — beim Start dieses Sprints traf das auf zwei zu, während „überfällig 0" gemeldet wurde. Nicht mitgebaut: die Abgrenzung zu erledigten und geparkten Tickets braucht Urteil (B025). Frist 20.08. |
| pm/T-0046 | pl | Sprint 7 | offen | **Neu, beim Nachzählen der eigenen Abschlusszahlen.** „Nicht geschlossen" stand vier Sprints auf **15**; das Werkzeug zählt **17 beim Start / 18 beim Abschluss**, und die Zählweise der 15 steht nirgends. Frist 20.08. |
| pm/T-0036 | pl | Sprint 7 | offen | Ändert das `BOARD.md`-Format, gebündelt mit `pm/T-0038` (B053). |
| pm/T-0038 | pl | Sprint 7 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| pm/T-0039 | pl | Sprint 8 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 9 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 10 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe. Vorgemerkt: dieselbe Zerlegungsfrage wie bei p11/T-0003. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033) — und genau deshalb nimmt `plan_drift` sie aus.

**Rollenzuweisungen in diesem Sprint (D006):** `pm/T-0044`, `pm/T-0045` und `pm/T-0046`
liegen bei `pl`, weil alle drei die Planung selbst betreffen und nicht das Werkzeug — die
Prüfungen sind die Folge, nicht die Sache. `platform/T-0009` liegt bei `cm` (Werkzeugfläche),
ebenso `platform/T-0008`.

---

## Sprint-Abschluss (Sprint 6, 2026-08-17)

**Geplant beim Start:** 17 nicht geschlossene Aufgaben (Werkzeugzahl), davon **9 in diesem
Sprint** — 3 Sachtickets (`platform/T-0008`, `team-dashboard/T-0002` und, aus dem
Startcheck, `platform/T-0009`) plus 6 Takt-Pflichten. Im Lauf kamen **4** Tickets dazu
(`platform/T-0009`, `pm/T-0044`, `pm/T-0045`, `pm/T-0046`) — und **`platform/T-0004` wurde
aus der Warteschlange in diesen Sprint gezogen**, weil sein Beleg um 04:32 eintraf.

**Geschlossen:** `platform/T-0009` und `pm/T-0044` (beide neu entstanden und im selben
Sprint geschlossen), `platform/T-0008`, **`platform/T-0004`** und die sechs Takt-Pflichten.
`p11/T-0006` bleibt **vorgelegt** — für das Team ist daran nichts offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `team-dashboard/T-0002` — Sprint 7, Frist 19.08. **Der einzige geplante Sprintinhalt,
  der nicht erledigt wurde.** Grund: der Startcheck hat mit `platform/T-0009` einen
  Defekt gefunden, der **jeden Push der Organisation** blockiert, und das Planning mit
  `pm/T-0044` einen zweiten in der Planung selbst. Beide gingen vor. Die Frist ist noch
  nicht gerissen; reißt sie, ist das ein Verzug und wird als solcher gemeldet.
* `pm/T-0043` — Sprint 7, Frist 19.08. **Aber mit einem anderen Ticketinhalt als in den
  vier Sprints davor:** zwei Ursachen sind ausgeschlossen (das Secret, weil der rote
  Schritt nach dem Checkout liegt; der heutige Inhalt, weil p3/p5 byte-gleich
  regenerieren), und der entscheidende CI-Lauf ist **angestoßen** statt erhofft — die
  `BOARD.md` beider Repos ist neu erzeugt und committet, beide stehen in der
  Push-Anforderung. **Widerlegbare Vorhersage:** beide werden grün.
* `projects/p11/T-0003` — Sprint 7. Erste Bauhandlung hängt an `p11/T-0006` (beim
  Auftraggeber) und `team-dashboard/T-0002`. Frist 20.08. gewahrt.
* `pm/T-0045`, `pm/T-0046` — Sprint 7, beide neu und beide bewusst nicht mitgebaut: die
  eine braucht eine Abgrenzung (was heißt „überfällig" für ein geparktes Ticket), die
  andere eine Festlegung (welche Zählweise gilt). Beides ist Urteil und kein Fix (B025).
* `pm/T-0036`, `pm/T-0038` — Sprint 7 unverändert. `pm/T-0039` Sprint 8, `pm/T-0028`
  Sprint 9, `projects/p12/T-0003` Sprint 10 — unverändert in der Reihenfolge.
  **Anders als in Sprint 5 wurden die Ticketfelder diesmal mitgezogen** (SWR-109).

## Was dieser Sprint über die Planung gelernt hat

**Die Sprint-5-Regel hat in Sprint 6 zweimal etwas gekippt — und beide Male war es eine
Begründung dieses Projekts.** L-2026-08-17j Regel 2 (*die zweite Wiederholung eines
Wartegrundes ist der Auslöser für eine Prüfung der Quelle*) galt bisher für Wartegründe.
Hier hat sie zuerst den Wartegrund von `platform/T-0004`/`pm/T-0043` geprüft — und dann
den **Verschiebungs**grund von `platform/T-0008`, der sich in fünf Minuten messen ließ und
sich als leer erwies. Die Regel gilt ab jetzt ausdrücklich für beide (L-2026-08-17m
Regel 3).

**Vier ungezählte Zahlen in einem Lauf, und die vierte fand die eigene Regel.** „Rund
zweihundert Läufe" (9), „die sieben Zeilen" (6), „was dabei auftaucht braucht Urteil" (0)
— und beim Schreiben des Abschlusses „nicht geschlossen 14" (17). Die letzte entstand
**nachdem** die Lehre aus den ersten dreien geschrieben war, im selben Dokument. Das ist
kein Argument gegen die Regel, sondern ihr Anwendungsfall: sie hat gegriffen, weil
jemand nachgezählt hat.

**Und eine Beobachtung zum Startcheck.** Zum zweiten Mal in Folge war der wertvollste
Sprintinhalt nicht der geplante — aber diesmal war er **fällig**: Sprint 5 hatte eine
widerlegbare Vorhersage hinterlassen, und die nachzusehen war Pflicht. Der Unterschied
zwischen Sprint 5 und Sprint 6 ist nicht Aufmerksamkeit, sondern dass es eine Zeile gab,
die man prüfen musste.

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

| | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 | Sprint 6 |
|---|---|---|---|---|---|
| Tickets gesamt | 246 | 248 | 250 | 254 | **258** |
| nicht geschlossen | 15 ⚠ | 15 ⚠ | 15 ⚠ | 15 ⚠ | **17** (Start: 17) |
| Tests | 463 | 471 | 486 | 492 | **514** |
| Matrix | 107 / 0 | 107 / 0 | 108 / 0 | 108 / 0 | **109 / 0** |
| offene Briefe | 0 | 0 | 0 | 0 | **0** |
| unterminiert / überfällig | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | **0 / 0** |
| Plan-Drift | — | — | — | 7 (unbemerkt) | **0** |

**⚠ Die Zeile „nicht geschlossen" ist ab Sprint 6 eine andere Zahl, und der Sprung ist
kein Ereignis.** Sprint 6 zählt mit dem Werkzeug (`sprint.plan()["offen_gesamt"]`): **17 beim Start**
und **17 beim Abschluss** — zwei geschlossen (`platform/T-0008`, `platform/T-0004`), zwei neu
offen (`pm/T-0045`, `pm/T-0046`); ohne die sechs Takt-Dauerläufer wären es 11. Die **15** der Sprints 2–5 passt zu keiner
dieser beiden Zählweisen, und ihre Zählweise ist nicht dokumentiert. Die alten Werte
bleiben **unkorrigiert** stehen und tragen ein ⚠ — eine still ersetzte Zahl nimmt dem
nächsten Leser den Hinweis, welche Art Angabe hier ungeprüft durchging (L-2026-08-17g
Regel 4). Aufgenommen als `pm/T-0046`.

**„Nicht geschlossen" steht zum dritten Mal auf 15, und wieder ist es Zufall:** zwei
geschlossen (`platform/T-0007`, `p11/T-0005`), zwei neu offen (`platform/T-0008`,
`team-dashboard/T-0002`), einer vorgelegt und einer aus der Vorwoche gezählt. Die Zahl
steht hier ausgeschrieben, damit sie nicht als Stillstand gelesen wird (B041 Regel 3).

## Nachtrag zur Sprint-Sicht (Verifikation, Sprint 5)

Beim Gegenlesen mit `sprint.plan()` meldete der Zähler `wartet_auf_mensch: 0`, während
`p11/T-0006` genau darauf wartet. Ursache war **diese Datei, nicht das Werkzeug**: die
Fälligkeitsspalte trug „dieser Sprint" und der Zustand das selbst erfundene Wort
„vorgelegt". `sprint.py` erkennt die Zuständigkeit an der Wendung **`wartet-auf-Mensch`**
(SWR-103, Befund B057) — und eine Planzeile, die eine eigene Vokabel benutzt, macht die
Zahl daneben still falsch.

Korrigiert: die Zeile trägt jetzt `wartet-auf-Mensch` in der Fälligkeitsspalte. Das ist
dieselbe Familie wie B033 und ein kleiner Beleg für dieselbe Regel wie der Sprintbefund
oben — **ein Werkzeug, das eine Zahl bildet, muss die Sprache lesen können, in der der
Plan geschrieben ist.** Gefunden nur, weil die Sicht gegen den echten Bestand gelaufen
ist und nicht bloß geschrieben wurde.
