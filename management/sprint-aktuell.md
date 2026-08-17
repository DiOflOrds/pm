# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 8** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **⚠ Der Startcheck fand, dass Sprint 7 ein Ticket vierfach als erledigt gemeldet hat,
   das auf `open` stand.** `platform/T-0010` war in `sprint-aktuell.md` (Planzeile **und**
   Abschluss), in `session-agenda.md` und in `PROJEKTSTATUS-UPDATE.md` als erledigt
   ausgewiesen — und damit in der Meldung an den Auftraggeber. Die **Arbeit war fertig**
   (SWR-110 in `p9` im Git, 19 Tests grün, `BEFUND:`-Zeile in `preflight`); nur das Feld
   wurde nie umgelegt.
3. **⚠ Und der eigentliche Befund ist, dass alle drei Planprüfungen `[]` meldeten.**
   `nicht_geplant`: das Ticket **steht** im Plan. `plan_drift` (SWR-109): die Planzeile
   sagt „dieser Sprint", also `sprint_nr is None`, also **übersprungen** — und die Prüfung
   vergleicht ohnehin nur die Sprintnummer, **nie die Statusspalte**. `sprint_vergangen`
   (SWR-112): `7 < 7` ist falsch. Aufgenommen als **`pm/T-0049`**.
4. **⚠ Die übersprungene Zeilenart ist genau die, um die es geht.** „dieser Sprint" tragen
   die Aufgaben, die der laufende Sprint gerade **schließt** — also die Zeilen, in denen im
   Abschluss „erledigt" geschrieben wird. `plan_drift` prüft die Zukunft und lässt die
   Gegenwart aus.
5. **✅ Die widerlegbare Vorhersage aus Sprint 7 ist eingetroffen.** Der Wächterlauf 05:47
   ist **durchgelaufen**, hat gepusht, und `CI-STATUS.md` meldet **ALLES GRÜN (15
   Abfragen)** — eine Abfrage mehr als in Sprint 7. SWR-110 hat `abschluss.cmd` nicht
   fälschlich angehalten; die Stand-Zeilen-Ausnahme ist damit **am Bestand** bestätigt und
   nicht nur im Test.
6. **✅ SWR-110 hat an seinem ersten echten Tag zweimal korrekt gegriffen** — es nannte in
   diesem Lauf `platform/tickets/T-0010.md` und `pm/tickets/T-0049.md` als unverbucht und
   ließ die fünf regenerierten `Stand:`-Zeilen zu Recht durch.
7. **`pm/T-0038` — der Verschiebungsgrund wurde gemessen und ist leer.** Das Ticket
   verlangte wörtlich, „gebündelt mit `pm/T-0036`" ausgeliefert zu werden. `pm/T-0036` ist
   seit Sprint 7 **geschlossen** — und hat **nie** eine Board-Formatänderung gemacht
   (Teil b) wurde eine Preflight-Zeile, Teil a) ging als `pm/T-0047` weiter). Der Partner,
   auf den gewartet wurde, existiert nicht mehr. Zerlegt statt erneut verschoben.
8. **Kein offener Brief.** Preflight STARTKLAR, unterminiert 0, überfällig 0.

## Sprint-Plan

*Sprint 8 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 9 (HORIZONT 2); ab Sprint 10 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

*Die Fälligkeitsspalte und das Feld `geplant_sprint` sagen dasselbe — geprüft durch
`sprint.plan_drift` (SWR-109). **Neu ab diesem Sprint:** die **Statusspalte** dieser
Tabelle wird gegen den Ticketstatus gehalten (`sprint.status_drift`, SWR-115) — die Lücke,
durch die `platform/T-0010` gefallen ist.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0010 | cm | dieser Sprint | **erledigt** | **Reparatur aus dem Startcheck.** Alle fünf DoD-Punkte nachgeprüft und erfüllt; das Ticket stand trotzdem auf `open`. Über den **legalen** Weg geschlossen (`open → in_progress → in_review → done`) mit **drei** Commits statt einem — damit fällt es nicht zusätzlich unter `pm/T-0048`. |
| pm/T-0049 | pl | dieser Sprint | **erledigt** | **Neu, im Startcheck gefunden und im selben Sprint geschlossen.** **SWR-115**: die Statusspalte wird ab jetzt in `preflight` gegen den Ticketstatus gehalten — beide Richtungen, Takt-Dauerläufer ausgenommen. 17 Tests. Die Prüfung hat an ihrem ersten Tag einen echten Drift im **eigenen** Plan gefunden. |
| pm/T-0048 | cm | Sprint 9 | offen | Übergangsprüfung ist blind für einen bereits committeten Sprung. **Dieselbe Familie wie `pm/T-0049`:** eine Prüfung, die nicht den Sachverhalt misst, sondern wann man sie laufen lässt. **Verschoben** — Grund unten im Abschluss. Frist 23.08. |
| pm/T-0038 | pl | dieser Sprint | **erledigt** | **Verschiebungsgrund gemessen (L-2026-08-17j Regel 2) — er ist leer.** Der Bündelungspartner `pm/T-0036` ist geschlossen und hat nie ein Board-Format geändert. **Zerlegt**; Teil a) gebaut: **SWR-116**, Feld `verantwortlich` (`team`/`mensch`, optional, `mensch` verlangt einen Handlungsabschnitt), 16 Tests, **alle 16 Boards validieren unverändert**. |
| pm/T-0050 | pl | Sprint 9 | offen | **Neu, Teil b) aus `pm/T-0038`.** `BOARD.md`-Spalte „Verantwortlich" — **das** ist die Formatänderung, die jedes Repo-CI prüft. Sie war der Grund, der die Teile a), c) und e) mitverschoben hat. |
| pm/T-0051 | pl | Sprint 9 | offen | **Neu, Teil c) aus `pm/T-0038`.** Cockpit- und Preflight-Zähler „n Tickets warten auf den Menschen" **mit Refs**. Berührt denselben Kopfblock wie `pm/T-0047` — nacheinander, nicht nebeneinander (B025). |
| pm/T-0052 | pl | Sprint 10 | offen | **Neu, Teil e) aus `pm/T-0038`.** HMI-Abschnitt „Für dich: Handlungen" neben der Inbox — eigener Abschnitt, **nicht** dieselbe Liste (B033: an der Inbox-Liste hängen die Entscheidungsknöpfe). |
| pm/T-0047 | pl | Sprint 9 | offen | Org-Summe „unterminiert" im Cockpit-**Kopfblock**. Grund unten im Abschluss. Frist 23.08. |
| pm/T-0039 | pl | Sprint 9 | offen | Am Brief weiterkommentieren — eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI). Frist 23.08. |
| projects/p11/T-0006 | pl | wartet-auf-Mensch | vorgelegt | DR an den Auftraggeber (LAY-a/b/c, Frist 19.08., Default LAY-a). Für das Team ist daran nichts offen. Von `sprint_vergangen` ausgenommen — begründet in SWR-112. |
| projects/p11/T-0003 | pl | wartet-auf-Mensch | **blocked** | **Status korrigiert.** Beide Sperren benannt: `team-dashboard/T-0002` ist gefallen, `T-0006` liegt beim Auftraggeber. Das Ticket stand auf `open` und sah dadurch wie unerledigte Teamarbeit aus, obwohl das Team es nicht bewegen kann. `blocked_by: [T-0006]`. Frist 20.08. |
| pm/T-0028 | chg | Sprint 9 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 10 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — **kein offener Brief**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight, Tests, Matrix. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Widget-Vertrag — in diesem Sprint keine Vertragsänderung nötig. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033) — und genau deshalb nimmt `plan_drift` sie aus. **Sie
sind auch der Grund, warum `status_drift` (SWR-115) eine Ausnahme braucht:** sie tragen
dauerhaft „erfüllt" im Plan und `open` im Ticket, und beides ist richtig.

**Rollenzuweisungen in diesem Sprint (D006):** `pm/T-0049` liegt bei `pl` — es ist ein
Befund an der **Planung** und ihren Kennzahlen; die Prüfung ist die Folge, nicht die Sache
(dieselbe Begründung wie bei `pm/T-0045`/`T-0046` in Sprint 7). `pm/T-0048` bleibt bei
`cm`, weil es die Werkzeugfläche `board.py` betrifft. Die drei Abtrennungen aus `pm/T-0038`
bleiben bei `pl`, weil das Ursprungsticket dort lag und die Zerlegung keine fachliche
Umwidmung ist.


---

## Sprint-Abschluss (Sprint 8, 2026-08-17)

**Geplant beim Start:** 15 nicht geschlossene Aufgaben (Werkzeugzahl, SWR-113), davon **9 in
diesem Sprint** — 3 Sachtickets (`pm/T-0048`, `pm/T-0047`, `pm/T-0038`) plus 6
Takt-Pflichten. Im Lauf kamen **5** Tickets dazu: `pm/T-0049` (aus dem Startcheck) und die
vier Abtrennungen `pm/T-0050`, `pm/T-0051`, `pm/T-0052` aus `pm/T-0038`. Und
**`platform/T-0010` wurde aus der Vergangenheit zurückgeholt** — es war in Sprint 7 als
erledigt gemeldet, aber nie verbucht.

**Geschlossen:** `platform/T-0010` (Reparatur), `pm/T-0049` (neu entstanden und im selben
Sprint geschlossen), `pm/T-0038` Teil a) und die sechs Takt-Pflichten — **neun Stück**.
`p11/T-0006` bleibt **vorgelegt**; `p11/T-0003` ist von `open` auf **`blocked`** korrigiert.

**Der Startcheck war zum vierten Mal in Folge der wertvollste Teil des Sprints.** Diesmal
fand er keinen Defekt in einem Werkzeug, sondern **eine Meldung ohne Deckung**: vier
Dokumente sagten „erledigt", das Ticket sagte `open`. Vier übereinstimmende Abschriften sehen
aus wie eine Bestätigung.

**⚠ Die drei Prüfungen, die schwiegen, hatten alle recht.** Das ist der Teil, der zählt.
`nicht_geplant` fragt nach dem Vorkommen, `plan_drift` nach der Sprintnummer,
`sprint_vergangen` nach der Gegenwart — die **Statusspalte** las keine. Und die Zeilenart,
die `plan_drift` überspringt („dieser Sprint"), ist genau die, die ein laufender Sprint
schließt: die Prüfung sieht die Zukunft und lässt die Gegenwart aus.

**⚠ `sprint_vergangen` hat den Fall gefunden — einen Sprint zu spät, und zwar
konstruktionsbedingt.** Solange Sprint 7 lief, war `7 < 7` falsch. Ihr frühester möglicher
Zeitpunkt liegt **nach** dem Bericht an den Auftraggeber. Deshalb steht SWR-115 in
`preflight` und nicht in der Sprintsicht.

**✅ Die neue Prüfung hat an ihrem ersten Tag einen echten Drift gefunden — im eigenen
Plan.** Nachdem `pm/T-0049` auf `done` ging, meldete sie die **zweite** Richtung: *„Ticket
steht auf done, Plan sagt offen"*. Das ist der Fall, den `offene_tickets` grundsätzlich nicht
sehen kann und für den `sprint.alle_tickets` gebaut wurde. Eine Prüfung, die ihren Erbauer im
selben Lauf erwischt, ist am Bestand belegt und nicht nur im Test.

**✅ Die widerlegbare Vorhersage aus Sprint 7 ist eingetroffen.** Der Wächterlauf 05:47 ist
durchgelaufen, hat gepusht, und `CI-STATUS.md` meldet **ALLES GRÜN (15 Abfragen)**. SWR-110
hat `abschluss.cmd` nicht fälschlich angehalten — die Stand-Zeilen-Ausnahme ist damit **am
Bestand** bestätigt. Im selben Lauf hat SWR-110 zweimal korrekt gegriffen und
`platform/tickets/T-0010.md` und `pm/tickets/T-0049.md` als unverbucht gemeldet.

**⚠ Und ein Verschiebungsgrund ist zum dritten Mal in drei Sprints an der Messung
gescheitert.** `pm/T-0038` verlangte wörtlich, „gebündelt mit `pm/T-0036`" ausgeliefert zu
werden. `pm/T-0036` ist seit Sprint 7 **geschlossen** und hat die gemeinsame Fläche **nie**
angefasst — sein Teil b) wurde eine Preflight-Zeile, sein Teil a) ging als `pm/T-0047`
weiter. Der Grund galt zudem nur für **einen** von fünf Teilen und hielt die anderen vier
mit fest. Zerlegt statt erneut verschoben; Teil a) in diesem Sprint gebaut.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `pm/T-0048` — Sprint 9, Frist 23.08. **Grund: dieselbe Fläche, dieselbe Woche, zwei
  Entscheidungen.** Das Ticket verlangt vor dem Bau eine Festlegung, ob die Prüfung die
  **Historie** (`git log` je Ticketdatei) oder den **Commit-Pfad** (`setze_status` erzwingen)
  adressiert — das ist Urteil, kein Fix (B025). Dieser Sprint hat mit SWR-115 bereits eine
  Prüfung derselben Familie gebaut und mit SWR-116 das Ticket-Schema angefasst; eine dritte
  Änderung an der Prüfstrecke im selben Lauf wäre die Bündelung, vor der B025 warnt.
  **⚠ Dies ist die erste Verschiebung dieses Tickets** — bei der zweiten mit demselben Grund
  greift L-2026-08-17j Regel 2 und der Grund wird gemessen.
  **Teilweise entschärft:** `platform/T-0010`, `pm/T-0049` und `pm/T-0038` sind in diesem
  Sprint über den **legalen** Weg mit je drei Commits geschlossen worden — sie erzeugen den
  Fehler also nicht, den `T-0048` beschreibt.
* `pm/T-0047` — Sprint 9, Frist 23.08. **Grund: unverändert Vertragsfrage vor Bau, und ein
  neuer Nachbar.** Der Cockpit-Kopfblock ist eine Formfrage (Block vs. Feld, aus welcher
  Quelle), und mit `pm/T-0051` aus der Zerlegung will jetzt eine **zweite** Zahl an dieselbe
  Stelle. Die Reihenfolge ist im Ticket festgeschrieben: `T-0047` entscheidet die Form,
  `T-0051` ergänzt sie danach. **Zweite Verschiebung mit ähnlichem Grund** — beim nächsten
  Mal wird der Grund gemessen (L-2026-08-17j Regel 2).
* `pm/T-0039` — Sprint 9, Frist 23.08. Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik,
  HMI); mit anderem zusammen wäre es B025. Unverändert.
* `pm/T-0050`, `pm/T-0051` — Sprint 9, **neu aus der Zerlegung**. `T-0050` ist **die**
  Board-Formatänderung und gehört bewusst allein in einen Lauf.
* `pm/T-0052` — Sprint 10, neu aus der Zerlegung (HMI-Kanal).
* `projects/p11/T-0003` — **Status korrigiert statt Termin verschoben.** Es stand auf `open`
  und sah wie unerledigte Teamarbeit aus, obwohl das Team es nicht bewegen kann. Jetzt
  `blocked` mit `blocked_by: [T-0006]`. Frist 20.08. **⚠ Reißt die DR-Frist am 19.08., reißt
  diese einen Tag später mit** — das ist zu beobachten, nicht zu verwalten.
* `pm/T-0028` Sprint 9, `projects/p12/T-0003` Sprint 10 — unverändert in der Reihenfolge.

**Widerlegbare Vorhersage für Sprint 9.** `preflight` hält ab jetzt die Statusspalte gegen
das Ticketfeld und **bricht `abschluss.cmd` in `[1/5]` ab**, wenn beide auseinanderlaufen.
Wenn dieser Abschluss ehrlich geschrieben ist, meldet der nächste Startcheck
`[org] Statusdrift Plan/Ticket: 0` — und **kein** in Sprint 8 als erledigt gemeldetes Ticket
steht dann noch offen. Steht eines offen, ist dieser Abschluss dasselbe gewesen wie der von
Sprint 7, und SWR-115 ist an der falschen Stelle eingebaut.

## Was dieser Sprint über die Planung gelernt hat

**Zum vierten Mal in Folge kam der wertvollste Inhalt aus dem Startcheck** — und zum ersten
Mal war der Befund kein Werkzeugdefekt, sondern **eine Meldung über uns selbst, die nicht
stimmte**. Sprint 7 hat viermal „erledigt" geschrieben und keinmal nachgesehen. Die Frage,
die jetzt in `preflight` steht, ist dieselbe wie die aus Sprint 7 — *ist das Gemeldete das
Verbuchte?* — nur eine Fläche weiter: dort Arbeitskopie gegen HEAD, hier Plantext gegen
Ticketfeld.

**Drei Befunde in drei Sprints haben dieselbe Form.** SWR-110: eine Prüfung misst etwas
anderes, als geliefert wird. `pm/T-0048`: eine Prüfung hängt an der **Reihenfolge** der
Session. SWR-115: eine Prüfung hängt am **Zeitpunkt**. Das ist eine Familie, und sie ist als
L-2026-08-17o Regel 4 benannt. Die Erkennungsfrage für jede neue Prüfung lautet ab jetzt:
*läuft sie vor oder nach dem Zeitpunkt, an dem der Fehler Schaden anrichtet?*

**Und die Regel mit der höchsten Trefferquote hat zum dritten Mal getroffen.**
L-2026-08-17j Regel 2 — den zweimal wiederholten Grund messen — hat in Sprint 6
`platform/T-0008` gekippt, in Sprint 7 `pm/T-0036` und hier `pm/T-0038`. Neu daran ist die
Art des Fehlers: der Grund war nicht bloß leer, er **zeigte auf ein Ticket, das es nicht
mehr gab**, und er galt nur für einen von fünf Teilen. Als L-2026-08-17o Regel 5 ergänzt.

---

## Sprint-Abschluss (Sprint 7, 2026-08-17)

**Geplant beim Start:** 16 nicht geschlossene Aufgaben (Werkzeugzahl nach der in diesem
Sprint festgelegten Zählweise, SWR-113), davon **11 in diesem Sprint** — 5 Sachtickets
(`pm/T-0043`, `team-dashboard/T-0002`, `pm/T-0045`, `pm/T-0046`, `pm/T-0036`) plus 6
Takt-Pflichten. Im Lauf kamen **3** Tickets dazu: `platform/T-0010` (aus dem Startcheck),
`pm/T-0047` (Abtrennung aus `pm/T-0036`) und `pm/T-0048` (aus der Schlussverifikation).

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
* `pm/T-0048` — Sprint 8, **neu und aus der eigenen Schlussverifikation**. Die
  Übergangsprüfung ist blind für einen Sprung, der schon committet ist; zwei Tickets
  dieses Sprints sind so mit `open -> done` in die Historie gegangen. Bewusst **nicht**
  nachträglich geglättet — der Verlauf ist der Vermerk. Nicht mitgebaut, weil vorher zu
  entscheiden ist, ob die Prüfung die Historie oder den Commit-Pfad adressiert (B025).
  ⚠ Zusammenhang mit SWR-110 beachten: die dortige Prüfung drängt auf frühes Committen und
  **zieht diesen Fehler damit an**.
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
| Tickets gesamt | 246 | 248 | 250 | 254 | 258 | **261** |
| nicht geschlossen | 15 ⚠ | 15 ⚠ | 15 ⚠ | 15 ⚠ | 17 (Start: 17) | **15** (Start: 16) |
| davon Sachtickets | — | — | — | — | 11 | **9** |
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
