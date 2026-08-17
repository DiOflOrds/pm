# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 7** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **✅ `pm/T-0043` ist nach fünf Sprints geschlossen — die Vorhersage aus Sprint 6 ist
   eingetroffen.** Der Wächterlauf 05:02 pushte `p3` und `p5`, löste dort je einen CI-Lauf
   aus, und beide sind **grün für ihren Commit**. `CI-STATUS.md` meldet erstmals
   **ALLES GRÜN (14 Abfragen)**. Es war kein Defekt: beide trugen einen Stand vom 16.08.,
   der gegen ein neueres Werkzeug geprüft wurde — und ohne Push kein neuer Lauf.
3. **⚠ Der Startcheck fand, dass Sprint 6 eine Anforderung gemeldet, aber nie committet
   hat.** „Matrix 109 SWRs / 0 Lücken" stimmte für die **Arbeitskopie**; im Git standen
   108. Der Plattformcode war gepusht, sein Requirement nicht. Sofort repariert (`p9`
   committet), dann gebaut: **`platform/T-0010` / SWR-110**.
4. **⚠ Warum das niemand sah — und das ist der eigentliche Befund.** `preflight` **hatte**
   es gemeldet: `[p9] Arbeitskopie nicht sauber (1 Datei(en))`. Daneben fünf gleich
   aussehende Zeilen, alle `1 Datei(en)`, alle eine `BOARD.md`, deren `Stand:`-Zeile das
   Werkzeug **bei jedem Lauf** neu erzeugt. Eine Prüfung, die häufiger belanglos als
   richtig anschlägt, ist eine Wegseh-Übung.
5. **Vier Tickets aus der Warteschlange geschlossen** — `team-dashboard/T-0002` (Vertrag
   v2.1), `pm/T-0045`, `pm/T-0046` und `pm/T-0036` (Teil a abgetrennt als `pm/T-0047`).
   Bei `pm/T-0036` wurde der Verschiebungsgrund **gemessen statt geglaubt** und war leer.
6. **568 Tests grün** (+54), Matrix **114 SWRs / 0 Lücken**, Preflight STARTKLAR, kein
   offener Brief, unterminiert 0, überfällig 0, Plan-Drift 0, **sprint_vergangen 0**.

## Sprint-Plan

*Sprint 7 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 8 (HORIZONT 2); ab Sprint 9 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

*Die Fälligkeitsspalte und das Feld `geplant_sprint` im Ticket sagen dasselbe — geprüft
durch `sprint.plan_drift` (SWR-109). Neu ab diesem Sprint: `sprint.sprint_vergangen`
(SWR-112) meldet zusätzlich jedes offene Ticket, dessen Sprint **vorbei** ist.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0043 | prob | dieser Sprint | **erledigt** | **Nach fünf Sprints geschlossen.** Der Lauf 05:02 pushte `p3`/`p5` und löste die entscheidenden CI-Läufe aus: beide **grün**. Kein Defekt — ein Standbild vom 16.08., das ohne Push nicht altern konnte. Frist 19.08. gewahrt. |
| platform/T-0010 | cm | dieser Sprint | **erledigt** | **Nicht geplant gewesen — im Startcheck gefunden.** SWR-109 war nie committet; die Matrix maß die Arbeitskopie, der Push lieferte HEAD. `p9` sofort committet, dann SWR-110: Preflight **nennt** unverbuchte Verifikationsquellen und macht sie zum Befund. Stand-Zeilen-Ausnahme am **Diff** entschieden, mit Gegenprobe. 19 Tests. |
| team-dashboard/T-0002 | pl | dieser Sprint | **erledigt** | Vertrag **v2.1**: `letzte_baseline` trägt nur den Tag, die Annotation steht in `letzte_baseline_text`. Getrennt in der **Quelle** (`aggregation`), nicht im Widget. Am echten Payload geprüft (p1 300 → 7 + 284). SWR-111, 11 Tests. Frist 19.08. gewahrt. |
| pm/T-0045 | pl | dieser Sprint | **erledigt** | Die drei offenen Abgrenzungen entschieden: erledigte Tickets kein Fall, `in_review` zählt mit, `decision-request` ausgenommen. **SWR-112**, 9 Tests. Ohne die DR-Ausnahme hätte die Prüfung an Tag eins `p11/T-0006` fehlgemeldet. Frist 20.08. gewahrt. |
| pm/T-0046 | pl | dieser Sprint | **erledigt** | Zählweise festgelegt: „nicht geschlossen" = `offen_gesamt`, **Takt-Dauerläufer eingeschlossen**; `sachtickets` als eigene Zahl daneben. Aus dem Werkzeug bezogen, nicht abgetippt. **SWR-113**, 7 Tests. Alte Reihe **nicht** rückwirkend korrigiert. Frist 20.08. gewahrt. |
| pm/T-0036 | pl | dieser Sprint | **erledigt** | **Der Verschiebungsgrund wurde gemessen (L-2026-08-17j Regel 2): 0 unterminierte Tickets im Bestand** — der Anlass ist leer, die Lücke nicht. Teil b) gebaut (**SWR-114**, org-weite Preflight-Zeile mit Namen) — das **ist** das Abnahmekriterium. Teil c) als Regel verankert. 8 Tests. |
| pm/T-0047 | pl | Sprint 8 | offen | **Neu, Teil a) aus `pm/T-0036`.** Org-Summe im Cockpit-**Kopfblock** ändert den Cockpit- und Widget-Vertrag; Sprint 7 hat `aggregation.cockpit` bereits für SWR-111 angefasst (B025). Frist 23.08. |
| pm/T-0038 | pl | Sprint 8 | offen | Feld `verantwortlich` in Board, Cockpit und Preflight — Board-**Formatänderung**, die jedes Repo-CI prüft. Grund unten im Abschluss. Frist 23.08. |
| projects/p11/T-0006 | pl | wartet-auf-Mensch | vorgelegt | DR an den Auftraggeber (LAY-a/b/c, Frist 19.08., Default LAY-a). Für das Team ist daran nichts offen. Von `sprint_vergangen` ausgenommen — begründet in SWR-112. |
| projects/p11/T-0003 | pl | Sprint 8 | offen | **Eine Sperre ist gefallen:** `team-dashboard/T-0002` ist entschieden, die Feldgrenze steht. Es hängt jetzt nur noch an `p11/T-0006` (beim Menschen). Frist 20.08. |
| pm/T-0039 | pl | Sprint 8 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 9 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 10 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — **kein offener Brief**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: **L-2026-08-17n** (5 Regeln) sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, **568 Tests** grün, Matrix 114/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Vertrag auf **v2.1** gezogen (SWR-111); die offene Frage aus `T-0002` ist beantwortet. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033) — und genau deshalb nimmt `plan_drift` sie aus.

**Rollenzuweisungen in diesem Sprint (D006):** `platform/T-0010` liegt bei `cm`
(Werkzeugfläche, Preflight). `pm/T-0045`, `pm/T-0046`, `pm/T-0036` und `pm/T-0047` liegen
bei `pl`, weil alle vier die Planung und ihre Kennzahlen betreffen — die Prüfungen sind
die Folge, nicht die Sache. `pm/T-0043` blieb bei `prob` bis zum Schluss.

---

## Sprint-Abschluss (Sprint 7, 2026-08-17)

**Geplant beim Start:** 16 nicht geschlossene Aufgaben (Werkzeugzahl nach der in diesem
Sprint festgelegten Zählweise, SWR-113), davon **11 in diesem Sprint** — 5 Sachtickets
(`pm/T-0043`, `team-dashboard/T-0002`, `pm/T-0045`, `pm/T-0046`, `pm/T-0036`) plus 6
Takt-Pflichten. Im Lauf kamen **2** Tickets dazu: `platform/T-0010` (aus dem Startcheck)
und `pm/T-0047` (Abtrennung aus `pm/T-0036`).

**Geschlossen:** `pm/T-0043`, `platform/T-0010` (neu entstanden und im selben Sprint
geschlossen), `team-dashboard/T-0002`, `pm/T-0045`, `pm/T-0046`, `pm/T-0036` und die sechs
Takt-Pflichten — **zehn Stück**. `p11/T-0006` bleibt **vorgelegt**; für das Team ist daran
nichts offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `pm/T-0038` — Sprint 8, Frist 23.08. **Grund: Board-Formatänderung.** Das Feld
  `verantwortlich` ändert das `BOARD.md`-Format, und dieses Format prüft die CI **jedes**
  Repos. Sprint 7 hat bereits `preflight.py`, `aggregation.py`, `sprint.py`, `app.js` und
  den Widget-Vertrag angefasst; eine Formatänderung obendrauf ist die Bündelung, vor der
  B025 warnt. **Konkreter Zusatzgrund:** eine Formatänderung macht in **allen 16** Repos
  die `BOARD.md` unsauber — genau die Datei, für die dieser Sprint in SWR-110 eine
  Ausnahme gebaut hat. Beides im selben Lauf hieße, eine neue Prüfung an ihrem ersten Tag
  gegen ihren eigenen Ausnahmefall laufen zu lassen. **Das ist die erste Verschiebung
  dieses Tickets mit diesem Grund** — bei der zweiten greift L-2026-08-17j Regel 2 und der
  Grund wird gemessen.
* `pm/T-0047` — Sprint 8, neu abgetrennt. Grund im Ticket: eigener Vertragsumfang.
* `projects/p11/T-0003` — Sprint 8. **Eine seiner zwei Sperren ist gefallen**
  (`team-dashboard/T-0002` entschieden); die zweite liegt beim Auftraggeber. Frist 20.08.
* `pm/T-0039` Sprint 8, `pm/T-0028` Sprint 9, `projects/p12/T-0003` Sprint 10 —
  unverändert in der Reihenfolge. Ticketfelder mitgezogen (SWR-109).

**Widerlegbare Vorhersage für Sprint 8.** `preflight` meldet ab jetzt unverbuchte
Verifikationsquellen als **Befund** und bricht damit `abschluss.cmd` in `[1/5]` ab. Wenn
das Werkzeug richtig gebaut ist, läuft der nächste Wächterlauf **durch** — dieser Sprint
hat alles committet. Bricht er in `[1/5]` mit einer `BEFUND:`-Zeile ab, ist die
Stand-Zeilen-Ausnahme aus SWR-110 zu eng gefasst und `platform/T-0010` wird wiedereröffnet.

## Was dieser Sprint über die Planung gelernt hat

**Zum dritten Mal in Folge kam der wertvollste Inhalt aus dem Startcheck** — und zum
zweiten Mal war er dort **fällig**, weil der Vorsprint eine prüfbare Zeile hinterlassen
hatte. Sprint 6 sagte „der nächste Lauf erreicht [3/5] oder weiter"; nachgesehen wurde,
und der Blick fiel dabei auf sechs Zeilen, von denen eine nicht dazugehörte.

**Ein Werkzeug hat diesmal den Fehler des Vorsprints gefunden, nicht ein Mensch.** Der
Startcheck war `git status` über alle Repos. Der Unterschied zu den Sprints davor ist
nicht Aufmerksamkeit, sondern dass die Frage *„ist das Gemessene das Gelieferte?"* gestellt
wurde — sie stand in keiner Routine, und ab jetzt steht sie in `preflight`.

**Und ein Verschiebungsgrund ist zum zweiten Mal in zwei Sprints an der Messung
gescheitert.** `platform/T-0008` in Sprint 6 („was dabei auftaucht, braucht Urteil" → 0
Befunde), `pm/T-0036` hier („Änderung an der Prüfstrecke, nicht nebenbei" → 0 unterminierte
Tickets, danach war Teil b) klein und beidseitig testbar). L-2026-08-17j Regel 2 ist damit
die Regel dieses Projekts mit der höchsten Trefferquote.

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

| | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 | Sprint 6 | Sprint 7 |
|---|---|---|---|---|---|---|
| Tickets gesamt | 246 | 248 | 250 | 254 | 258 | **260** |
| nicht geschlossen | 15 ⚠ | 15 ⚠ | 15 ⚠ | 15 ⚠ | 17 (Start: 17) | **14** (Start: 16) |
| davon Sachtickets | — | — | — | — | 11 | **8** |
| Tests | 463 | 471 | 486 | 492 | 514 | **568** |
| Matrix | 107 / 0 | 107 / 0 | 108 / 0 | 108 / 0 | 109 / 0 | **114 / 0** |
| offene Briefe | 0 | 0 | 0 | 0 | 0 | **0** |
| unterminiert / überfällig | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | **0 / 0** |
| Plan-Drift | — | — | — | 7 (unbemerkt) | 0 | **2 → 0** |
| Sprint vergangen | — | — | — | 2 (unbemerkt) | 2 (unbemerkt) | **0** |

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

**⚠ Ab Sprint 7 ist „nicht geschlossen" definiert — vorher war sie es nicht** (`pm/T-0046`,
SWR-113). Die Zählweise lautet: jedes Ticket, dessen Status weder `done` noch `rejected`
ist, **Takt-Dauerläufer eingeschlossen**; `davon Sachtickets` steht als eigene Zahl daneben.
Die Werte der Sprints 2–5 bleiben **unkorrigiert** mit ⚠ stehen: sie passen zu keiner der
beiden Zählweisen, und eine still ersetzte Zahl nimmt dem nächsten Leser den Hinweis
(L-2026-08-17g Regel 4).

**Die Zeile „Plan-Drift" liest sich in Sprint 7 als `2 → 0`, und das ist kein Schönfärben.**
Beim Fortschreiben des Plans wurden `pm/T-0038` und `p11/T-0003` eine Nummer nach hinten
gesetzt — und die Prüfung aus Sprint 6 hat **denselben Fehler bei ihrem eigenen Erbauer**
gefunden, im Lauf danach. Die Ticketfelder wurden nachgezogen, danach 0. Genau dafür ist
sie gebaut.

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
