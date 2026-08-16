# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand 2026-08-16 18:35)

1. **Dein Knopf hat gehalten: P12 ist gestartet, freigegeben und Sprint 0 liegt.** Du hast
   „Markdown-Renderer auch für Briefe/Reports" um 18:03 aus dem Pool gestartet und um **18:04**
   mit **G0a** freigegeben — beides ist verbucht.
2. **Auf dich wartet eine Entscheidung:** `p12/T-0002` (G1, Frist **23.08.**, Default G1a) —
   Anforderungen freigeben und Sprint 1 beauftragen. Drei Punkte sind darin offengelegt, der
   wichtigste: **es gibt keine JS-Teststrecke**, die Prüfung ist Arbeit von Sprint 1, keine Zusage.
3. **Morgen fällig:** `pm/T-0034` (17.08., nur am Host lösbar) — ab morgen greift B044.
4. **Weiterhin für dich:** ein Blick auf die GitHub-Actions-Seiten schließt `pm/T-0010`,
   `T-0013`, `T-0026` (Frist 18.08.).
5. **Werkzeugbefund B051:** Der „Starten"-Knopf hat den Pool-Kandidaten spurlos gelöscht und ein
   Decision-Log ohne Tabellenkopf angelegt. Von Hand behoben, Werkzeugänderung als `pm/T-0037`.

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 18:04–18:35, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — alle
38 Briefe aller Projekte/Teams auf `status: offen` durchsucht, kein Treffer; zweimal geprüft
(Sessionanfang und -ende). Inbox beim Start: `inbox.liste` meldete **leer** — und das war
**falsch im Sinne der Verbuchung**: `p12/T-0001` trug seit **18:04** den Entscheidungsvermerk
**G0a** bei Status `open` (SWR-039/B047, sechster Fund dieser Klasse). Gegen die **DR-Rohdaten**
geprüft, wie es die Ablaufregel aus B047 verlangt — genau dort stand er. **Verbucht.** Am Ende:
ein wartender DR (`p12/T-0002`, von dieser Session vorgelegt), kein unverbuchter.
**Kein überfälliges Ticket**, **Org-Summe „ohne Frist" = 0**; `mail_digest.faellig(1)` und
`faellig(7)` beide `False`. Push: `PUSH-ANFORDERUNG.txt` war beim Start **nicht vorhanden** — die
Zeile der 17:06-Session ist abgearbeitet (Wächter-Erfolg 17:30:26). Diese Session legt sie neu an
(Repos: projects, pm, process, p0).*

**Der Knopf aus `pm/T-0022` ist zum ersten Mal echt gelaufen — und der Lauf war der Prüfstein
(B051).**

Um **18:03** hat der Auftraggeber Technik-Kandidat **#7** aus dem Projekt-Pool gestartet; das
Werkzeug legte `projects/p12` mit Auftragsentwurf, leerem Decision-Log, `steckbrief.yaml` und dem
G0-Antrag `T-0001` an. Um **18:04** kam **G0a**. Beides passierte **vor** dem Beginn dieser
Session — sichtbar wurde es nicht über die Inbox (die filtert entschiedene DRs bauartbedingt
heraus), sondern über die Prüfung gegen die DR-Rohdaten.

**Vollzogen (Klasse C — die Entscheidung war Klasse A und ist gefallen):** Sprint 0 für P12.
Projektauftrag **v1.0** mit sechs messbaren Abnahmekriterien, **STK-022 + SWR-097–101** als
`draft` (B027), Sprint-0-Plan mit **sechs** Risiken, G1-DR `p12/T-0002`. `T-0001` über die
erlaubten Übergänge geschlossen (`open → in_progress → in_review → done`), nicht per
Direktsetzung. **Matrix: 101 SWRs / 0 Lücken** (vorher 96).

**⚠ Der inhaltliche Kern des Projekts wurde in Sprint 0 gefunden, nicht vorausgesetzt.** Es gibt
im HMI **zwei** Textwege, und jedem fehlt genau die Fähigkeit des anderen: `mdRender` (SWR-059/060)
formatiert, kennt aber **keine Ticket-Links**; `preMitLinks`/`tlinks` (SWR-040) verlinkt Tickets,
formatiert aber nichts. Briefe und Reports einfach auf den Renderer umzuhängen hätte die
Ticket-Links **genau dort verloren, wo die meisten stehen** — Reports und DR-Bodys. Deshalb steht
in SWR-098 die Ticket-Erkennung **im Inline-Pass des vorhandenen Renderers**; P12 ist eine
Zusammenführung, kein Anstrich.

**⚠ Was der Antrag ausdrücklich nicht zusagt: die Prüfung.** Die Abnahmekriterien verlangen
Nachweise an JavaScript — die Organisation hat **329 Python-Tests und null JS-Tests**;
„JS-Frontend-Tests" ist Pool-Kandidat **#8** und nicht beauftragt. Das steht als **R5** im Plan und
als Punkt 1 im G1-Antrag: *wie* geprüft wird, ist die erste Entscheidung in Sprint 1 und gehört in
den ADR. Ein „Tests" im Kriterium, aus dem am Ende eine Stichprobe wird, wäre B027/B038.

**⚠ Werkzeugbefund B051 — eine Konvention, die nur von Hand existierte, hat den ersten
Werkzeuglauf nicht überlebt.** Zwei Sachen, beide **lautlos**:

1. **Der Pool-Kandidat wurde gelöscht, nicht verschoben.** Der Diff des Knopf-Commits ist wörtlich
   `1 file changed, 1 deletion(-)`. Den Abschnitt **„Realisiert"** gibt es seit **16:15 desselben
   Tages** — von Hand eingeführt für Kandidat #13 mit der Begründung aus B029 (*ein Kandidat, der
   verschwindet, sieht aus wie einer, den nie jemand wollte*). Der Knopf war da schon gebaut.
2. **Das erzeugte Decision-Log hat keinen Tabellenkopf.** `pool.py` schreibt einen
   Platzhaltersatz, `inbox.entscheide` hängt die D000-Zeile an — ohne Kopf ist das keine Tabelle,
   sondern Pipe-Text, und der Platzhaltersatz behauptet danach weiter, es gebe keine Entscheidung.

Gefunden nur, weil der fremde Commit gegengelesen wurde (B041 Regel 3). **Von Hand sofort
angewandt**, was ohne Code geht: Pool-Zeile unter „Realisiert" nachgetragen, Tabellenkopf im
p12-Log ergänzt (mit Vermerk, append-only gewahrt). **Die Werkzeugänderung ist eingeplant als
`pm/T-0037`** (Klasse B, Frist 23.08.) und **nicht** nebenbei gebaut — eine Änderung an `pool.py`
samt Tests neben dem Vollzug einer Klasse-A-Entscheidung ist genau das Risiko aus B025/B038.

**Kein Code geändert, deshalb keine neuen Tests** — die Arbeit war Vollzug, Anforderungsentwurf
und eine Recherche im Frontend. **329 Tests, Matrix 101 SWRs / 0 Lücken, Katalog- und
Architektur-Gate grün.** Board-Check gegen die Erwartung gelesen (B041 Regel 3): **pm 37 Tickets**
(vorher 36, +`T-0037`), **p12 2 Tickets** (vorher 1, +`T-0002`).

**⚠ Eigener Fehler dieser Session, gefunden und behoben.** Beim Erkunden wurde
`trace_matrix.py` **ohne** `--repos . --alle-projekte` aufgerufen; der Lauf schrieb
`p0/verification/reports/swr-test-matrix.md` auf einen Teilstand (24 SWRs, 56 Lücken) — eine
Datei, die diese Session zu dem Zeitpunkt gar nicht anfassen wollte. Sofort gegengelesen
(`git diff --stat`: 116+/74−), **in-place** aus `git show HEAD:` zurückgeschrieben (`git checkout`
scheitert am `unable to unlink` des Mounts, R7) und mit `git diff --quiet` als bitgleich zu HEAD
belegt, **bevor** irgendetwas committet wurde. Danach der richtige Aufruf: 101 SWRs / 0 Lücken.
**Lehre:** Ein Werkzeug, das Dateien schreibt, ist kein Erkundungsmittel — Erkundung liest.

---

*Vorheriger Stand: 2026-08-16 17:06–17:32, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — alle 36
Briefe aller Projekte/Teams auf `status: offen` durchsucht, kein Treffer; zweimal geprüft
(Sessionanfang und -ende) — die Zweitprüfung fand **zwei neue Briefe**, `pm/N-0028`/`N-0029`
(wortgleich, 15:18:55 und 15:18:56), beide beantwortet. Inbox: beim Check um **17:06** stand
`pm/T-0035` wartend da; der Auftraggeber entschied um **17:17** mitten in der Session mit **AK-b**
— gefunden hat das ebenfalls die Zweitprüfung (B036, fünfter Fund), und zwar als fremde Änderung im
Abschluss-`git status`, nicht über `inbox.liste` (die filtert entschiedene DRs bauartbedingt heraus,
SWR-039/B047). **Verbucht.** Am Ende: gegen die DR-Rohdaten geprüft — **kein `decision-request` mit
Status ≠ `done`**, Inbox leer. **Kein überfälliges Ticket** — frühester Termin ist `pm/T-0034`
(17.08.). `mail_digest.faellig(1)` und `faellig(7)` beide `False`. Push: die Zeile der 16:50-Session
war beim Start **abgearbeitet** (Wächter-Erfolg **17:00:23**); die Zeile **dieser** Session wurde
noch während der Session abgeholt — Wächter **17:29:00 → 17:30:26**, `OK - alles geprueft und
gepusht`, danach alle Repos `ahead 0/behind 0`. Für die letzten Korrektur-Commits liegt eine neue
Zeile bereit (Repos: pm, process).*

**Der „ohne Frist"-Zähler war zum dritten Mal nicht zu Ende gelesen — hinter der pm-Kachel standen
drei Tickets, und bei einem lag die halbe Verifikation seit 07:59:59 im lokalen Log (B049).**

`cockpit_alle` meldete beim Sessionstart **p0 = 1** *und* **pm = 3**. Die 16:15-Session hatte die
pm-Kachel für abgearbeitet erklärt (sie ging von 4 auf **3**, nicht auf 0); die 16:50-Session
erklärte den Zähler für „zu Ende gelesen" und las dabei nur p0. Dahinter: **`pm/T-0010`,
`pm/T-0013`, `pm/T-0026`** — drei `in_review`-Problemtickets ohne Frist, die in **sieben**
Session-Fußzeilen wortgleich als *„bleiben `in_review`, Grund unverändert: kein `gh`/Netzzugriff"*
stehen. Wörtlich das Muster aus **B043**, diesmal an der eigenen Fußzeile.

**Die Eskalationsregel aus B044 kann sie bauartbedingt nicht sehen.** „Überfällig" ist
`board.ist_ueberfaellig`, und das setzt eine **Frist** voraus — ohne Frist ist die Ampel „grau", ein
Ticket ohne Frist wird nie überfällig. Die Regel gegen das Liegenbleiben hat ihren blinden Fleck
genau dort, wo das Liegenbleiben passiert. Einziger Melder ist der `unterminiert`-Zähler, und der
ist eine **Zahl je Kachel**, keine Summe: drei Sessions haben je eine Kachel gelesen und „erledigt"
notiert. Eine Org-Summe hätte jedes Mal ≠ 0 gemeldet.

**⚠ Der schärfste Teil: bei `pm/T-0013` war die halbe Verifikation die ganze Zeit lokal prüfbar.**
Das Ticket hat **zwei** Kriterien, die der alte Vermerk unter einem Satz zusammenfasste. Kriterium 1
— *„`platform` erscheint als erstes Repo in der Push-Ausgabe"* — steht in `abschluss-auto.log`,
einer Datei ohne jeden Netzzugriff: `platform` ist dort seit dem Lauf **07:59:59** in **jedem**
erfolgreichen Wächter-Lauf das erste Repo (13 Läufe, zuletzt 17:00:23; davor, 00:44–07:15, war es
`p0`). Der Vermerk, der den Nachweis für unerreichbar erklärte, nennt selbst *„letzter erfolgreicher
Push 08:30"* — **genau dieser Lauf trug den Beleg bereits.** Auch der Hinderungsgrund von
`T-0010`/`T-0026` (Wächter bricht seit 09:44 ab) ist **seit 10:30 weg**.

**Getan (Klasse C):** Kriterium 1 in `T-0013` mit Zeitstempeln als erfüllt belegt; die überholten
Vermerke in `T-0010`/`T-0026` richtiggestellt; alle drei mit **Frist 18.08.** versehen und der Grund
dafür im Ticket. Gegenprobe zum CR-Kandidaten in `T-0026`: die Repo-Liste in
`platform/.github/workflows/ci.yml` deckt P11 ab (liegt in `projects`) — sie hat gehalten, weil P11
in ein gelistetes Repo gelegt wurde, nicht weil sie sich pflegt. **pm meldet jetzt `unterminiert=0`;
organisationsweit bleibt 1** (`p0/T-0008`, begründet nach B048).

**Warum hier eine Frist keine Behauptung ist (Unterschied zu B048):** `p0/T-0008` wartet auf eine
Entscheidung, die der Auftraggeber zweimal vertagt hat — ein Datum hätte dort einen Termin
behauptet, den niemand zugesagt hat. Diese drei warten auf **einen Blick auf eine Seite, die der
Wächter ohnehin öffnet** ([5/5] seiner Ausgabe). Präzedenzfall: `pm/T-0034` ist ebenfalls nur am
Host lösbar und trägt trotzdem einen Termin.

**Nicht gebaut, eingeplant als `pm/T-0036` (Klasse B, Frist 23.08.):** Org-Summe statt Kachelzahl,
Preflight-Zeile mit den **Namen** der unterminierten Tickets, Ablaufregel *„Kachel X erledigt ist
keine gültige Abschlussmeldung"*. Das ist eine Änderung an der Prüfstrecke selbst (Cockpit-Vertrag +
Preflight-Ausgabe, berührt SWR-091) — nebenbei in einer 30-Minuten-Routine ist das genau das Risiko
aus B025/B038. Von Hand sofort angewandt wurde, was ohne Code geht.

**Fremde Änderung geprüft und übernommen (B041):** `pm/T-0035` trug beim Start eine uncommittete
Zeile **„Benachrichtigt: 2026-08-16 per E-Mail (SWR-033)"** — der Marker aus
`platform/scripts/dr_benachrichtigung.py`, geschrieben vom DR-Mailversand am Host nach der
16:50-Session. Inhaltlich echt und historienwürdig, deshalb **eigener Commit vor der Sessionarbeit**,
damit Fremdes und Eigenes nicht in einer Zeile stehen. Die bekannte `team-mail`-Anzeige
(`digest/2026-08-16-woche-digest.md` erscheint in `git status`, `git diff` ist leer) ist unverändert
der nicht durchlaufende Index-Refresh aus R7 — **erneut geprüft, erneut kein Commit**.

**⚠ Morgen fällig, nur am Host lösbar: `pm/T-0034`** (17.08., hoch) — unverändert. Der Wochendigest
liegt; offen ist, warum Ollama um 15:28 nicht erreichbar war und ob `ASPICE-MailAutopilot`
eingerichtet ist. Kein IMAP/Ollama in dieser Sandbox (Guardrail 2): **kein übergangenes Ticket im
Sinne von B044**, sondern die Grenze der Ausführung.

**Kein Code geändert, deshalb keine neuen Tests** — der Befund war eine Recherche in Log und Tickets.
**329 Tests, Matrix 96 SWRs / 0 Lücken, Katalog- und Architektur-Gate grün.** Board-Check gegen die
Erwartung gelesen (B041 Regel 3): **pm 36 Tickets** (vorher 35, +`T-0036`).

**⚠ Werkzeug-Notiz (R7) — ein Umgehungsweg, der beinahe Arbeit vernichtet hätte. Bitte nicht
wiederholen.** `git status` hinterlässt auf diesem Mount ein `.git/index.lock`, das es nicht mehr
löschen kann („Operation not permitted"); jeder folgende `git`-Aufruf im selben Repo bricht dann mit
„Unable to create index.lock" ab.

**Der falsche Ausweg (in dieser Session versucht):** `GIT_INDEX_FILE` auf eine **Kopie** des Index
zu setzen. Das läuft durch — aber die echte `.git/index` bleibt auf dem alten Stand, und **jede
Datei, die nicht ausdrücklich im `git add` steht, wird aus diesem alten Stand mitcommittet**. Genau
das ist passiert: Der Sammelcommit hat `pm/T-0035` um **26 Zeilen zurückgesetzt** — Status wieder
`open`, Vollzugsvermerk und Benachrichtigungszeile weg. Die Historie hätte danach „T-0035 -> done"
behauptet, während das Ticket wieder offen dastand.

**Gefunden wurde es über die Zahl `-26` in der Diffstat beim Gegenlesen** — B041 Regel 3 („Zahlen aus
Werkzeugausgaben gegen die Erwartung lesen"), zum zweiten Mal an einer Zahl, die in die falsche
Richtung zeigte. Behoben mit einem Korrektur-Commit.

**Der richtige Ausweg:** Locks per **`mv`** nach `.git/verwaiste-locks/` wegräumen (Umbenennen ist
auf diesem Mount erlaubt, Löschen nicht — derselbe Trick wie in `pm/T-0023`), danach **`git reset`**
gegen den echten Index und ganz normale `git add`/`git commit`-Aufrufe. Nie auf einer Indexkopie
committen.

---

*Vorheriger Stand: 2026-08-16 16:50, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — alle 37
Briefe aller Projekte/Teams auf `status: offen` durchsucht, kein Treffer; zweimal geprüft
(Sessionanfang und -ende). Inbox: **leer beim Start und beweisbar nichts Unverbuchtes** —
erstmals nach der neuen Ablaufregel aus B047 gegen die **DR-Rohdaten** geprüft: es existiert
**kein einziger `decision-request` mit Status ≠ `done`**, die Klasse „entschieden, aber nicht
verbucht" ist damit leer und nicht nur laut `inbox.liste`. **Kein überfälliges Ticket** —
frühester Termin ist `pm/T-0034` (17.08.). `mail_digest.faellig(1)` und `faellig(7)` beide
`False`, nichts fällig. Push: die Zeile der 16:15-Session in `PUSH-ANFORDERUNG.txt` (16:32) war
beim Sessionstart **noch unverarbeitet** (letzter Wächter-Erfolg damals 16:30:26) und ist
**während dieser Session abgearbeitet worden** — der Wächter startete **16:44:00** und meldete
**16:45:25** `OK - alles geprueft und gepusht`; `pm` ist danach nur noch um den Commit dieser
Session voraus. Diese Session hängt eine neue Zeile für ihre eigenen Commits an (pm, p0).
`pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein `gh`/Netzzugriff
in dieser Sandbox — bitte am Host/Browser gegenprüfen).*

**Der „ohne Frist"-Zähler ist zu Ende gelesen — die p0-Kachel war noch offen (B048).** Die
Vorsession hatte den Zähler aus SWR-091 **nur für die pm-Kachel** abgearbeitet (`pm/T-0003` bekam
sein `takt`-Feld); `cockpit_alle` meldet für **p0 unverändert `unterminiert=1`**. Dahinter steht
`p0/T-0008` (Anthropic-API-Key, `open`, `prio: hoch`, ohne Frist, erstellt **05.08.**) — das
**einzige offene Ticket in zwei abgeschlossenen Projekten** (P0 `genesis-v1.0`, P1 `p1-v1.0`).

**Es ist nicht liegengeblieben, sondern zweimal ausdrücklich vertagt** — `p0/D008` und `p0/D015`,
im P0-Abschlussbericht als Kriterium 9 „teilweise" mit Backlog-Punkt **B9** abgenommen, als Epic
**P1-E5** weitergereicht („optional nach Budgetfreigabe"). **Nur stand davon nichts im Ticket.**
Wer es heute öffnet, liest eine elf Tage alte hochpriorisierte Sprint-1-Aufgabe ohne Termin — das
Muster aus **B043**, diesmal nicht durch Vergessen, sondern weil der Kontext in drei anderen
Dokumenten liegt. Der Zähler kann das nicht unterscheiden: er zählt „ohne Frist", er liest keine
Decision-Logs.

**Und der Zwilling ist längst entschieden.** P0-Kriterium 9 hatte **zwei** Betriebsreste, beide
als P1-E5 weitergereicht: der **Copilot-Lauf** ist als `p0/T-0072` **und** `p1/T-0018`
**rejected** — der **Claude-API-Tick** blieb `open`. Zwei gleichrangige Reste desselben
Kriteriums, einer geschlossen, einer nicht. Das ist der Kern des Befunds, nicht die 20 €.

**Getan (Klasse C):** Belegkette (D008, D015, Kriterium 9/B9, P1-E5) und die Begründung für die
fehlende Frist stehen jetzt **im Ticket selbst** — die nächste Session muss nicht neu
recherchieren. **Status unverändert `open`.**

**Nicht getan (Klasse A):** über das Ticket entschieden. Ein API-Key ist eine Budget- und
Zugangsfreigabe (Playbook Kap. 16) — **in beide Richtungen**: ihn anzulegen ist eine
Geldentscheidung, ihn abzuräumen eine Scope-Entscheidung über ein Abnahmekriterium. Vorgelegt als
**`pm/T-0035`** (AK-a jetzt umsetzen / **AK-b schließen wie den Zwilling** / AK-c offen lassen mit
Frist; Frist **23.08.**, Default **AK-b**). **Default AK-b, weil Schweigen nie in Richtung
Geldausgabe oder neuer Credentials laufen darf** — und weil AK-c der dritte Aufschub wäre.

**Eine Frist hat das Ticket bewusst nicht bekommen.** Es wartet nicht auf Arbeit des Teams,
sondern auf eine Entscheidung, die der Auftraggeber zweimal vertagt hat; ein von der Session
gesetztes Datum hätte einen Termin behauptet, den niemand zugesagt hat (B038-Familie). Die Frist
trägt der Antrag, nicht das Ticket.

**⚠ Morgen fällig, nur am Host lösbar: `pm/T-0034` (Frist 17.08., Priorität hoch).** Der
Wochendigest **liegt** seit der 16:15-Session (`faellig(7)` = `False`), offen ist der eigentliche
Befund: Warum war Ollama um 15:28 nicht erreichbar, und läuft `ASPICE-MailAutopilot` überhaupt?
Diese Session kann daran nichts tun (kein IMAP/Ollama, Guardrail 2) — **das ist kein übergangenes
Ticket im Sinne von B044**, sondern die Grenze der Ausführung; der Grund steht hier und im Ticket.
Reißt die Frist morgen, ist es der erste Arbeitspunkt der nächsten Session **am Host**.

**Sonst nichts angefasst.** Kein Code geändert, deshalb keine neuen Tests — der Befund war eine
Recherche in vorhandenen Dokumenten und ein Antrag. **329 Tests, Matrix 96 SWRs / 0 Lücken,
Katalog- und Architektur-Gate grün.** Board-Check nach dem Schreiben: **pm 35 Tickets** (vorher 34
— gegen die Erwartung gelesen, Lesson B041 Regel 3), p0 72 unverändert.

---

*Stand davor: 2026-08-16 16:15, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — alle
27 pm-Briefe und die Briefkästen aller Projekte/Teams auf `status: offen` durchsucht, kein Treffer;
zweimal geprüft (Sessionanfang und -ende). Inbox: **zwei Klasse-A-Entscheidungen verbucht**
(`pm/T-0033` → D007/G0a, 15:55 · `p11/T-0002` → p11/D001/G1a, 16:07 — letztere fiel **51 Sekunden
nach** dem Commit, mit dem das Projekt entstand). Push: `PUSH-ANFORDERUNG.txt` aus der
15:35-Session war beim Start **bereits abgearbeitet** (Wächter-Erfolg **15:45:30**, Log
`OK - alles geprueft und gepusht`) — diese Session schreibt am Ende eine neue Zeile für ihre
eigenen Commits.
`pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein `gh`/Netzzugriff
in dieser Sandbox — bitte am Host/Browser gegenprüfen).*

**Projekt P11 „Widget-Dashboard" ist angelegt und hat G1 — beides in dieser Session (B047).**
`projects/p11` (Sammel-Repo, `pm/D003`) mit Projektauftrag v1.0 (fünf messbare Abnahmekriterien,
Abgrenzung), `steckbrief.yaml`, README, Decision-Log **D000**; **STK-021 + SWR-092–096 als
`draft`** (B027 — die Freigabe beauftragt das Projekt, sie verifiziert keine Anforderung), Matrix
**96 SWRs / 0 Lücken**; Sprint-0-Plan mit fünf Risiken; G1-DR `p11/T-0002` vorgelegt und **schon
entschieden** (G1a). Erstes Projekt der Organisation mit einem **Team** als fachlichem
Auftraggeber (`team-dashboard`).

**⚠ Befund am Werkzeug (B047): Ein entschiedener, aber noch nicht verbuchter DR ist in der Inbox
unsichtbar.** `inbox.liste` meldete `{"inbox": []}`, während `pm/T-0033` seit 15:55 entschieden
dalag — `_dr_tickets` filtert jeden DR mit Entscheidungsvermerk heraus (SWR-039). Für die Inbox
ist das richtig (dort steht, was **wartet**), als Verbuchungsprüfung taugt sie damit nicht.
Gefunden nur, weil die Agenda `pm/T-0033` namentlich als „wartend" nannte und **gegen die
Rohdaten** geprüft wurde — fünfter Beleg für B025. **Regel für den Ablauf:** Die Inbox-Prüfung
beantwortet „was wartet?", **nicht** „was ist entschieden und noch nicht verbucht?". Letzteres
wird gegen die DR-Tickets selbst geprüft (`grep "**Entscheidung ("` über die `decision-request`-
Tickets mit Status ≠ `done`) — bis ein Werkzeug das kann.

**⚠ Zweiter Befund, unbehoben und als CR vermerkt (B047): `blocked_by` reicht nicht über
Repo-Grenzen.** `p11/T-0003` (Sprint 1) sollte `blocked` sein — die Sperre ist der Widget-Vertrag
`team-dashboard/T-0001`. `board.py` verlangt zu `blocked` einen `blocked_by`-Verweis und prüft ihn
gegen die IDs **desselben** Repos. Eine Abhängigkeit *Projekt wartet auf Team* lässt sich damit
nicht ausdrücken; sie ist mit `team-dashboard` als fachlichem Auftraggeber zum ersten Mal
entstanden. Ein erfundener p11-interner Verweis hätte das Feld gefüllt und eine Sperre behauptet,
die es nicht gibt (B038-Familie) — deshalb `open` mit der Ursache im Klartext und **Frist 30.08.**
Der CR steht im Betriebs-Backlog, nicht nebenbei gebaut.

**Erledigt: `pm/T-0003` hat sein `takt`-Feld** (`je-session`). Der Agenda-Auftrag der Vorsession
lautete „Feld setzen oder begründen, warum keins". Der Beleg stand im Ticket selbst: *„prüft je
Routine-Session"*. Der Titel („je Sprint/Durchlauf") nennt den **Anlass**, `takt` den **Rhythmus
des Aufgreifens** — die Verwechslung war der Grund für das Zögern der Vorsession. Was `TAKTE`
weiterhin nicht kann, ist ein **ereignisgebundener** Takt; das gehört zu `pm/T-0032` (Frist 19.08.)
und nicht in ein drittes Taktvokabular nebenbei (B033).

**⚠ Beobachtung, nicht behoben — ein Testlauf war einmal rot und die Namen sind weg.** Der
Abschluss-Preflight um ~16:20 meldete `[platform] Unit-Tests: ROT — FAILED (failures=4)`. **Sechs
direkt anschließende Läufe der Suite waren grün** (je 329 Tests), ebenso zwei weitere
Preflight-Läufe — nicht reproduzierbar. **Untersuchen ließ es sich nicht:** `preflight.unit_tests`
schneidet die Ausgabe auf die **letzten drei Zeilen** zu; bei einem roten Lauf sind das genau die
Zusammenfassung — die `FAIL:`-Zeilen mit den Testnamen stehen weiter oben und werden verworfen.
Damit meldet Preflight einen Fehlschlag zwar sichtbar, aber **unbrauchbar**: dieselbe Familie wie
B038, eine Stufe später („wo wird ein Fehlschlag sichtbar" ist beantwortet, „womit lässt er sich
verfolgen" nicht). **CR-Kandidat:** bei `returncode != 0` die `FAIL:`/`ERROR:`-Zeilen mit
ausgeben statt nur den Tail. **Zweimal aufgetreten** (beide Male in einem Preflight-Lauf direkt
nach einem `git commit`, nie in einem nackten Suite-Lauf) — das stützt den Verdacht auf **parallele
Git-Aktivität** gegen einen nicht vollständig hermetischen Test (B038, dritter Teil; Kandidaten
sind der Push-Wächter alle 15 Min und die von Git nach einem Commit gestartete
Hintergrund-`maintenance`).

**Eine naheliegende Spur ist bereits ausgeschlossen — bitte nicht noch einmal verfolgen:**
`TestLockArtefakte` hat **genau vier** Tests und ist als einzige Klasse in `test_preflight.py`,
die `git_prozess_aktiv` **nicht** in `setUp` festnagelt — die Zahl passte verdächtig gut zu
`failures=4`. **Nachgestellt mit erzwungenem `git_prozess_aktiv → True`: alle vier bleiben grün.**
Die Klasse ist gegenüber laufenden Git-Prozessen hermetisch, die Übereinstimmung der Zahl ist
Zufall. **Bewusst nicht auf Verdacht repariert:** Ohne die Testnamen wäre jede Änderung geraten,
und ein Eingriff in die Prüfstrecke auf Verdacht ist genau das, wogegen B025/B038 geschrieben
sind. Der erste Schritt ist der CR oben (Fehlerzeilen durchreichen) — danach hat der nächste rote
Lauf einen Namen. Verwandt mit `pm/T-0010` (board-check-Flake).

**Fremde Änderung in `team-mail` geprüft und aufgelöst (B041, Regel 1+2).** Preflight meldete beim
Sessionstart „Arbeitskopie nicht sauber (1 Datei)" an `digest/2026-08-16-woche-digest.md` — einer
Datei, die diese Session nie angefasst hat. Geprüft statt verworfen und statt übernommen: Der Diff
umfasst **zwei Zeilen mit identischem Text**, Unterschied ausschließlich **CRLF statt LF**; ohne
Zeilenenden ist der Inhalt bitgleich (`md5sum` gegengeprüft). Herkunft: der Zustellschritt am Host,
der um 15:45 den Zustellvermerk geschrieben hat (Commit `67a20f1`) und die Datei danach mit
Windows-Zeilenenden zurückgelegt hat. Zurückgesetzt **in-place** — `git checkout` scheiterte am
bekannten `unable to unlink` des Mounts (R7), das Überschreiben ohne Löschen ist derselbe Ausweg
wie in `pm/T-0023`. `git diff` ist jetzt leer (Exit 0); `git status` zeigt die Datei weiterhin als
geändert, weil der Index-Refresh mangels Schreibrecht auf `.git/index` nicht durchläuft — eine
Anzeige, kein Inhalt. **Kein Commit dafür**: Ein Commit über null inhaltliche Änderung wäre eine
Zeile Historie, die etwas behauptet, das nicht stattgefunden hat.

**Pool-Kandidat #13 ist aus der Kandidatenliste heraus** — nicht gelöscht, sondern in einen neuen
Abschnitt **„Realisiert"** verschoben, mit dem Weg (Team `team-dashboard` + Projekt P11) und den
Belegen. Ein Kandidat, der einfach verschwindet, sieht aus wie einer, den nie jemand wollte
(B029). Die Nummernvergabe bleibt unberührt (nächste freie Nummer: 14).

---

*Vorheriger Stand: 2026-08-16 15:35, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — zweimal
geprüft (Sessionanfang und -ende), alle 36 Briefe `beantwortet`. Inbox: **eine Entscheidung fiel
während der Session** (`pm/T-0031` → D006/TG-a, 15:21) und ist verbucht; danach steht dort **ein
neuer wartender Klasse-A-Entscheid**, den diese Session vorgelegt hat (`pm/T-0033`, G0 für P11).
Push: `PUSH-ANFORDERUNG.txt` aus der 14:50-Session war beim Start **noch unverarbeitet** (letzter
Wächter-Erfolg 14:30:22) — diese Session hängt eine weitere Zeile an. `pm/T-0010`, `pm/T-0013`,
`pm/T-0026` bleiben `in_review` (Grund unverändert: kein `gh`/Netzzugriff in dieser Sandbox —
bitte am Host/Browser gegenprüfen).*

**`pm/T-0030` ist ERLEDIGT (Teil 1, SWR-091) — das Ticket, das gegen das Liegenbleiben gebaut
wurde, war selbst der oberste liegengebliebene Punkt.** Die Session war frei (kein Brief, kein
entschiedener DR beim Start), und `T-0030` stand oben auf der Agenda; es ein sechstes Mal
weiterzureichen wäre die Wiederholung genau des Befunds gewesen, den es beschreibt (B043).
Geliefert: `frist` gilt für **jeden** Tickettyp und wird für jeden geprüft (bisher nur im
`decision-request`-Zweig — ein Tippfehler in der Frist eines CR fiel lautlos auf „keine Frist"
zurück); die Ampel-Regel liegt **einmal** in `board.frist_ampel` und wird von DR-Fristen und
Backlog-Fristen geteilt (sie stand inline im Cockpit; ein Test vergleicht alt und neu einen Monat
lang Tag für Tag); `board.ist_ueberfaellig` gilt nur für offene Tickets; die Cockpit-Kachel zeigt
überfällige Tickets **vollständig und vor den Statuszahlen** samt „n Tage über" plus einen Zähler
„n ohne Frist". Nebenbefund mitbehoben: `DATUM_MUSTER` prüfte nur die Form — „2026-13-01" kam
durch und hätte als **„grau" = keine Frist** gegolten, ein falsch terminiertes Ticket hätte wie
ein unterminiertes ausgesehen. **11 neue Tests, Gesamtsuite 329** (vorher 318), Matrix **91 SWRs /
0 Lücken**, Katalog- und Architektur-Gate grün, **Gegenprobe gegen den Altstand geführt** (3 Tests
scheitern dort nachweislich). **Das BOARD.md-Format blieb bewusst unangetastet** — eine neue
Spalte ist eine Formatänderung, und genau die hat heute früh alle board-check-Workflows rot
gemacht (`pm/T-0013`).

**Eskalationsregel festgelegt (B044) — das war die offene Frage in `T-0030`:** Ein überfälliges
Backlog-Ticket ist der **erste Arbeitspunkt der nächsten Routine-Session nach dem Briefkasten**,
vor jeder neuen Fläche. Nimmt eine Session es trotzdem nicht auf, **schreibt sie den Grund beim
Ticket in die Agenda** — nicht als Randnotiz. Ab dem **zweiten** übergangenen Mal geht ein Vermerk
an den Auftraggeber. Sofort angewandt statt nur gebaut: `pm/T-0028` (Frist 23.08.), `pm/T-0032`
(19.08.), `pm/T-0034` (17.08.).

**`team-dashboard` ist gegründet — D006/TG-a kam um 15:21 herein, mitten in dieser Session
(B045).** Der erste Inbox-Check um 15:11 hatte den DR noch als wartend gemeldet; gefunden hat die
Entscheidung die **Zweitprüfung aus B036** — der vierte Fund dieser Regel, diesmal an einem
Klasse-A-Entscheid, der sonst 30 Minuten unverbucht geblieben wäre. Vollzogen sind alle vier
Schritte aus `pm/T-0031`: Repo `team-dashboard` aus dem Template (Charter v1.0, `team.yaml`,
`steckbrief.yaml`, Decision-Log mit D000, board-check grün, **lokal ohne Remote** — bewusst **kein**
`.kein-remote`, denn `intern` erlaubt einen Remote, er fehlt nur, weil GitHub-Repo/Secret/PAT
Handlungen des Auftraggebers sind); Registry-Eintrag; erstes Takt-Ticket `team-dashboard/T-0001`
(**Widget-Vertrag entwerfen**, `takt: je-session`, Frist 23.08.) — die Voraussetzung aus dem
Kandidat-Text („Die Projekte haben eine Widget Kompatibilität") existiert nicht und ist damit die
eigentliche erste Arbeit; und der **getrennte G0-DR `pm/T-0033` für Projekt P11** (Dashboard-Bau,
Optionen G0a–G0c, Frist 23.08., Default G0a). **Die Mail-Widget-Auflage steht dreimal im
Klartext** — in `team.yaml`, im Charter und in der Registry: `team-mail` ist `sensibel`, gerendert
wird nur zur Laufzeit hinter dem PIN-Lesegate, und der erste committete Digest-Inhalt macht
`team-dashboard` `sensibel` und kostet den GitHub-Remote.

**Neuer Befund in eigener Sache: `pm/T-0034` — der team-mail-Wochendigest stand fünf Sessions
lang als unveränderte Randnotiz in Punkt 3.** `mail_digest.faellig(7)` meldet seit der
11:21-Session `True`, eine `-woche-`-Datei existiert bis heute nicht, und die Sessions 11:45,
12:16, 14:05, 14:50 haben jeweils „unverändert offen" notiert. Das ist wörtlich das Muster aus
B043 — deshalb ist es jetzt ein Ticket mit **Frist 17.08.** und Priorität hoch statt einer
Agendazeile. Lösen kann es nur der Host (kein IMAP/Ollama hier, Guardrail 2); der kürzeste Weg
steht im Ticket.

---


*Vorheriger Stand (14:50-Session, komprimiert): Ein neuer Brief `pm/N-0027` („starte mit der
initialiserung von team-dashboard aus dem projekt-pool") — angefangen, aber bewusst nicht
vollzogen: Team-Gründung ist Klasse A, deshalb Steckbrief formuliert und Gründungs-DR `pm/T-0031`
in die Inbox gestellt (Optionen TG-a–TG-d, Frist 23.08., Default TG-a) mit drei Befunden im
Antrag (Mail-Widget berührt Guardrail 2; Bauen ≠ Verwalten → Empfehlung eigenes Projekt P11;
„vom Handy aus dem Internet" kollidiert mit Runbook Kap. 10). **Der Auftraggeber hat am 16.08.
um 15:21 mit TG-a entschieden — vollzogen in der 15:35-Session, siehe oben.** `pm/T-0025`
ERLEDIGT (SWR-090, Sofort-Knopf sagt vorher womit er läuft und hinterher was entstanden ist;
8 Tests, Suite 318, Matrix 90/0, am echten System gelaufen).*

*Vorheriger Stand: 2026-08-16 14:05, Routine-Session (D004, alle 30 Min). Briefkasten: **drei neue
Briefe** seit der 12:16-Session — `pm/N-0024` (12:05) lag beim ersten Check bereits vor;
`pm/N-0025` (12:08) und `pm/N-0026` (12:10) gingen **während** der Session ein und wurden erst
bei der Zweitprüfung gefunden (Lesson B036, drittes Mal bestätigt). Alle drei beantwortet,
dritte Prüfung: leer. Inbox: unverändert leer (37 DRs, alle `done`) — kein neuer Kandidat
gestartet. Push: `PUSH-ANFORDERUNG.txt` aus der 12:16-Session war beim Start bereits
abgearbeitet — diese Session schreibt am Ende eine neue Zeile für ihre eigenen Commits.
`pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein
`gh`/Netzzugriff in dieser Sandbox — bitte am Host/Browser gegenprüfen).

**`pm/N-0024` sofort geliefert (`pm/T-0029`, SUP.9, zweite Korrektur an SWR-088):** „Quelle:
1-4000 Zeichen ... reicht auch nicht aus" — selbst die in `pm/T-0027` auf 4000 Zeichen
angehobene Grenze war für ein reales „Quelle"-Feld zu eng. Statt einer dritten geratenen Zahl
diesmal die Ursache behoben: `FELD_MAX` 4000 → 200 000 (technische Notbremse, keine
Inhaltsgrenze mehr) — hart verboten bleibt weiterhin nur `|`. HMI: „Nutzen"/„Voraussetzung"/
„Quelle" jetzt ebenfalls `<textarea>` statt einzeiliger Eingabe (alle drei laufen durch
dieselbe Prüfung, sonst wäre der nächste Brief zur nächsten Spalte fällig gewesen). 1 neuer
Test, Gesamtsuite **310** (vorher 309), Matrix weiterhin **89 SWRs / 0 Lücken**, Katalog-/
Architektur-Gate geprüft und grün. Klasse C — kein Decision-Log-Eintrag nötig (analog T-0027).

**`pm/N-0025` beantwortet — BEFUND in eigener Sache (B043, `pm/T-0030`):** Vorwurf „offene
Aufgaben werden nicht erledigt/terminiert" trifft zu, belegt an `pm/T-0025` (offen seit
10:40-Session, fünf Routine-Sessions nicht aufgegriffen). Zwei strukturelle Lücken: Backlog-
Tickets (CR/Problem) haben kein Fristfeld; „wiederkehrend" kennt keine feste Uhrzeit, nur „je
Sessionlauf". Nicht sofort gebaut (Entwurfsentscheidung mit Wirkung auf F14/alle Tickets —
B025/B038-Risiko eines zu schnell gebauten Werkzeugs) — als `pm/T-0030` für eine Design-Session
eingeplant. Sofort umgesetzt: `pm/T-0025` Priorität mittel → hoch.

**`pm/N-0026` beantwortet — einfache Statusfrage:** Ja, P9 ist abgeschlossen (G4a/D002,
Baseline `p9-v1.0`), kein offenes Ticket. Nur die drei Betriebs-Stichproben aus `p9/T-0004`
bleiben offen (Betriebsnachweis des Auftraggebers, kein Blocker).

*Vorheriger Stand (12:16-Session, komprimiert): Briefkasten hatte zwei neue Briefe
(`pm/N-0022`, `pm/N-0023`), beide beantwortet. `pm/N-0023` sofort geliefert als `pm/T-0027`
(SUP.9-Korrektur an SWR-088, `FELD_MAX` 200 → 4000). `pm/N-0022` (Team-Gründung im Pool) als
`pm/T-0028` (CR, `open`) für eine dafür vorgesehene Session eingeplant, bewusst nicht gebaut —
Klasse-A-Fläche mit Datenklassen-Wirkung. Inbox leer, 309 Tests, Matrix 89/0.*

---

*Vorvoriger Stand: 2026-08-16 12:16-Session, ausführlich. Briefkasten: **zwei neue Briefe**
seit der 11:45-Session — `pm/N-0022` (09:59, aber erst 11:59 committet) und `pm/N-0023` (10:05,
erst 12:05 committet) —, zweimal geprüft (Sessionanfang und -ende, Lesson B036), beide
beantwortet. Inbox: unverändert leer (37 DRs, alle `done`) — kein neuer Kandidat gestartet.
Push: `PUSH-ANFORDERUNG.txt` aus der 11:45-Session war beim Start bereits abgearbeitet
(Wächter-Erfolg 12:00:22) — diese Session schreibt am Ende eine neue Zeile für ihre eigenen
Commits. `pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein
`gh`/Netzzugriff in dieser Sandbox — bitte am Host/Browser gegenprüfen).

**`pm/N-0023` sofort geliefert (`pm/T-0027`, SUP.9-Korrektur an SWR-088):** „Projekt-Pool:
1-200 Zeichen, keine Zeilenumbrüche" war zu eng für den Zweck des Feldes — bei
Technik-Kandidaten trägt der Kandidat-Text die ganze Aufgabe, bei Team-Kandidaten die
Kurzbeschreibung, beides sollte mehrsätzig (auch KI-formuliert) sein dürfen. `FELD_MAX`
200 → 4000, Zeilenumbrüche werden jetzt zu Leerzeichen normalisiert statt die Eingabe
abzulehnen (`pool._text_bereinigen`) — hart verboten bleibt nur `|` (sprengt die
Markdown-Tabellenzeile). HMI: Kurzbeschreibung/Kandidat-Text jetzt `<textarea>` statt
einzeiliger Eingabe. **Bewusst nicht angefasst:** `kandidat_starten` prüft weiter hart auf
`|`/`"`/Zeilenumbruch (Text landet dort im Ticket-YAML) — Bestandsverhalten aus `pm/T-0022`.
4 neue/geänderte Tests, Gesamtsuite **309** (vorher 305), Matrix weiterhin **89 SWRs / 0
Lücken** (kein neuer SWR), Katalog-/Architektur-Gate geprüft und grün.

**`pm/N-0022` — Team-Gründung im Pool beauftragt, aber bewusst nicht in dieser Session
gebaut (`pm/T-0028`, CR, `open`):** Der Brief nennt selbst den Unterschied zu „Projekt
starten" („bei team-steuer/team-trading hängt daran mehr als ein Ordner"). `intake.md`
verlangt für eine Team-Gründung einen vollen Steckbrief (Auftrag, Profil, Rollen,
**Datenklasse**, Zugänge, Grenzen), Repo aus Template statt Ordner-Skelett, bei `sensibel`
ausdrücklich keinen GitHub-Remote — Klasse A mit Datenklassen-Wirkung (Playbook Kap. 16).
Das als Formular in einer Routine-Session ohne Rückfrage zu entwerfen, ist genau das
Risiko aus B025/B038 (ein zu schnell gebautes Werkzeug täuscht Sicherheit vor, die es
nicht hält) — deshalb als eigenes, für eine dafür vorgesehene Session eingeplantes Ticket
angelegt statt durchgezogen. Zweiter Teil des Briefs („Löschen von Kandidaten bleibt
Session auf Zuruf") ist eine Festlegung, keine Anfrage — bestätigt, keine Code-Änderung.

*Vorheriger Stand (11:45-Session, komprimiert): Briefkasten/Inbox clean, `pm/T-0022` Teil 2
„Starten" geliefert (SWR-089, Variante A, nur Technik-Kandidaten, 20 Tests, Matrix 89/0) —
Ticket damit komplett (beide Teile `done`). Push-Wächter 11:00 erfolgreich. 305 Tests
(vorher 285). team-mail-Befund unverändert (siehe Punkt 3).*

---

*Vorheriger Stand: 2026-08-16 10:23, Routine-Session (D004, alle 30 Min). **BEFUND: Der Auto-Push stand seit 09:44 still — bemerkt hat es der Auftraggeber, nicht die Automatik (B038, `pm/T-0024`).** Sein Brief `pm/N-0021` fragte, warum ein paar pm-Tickets „seit längerem in review" stehen. Der Grund lag nicht bei den Tickets: `pm/T-0010` und `pm/T-0013` warten beide auf einen grünen GitHub-Actions-Lauf, und der Wächter brach dreimal in Folge ab (09:44, 09:59, 10:14); letzter erfolgreicher Push **08:30**. Liegengeblieben waren **21 Commits** und die Baseline-Tags `p10-v1.0` — die Abnahme des zehnten Projekts existierte auf GitHub nicht. Ursache: `git_prozess_aktiv()` las die `tasklist`-Ausgabe im falschen Codec und meldete ausgerechnet dann „Git läuft", wenn **keiner** lief (das `ü` in „ausgeführt" ist in CP850 das Byte 0x81); dazu ein nicht hermetischer Test, der den ganzen Rechner nach Git-Prozessen fragte, um ein Fake-Repo in %TEMP% zu prüfen. Beides behoben, 4 neue Tests, Gegenprobe gegen den alten Code (2 scheitern dort) und der Abbruch von 10:14 exakt nachgestellt. **267 Tests, Matrix 87/0, 0,00 € API.** `pm/T-0010` und `pm/T-0013` bleiben bewusst `in_review` mit Vermerk — ein Fremdnachweis wird nicht dadurch erbracht, dass jemand nachfragt (B025). Briefkasten: **zwei** Briefe beantwortet — `pm/N-0021` (Push-Befund) und `team-mail/N-0002`; letzterer kam um **10:17 herein, also nach dem Check am Sessionanfang**, und wurde nur durch die Zweitprüfung aus B036 gefunden — zweiter Fund in zwei Sessions. **Zu N-0002 ein echter Fehler (B040/B041, `team-mail/T-0003`): „Jetzt zusammenfassen" lief fest auf einen Tag, obwohl das Team auf `takte: [7]` (wöchentlich) steht** — jeder Klick erzeugte einen Tages- statt des konfigurierten Wochen-Digests, ohne Fehlermeldung, erkennbar nur am Dateinamen. Behoben (`jetzt_takte`), Regressionstest mit Gegenprobe (`[1] != [7]`). Der KI-Hinweis wirkte dort übrigens die ganze Zeit — er war nur nirgends sichtbar. **Dabei sind zwei Routine-Sessions kollidiert** (B041): Die parallele Session hatte denselben Befund gefunden und ihre Arbeit dann selbst zurückgezogen; ohne den Board-Check (2 statt 3 Tickets) wäre er verschwunden und die Brief-Antwort hätte auf ein nicht existierendes Ticket verwiesen. Sonst keine offenen Briefe (alle 28 geprüft). **268 Tests.** Inbox: leer — gegen die Rohdaten geprüft, alle 38 DR-Tickets stehen auf `done` (Lesson B025). team-mail-Takt: Tages-Digest 2026-08-16 liegt zugestellt vor, nichts fällig. **`pm/T-0022` blieb liegen (B039) — Reihenfolge, nicht Zeitmangel: solange nichts nach außen geht, erzeugt jede Feature-Session unsichtbare Arbeit.** Reihenfolge für die nächste Session:*

**⚠ Zweiter Befund derselben Session (B042, `pm/T-0026`) — und der erste hat ihn verdeckt gehalten:** Der Auftraggeber meldete um 10:36 einen **roten CI-Lauf** (`platform/N-0006`). Nachgestellt: mit `projects` **87 SWRs / 0 Lücken**, mit der Repo-Liste aus `ci.yml` **82 / 5 Lücken → exit 1**. `ci.yml` checkt `projects` **nicht** aus — seit `pm/D003` liegen Projekte aber als Ordner darin, P10 hat dort SWR-077–081. Rot ist der Workflow **seit der P10-Freigabe um 08:18**; sichtbar wurde es erst, als der Push um 10:30 wieder lief. Behoben (Checkout ergänzt), bleibt `in_review` bis ein grüner Lauf vorliegt. **Handlung des Auftraggebers nötig:** `P0_READ_TOKEN` muss `DiOflOrds/projects` einschließen, sonst scheitert künftig der Checkout statt des Matrix-Schritts.

**Zuerst nachsehen, ob der Push wieder läuft:** `PUSH-ANFORDERUNG.txt` verschwunden und in `abschluss-auto.log` `OK - alles geprueft und gepusht`? Wenn ja, sind damit auch `pm/T-0010` und `pm/T-0013` fällig zum Schließen (grüne board-check-Actions prüfen). Wenn nein: **nicht weiterbauen**, sondern die Abbruchstelle im Log lesen — der Grund steht dort immer, nur liest ihn ohne Anlass niemand.

*Erledigt (11:21-Session): Ja, der Push lief wieder — `PUSH-ANFORDERUNG.txt` war bereits weg, Log zeigt `OK - alles geprueft und gepusht` um 11:00:10. Die grünen board-check-Actions selbst kann diese Cowork-Sandbox nicht einsehen (kein `gh`, kein Netzzugriff auf github.com) — `pm/T-0010`/`pm/T-0013`/`pm/T-0026` bleiben deshalb bewusst `in_review`, bitte am Host/Browser gegenprüfen und dann schließen.*

---

*Vorheriger Stand: 2026-08-16 10:05, Routine-Session. **P10 Sprint 1 ist gebaut und liegt zur Abnahme (B033/B034).** Der Lock-Fallback aus `pm/T-0023` hat beim Start gearbeitet (Meldung „weggeräumt nach `.git/verwaiste-locks/`" in 15 Repos) — ohne ihn wäre auch diese Session blockiert gewesen. Geliefert: ADR-007 (zweiter Schreibpfad auf Tickets, Regeln bleiben in `board.py`, Fingerabdruck statt Sperre), `backend/tickets.py` als Fassade, `GET /api/ticket/editor` + `POST /api/ticket`, Editor-Ansicht, Label-Pillen und Label-Filter im HMI; SWR-077–081 **einzeln** auf `reviewed` mit ihrem jeweiligen Nachweis (B027 eingehalten). **263 Tests, Matrix 87/0, 0,00 € API.** Nebenbefund mitbehoben: die Zeitstempel-Formatierung (SWR-084) lag doppelt vor — `inbox.entscheidungszeitpunkt` delegiert jetzt an `board.zeitpunkt`. **G4 nicht selbst abgenommen:** `p10/T-0004` liegt als DR in der Inbox (Frist 23.08., Default G4a), Baseline `p10-v1.0` bleibt bis dahin ungesetzt. Briefkasten: keine offenen Briefe (alle 25 auf `beantwortet` geprüft). Inbox: **eine** wartende Entscheidung (`p10/T-0004`) — gegen die Rohdaten geprüft, nicht nur gegen die Werkzeugausgabe (Lesson B025). team-mail-Takt: Tages-Digest 2026-08-16 liegt zugestellt vor, nichts fällig. Reihenfolge für die nächste Session:*

**Für den Auftraggeber, eine Handlung (keine Entscheidung):** Der Cowork-Session fehlt auf `Downloads\aspice-team-repos-final` das Recht, Dateien zu **löschen**. Der neue Fallback macht das Team wieder arbeitsfähig, beseitigt die Ursache aber nicht — es sammeln sich weiter unlöschbare `.git\objects\**\tmp_obj_*` an. Sauber wird es erst mit erteiltem Lösch-Recht; bis dahin gelegentlich `.git\verwaiste-locks\` und die `tmp_obj_*` auf dem Host aufräumen (Runbook Kap. 5, R7).

0. **Briefkasten zuerst** — alle Projekte/Teams (Cockpit zeigt offene Briefe). *Aktuell keine offenen Briefe (alle 26 auf `beantwortet` geprüft; `platform/N-0004` kam **während** der Session um 10:04 herein und wurde in derselben Session beantwortet — B036).* **Merke für den Ablauf:** Der Briefkasten wird nicht nur am Anfang gelesen. Diese Session hätte den Brief sonst 30 Minuten liegen lassen, obwohl sie noch lief; aufgefallen ist er nur, weil beim Taggen ein fremder Commit im `platform`-Log stand. Ab jetzt: **vor dem Abschluss ein zweites Mal auf offene Briefe und entschiedene DRs prüfen** — dasselbe gilt für die Inbox (die G4a-Entscheidung kam 14 Sekunden nach dem Sprint-Commit).
0b. **Repo-Zustand vor dem ersten Schreiben** — `preflight.py` laufen lassen und die Ausgabe **lesen**. Steht dort „nicht löschbar … weggeräumt nach `.git/verwaiste-locks/`", hat der Fallback aus `pm/T-0023` gearbeitet und die Session wäre ohne ihn blockiert gewesen. Danach `git status` je Repo: **Liegt Arbeit einer Vorsession unverbucht da, zuerst verifizieren (Tests + Matrix + Gates), dann committen** — nie ungeprüft übernehmen (B025), nie doppelt verbuchen.
0c. **Überfällige Tickets zuerst (Eskalationsregel B044, seit SWR-091 maschinell sichtbar).** Die Cockpit-Kachel zeigt je Projekt/Team überfällige Aufgaben **über** den Statuszahlen, mit „n Tage über", dazu „n ohne Frist". Ein überfälliges Backlog-Ticket ist der **erste Arbeitspunkt nach dem Briefkasten**, vor jeder neuen Fläche. Wird es trotzdem nicht aufgegriffen, **steht der Grund hier beim Ticket** — nicht als Randnotiz. Ab dem zweiten übergangenen Mal geht ein Vermerk an den Auftraggeber. *(Erledigt in der 15:35-Session: `pm/T-0025` war bereits weg — 14:50, SWR-090.)*

*Erster Fund des neuen Zählers (SWR-091), noch in der Session seiner Einführung: Die pm-Kachel meldet **4 offene Tickets „ohne Frist"** — `T-0010`/`T-0013`/`T-0026` warten auf einen fremden Nachweis (grüner Actions-Lauf) und sind zu Recht unterminiert, aber **`pm/T-0003` heißt „Takt: LeLe je Sprint/Durchlauf konsolidieren" und trägt gar kein `takt`-Feld** — im Board steht es deshalb als „einmalig". Das war zur Zeit von B014 so gewollt, `pm/D005` hat es danach auf „kontinuierlich" umgestellt, ohne das Feld nachzuziehen. **Bewusst nicht auf Verdacht gesetzt:** `je-session` ist nicht dasselbe wie „je Sprint/Durchlauf", und TAKTE kennt letzteres nicht — das gehört zu `pm/T-0032` (Takt-Konzept), nicht in einen Nebensatz. Nächste Session: entweder Feld setzen oder begründen, warum keins.*

1. **Offene pm-Tickets, jetzt alle terminiert (SWR-091).** **`pm/T-0034` — Frist 17.08., Priorität hoch:** team-mail-Wochendigest seit Gründung fällig, nie erzeugt; fünf Sessions lang nur Randnotiz in Punkt 3, jetzt eigenes Ticket. Lösbar **nur am Host** (kein IMAP/Ollama hier) — kürzester Weg im Ticket. **`pm/T-0032` — Frist 19.08.:** Teil 2 aus `pm/N-0025`, echter Uhrzeit-Takt („jeden Tag um 14 Uhr"); berührt F14 und die zwei bestehenden Taktlogiken, Entwurf im Ticket, **erster Nutzer des Fristfeldes, das Teil 1 gebaut hat**. **`pm/T-0028` — Frist 23.08.:** Gründungs-Knopf im Pool; die von Hand vollzogene Gründung von `team-dashboard` ist jetzt seine reale Vorlage. **`team-dashboard/T-0001` — Frist 23.08.:** Widget-Vertrag entwerfen, Vorbedingung für P11. **`p11/T-0003` — Frist 30.08.:** Sprint 1 des Widget-Dashboards; beauftragt (G1a), startet aber erst mit dem Widget-Vertrag. Steht auf `open` statt `blocked`, weil `blocked_by` nicht über Repo-Grenzen reicht (B047) — die Ursache steht im Ticket. **ERLEDIGT:** `pm/T-0033` (G0a vollzogen, P11 angelegt) und `p11/T-0002` (G1a verbucht) — beide in der 16:15-Session; `pm/T-0030` Teil 1 (SWR-091, 15:35), `pm/T-0031` (Gründung, D006/TG-a), `pm/T-0025` (14:50, SWR-090), `pm/T-0029` (14:05), `pm/T-0027` (12:16), `pm/T-0022` (beide Teile). **Wartend beim Auftraggeber: `pm/T-0035`** (16:50-Session) — DR Klasse A zu `p0/T-0008` (Anthropic-API-Key): AK-a jetzt umsetzen / AK-b schließen wie den Zwilling `p1/T-0018` / AK-c offen lassen mit Frist. **Frist 23.08., Default AK-b.** `p0/T-0008` bleibt bis dahin `open` und **bewusst ohne Frist** (Begründung jetzt im Ticket, siehe B048). Vor diesem Antrag war die Inbox leer — gegen die DR-Rohdaten geprüft, nicht nur gegen `inbox.liste` (Werkzeug-Befund B047). **Ergänzung 17:30 (B049): `pm/T-0010` (18.08.), `pm/T-0013` (18.08.), `pm/T-0026` (18.08.)** sind ab jetzt ebenfalls terminiert — sie waren die drei unterminierten Tickets hinter der pm-Kachel, die drei Sessions lang übersehen wurden (siehe Punkt 6). **Neu: `pm/T-0036` — Frist 23.08., Priorität hoch:** CR gegen den blinden Fleck selbst (Org-Summe des „ohne Frist"-Zählers, Preflight-Zeile mit Ticketnamen, Ablaufregel). Damit meldet die pm-Kachel `unterminiert=0`; **organisationsweit bleibt 1** — `p0/T-0008`, begründet nach B048.

2. **P10 ist abgeschlossen (G4a/D002, 10:02 via Inbox — B035)** — Baseline `p10-v1.0` auf `projects` und `platform`, Abschlussbericht liegt in `projects/p10/management/`. Offen bleibt nur der **Betriebsnachweis des Auftraggebers**: die sieben Stichproben aus `p10/T-0004` (siehe Punkt 5) — nur erinnern, nie selbst abhaken.
3. **team-mail-Takt (`team-mail/T-0001`): SLA erstmals seit Gründung erfüllt (B046).** Der **erste Wochendigest** liegt (`digest/2026-08-16-woche-digest.md`), `mail_digest.faellig(7)` meldet `False`. Zustandegekommen ist er allerdings von Hand: Ein Lauf des Auftraggebers um 15:28 holte 165 Mails über 7 Tage, fand **kein Ollama** und schrieb Rohdaten mit dem Vermerk *die naechste Session verdichtet* — das war diese (Fallback SWR-062). **Der Rest des Befunds steht als `pm/T-0034`, Frist 17.08.:** Warum lief Ollama nicht, und ist `ASPICE-MailAutopilot` überhaupt eingerichtet? Ein fälliger Wochendigest darf nicht auf einen Klick warten.
4. **Fällige pm-Takt-Tickets** — Intake-Queue, Agenda fortschreiben; PUSH-ANFORDERUNG.txt am Session-Ende schreiben (Runbook Kap. 11).
5. **Offene Stichproben des Auftraggebers nachhalten** (nur erinnern, nie selbst abhaken) — **alle brauchen vorher einen Serverneustart**:
   - **Neu (17:30-Session, B049) — die einzige Stichprobe, die diesmal wirklich zählt:** **GitHub-Actions-Seiten öffnen** (der Wächter öffnet sie in Schritt [5/5] von allein) und für `p0`–`p9`, `pm`, `platform`, `projects` nachsehen, ob die Läufe **nach 10:30** grün sind. Damit schließen **drei** Tickets auf einmal: `pm/T-0026` zuerst (Matrix-Gate — solange das rot ist, sagt der Rest nichts), dann `pm/T-0013` und `pm/T-0010`. **Frist für alle drei: 18.08.** Gegenprobe im Cockpit: die **pm-Kachel** zeigt jetzt **keine** Pille „n ohne Frist" mehr; die **p0-Kachel** zeigt weiterhin „1 ohne Frist" — das ist erwartet und begründet (`p0/T-0008`, B048).
   - **Neu (16:50-Session, B048/pm/T-0035):** **Inbox öffnen** — dort steht `pm/T-0035` mit drei Knöpfen **AK-a/AK-b/AK-c**, Frist 23.08., Default AK-b. **Cockpit**: die **p0-Kachel** zeigt weiterhin die Pille „1 ohne Frist" (`p0/T-0008`) — das ist **erwartet und begründet**, nicht übersehen; die Begründung steht im Ticket. Gegenprobe: `p0/T-0008` öffnen → der Nachtrag nennt D008, D015, Kriterium 9/B9 und P1-E5, Status ist unverändert `open`.
   - **Neu (16:15-Session, pm/T-0033/D007 + p11/D001):** **Kopfbereich und Cockpit** zeigen **P11 „Widget-Dashboard"** als aktives Projekt mit Board und einer offenen Aufgabe (`p11/T-0003`, Frist 30.08.). **Requirements-Reiter** → Filter „Projekt/Team: p11" zeigt STK-021 und SWR-092–096, alle auf `draft`. **Inbox** ist leer. **Pool-Reiter** zeigt einen dritten Abschnitt **„Realisiert"** mit Kandidat #13 und dem Weg, den er genommen hat; die Team-Kandidatenliste hat noch fünf Einträge. Gegenprobe: „Neuen Kandidaten anlegen" vergibt die Nummer **14**, nicht 13.
   - **Neu (15:35-Session, SWR-091/pm/T-0030):** **Cockpit öffnen** — über den Statuszahlen einer Kachel steht bei überfälligen Aufgaben ein roter Block („n überfällig", je Ticket „Frist … (n Tage über)"), in der Statuszeile eine Pille „n ohne Frist". Gegenprobe: einem offenen Ticket im Ticket-Editor eine Frist von **gestern** geben → es erscheint sofort im roten Block; eine unsinnige Frist („2026-13-01") wird beim Speichern mit Klartext abgelehnt.
   - **Neu (15:35-Session, pm/T-0031/D006):** **Kopfbereich und Cockpit** zeigen `team-dashboard` als **Projekt-Team** mit Board und einer offenen Aufgabe (`T-0001`, wiederkehrend). **Inbox** zeigt den neuen G0-Antrag `pm/T-0033` (P11) mit drei Knöpfen G0a–G0c und Frist 23.08.
   - **Neu (14:50-Session, SWR-090/pm/T-0025):** **Team-Reiter `team-mail`** — unter „Jetzt zusammenfassen" steht die Klartextzeile **„Ein Klick startet: Woche · Modell: gemma3:27b · KI-Hinweis: kein Zusatz · Versand: zusätzlich per Mail"**. Im Konfigurator einen KI-Hinweis eintragen, speichern, Seite neu laden → die Zeile zitiert ihn. Takt auf „Täglich" umstellen, speichern, neu laden → die Zeile sagt „Tag". Nach einem echten Klick nennt die Erfolgsmeldung die geschriebene Datei beim Namen.
   - **Neu (14:50-Session, pm/T-0031):** **Inbox öffnen** — der Gründungs-Antrag `pm/T-0031` steht dort mit vier Knöpfen `TG-a` bis `TG-d` und Frist 23.08.
   - **Neu (14:05-Session, pm/T-0029):** Pool-Reiter → „Neuen Kandidaten anlegen" → Technik-Kandidat, in „Quelle" einen deutlich über 4000 Zeichen langen Text eintragen (z. B. einen längeren Gesprächsausschnitt) → anlegen → erscheint als eine Zeile im Pool, keine Ablehnung. Nutzen/Voraussetzung/Quelle sind jetzt Mehrzeilenfelder im Formular.
   - **Neu (12:16-Session, pm/T-0027):** Pool-Reiter → „Neuen Kandidaten anlegen" → Technik-Kandidat, mehrsätzigen Text mit Zeilenumbrüchen eintragen (z. B. aus einer KI-Antwort kopiert), anlegen → erscheint als eine Zeile ohne Zeilenumbrüche im Pool.
   - **Neu (11:45-Session, SWR-089):** **Pool-Reiter „Projekt starten"** — einen Technik-Kandidaten aus der Dropdown wählen (z. B. einen unwichtigen wie „JS-Frontend-Tests"), auf „G0-Antrag anlegen" klicken; Meldung zeigt die neue Projekt-Referenz (z. B. `p11/T-0001`), der Kandidat verschwindet ohne Neuladen aus der Pool-Tabelle, die Inbox zeigt den neuen G0-Antrag mit Frist. `git -C projects log --oneline -2` und `git -C pm log --oneline -2` zeigen je einen „Mensch via HMI"-Commit. Einen Team-Kandidaten wählen sollte mit einer Erklärung abgelehnt werden (Team-Gründung ist nicht Teil dieses Knopfs). Kopfzeile im Pool-Reiter sagt jetzt „Anlegen: da / Starten (Technik) per Knopf: da". **Danach entweder über die Inbox entscheiden (G0a/b/c) oder den Testordner wieder entfernen, wenn die Stichprobe nur die Funktion prüfen soll.**
   - **Neu (11:21-Session, SWR-088):** **Pool-Reiter „Neuen Kandidaten anlegen"** — einen Team- und einen Technik-Kandidaten anlegen (unterschiedliche Felder je Kategorie), beide erscheinen ohne Neuladen im richtigen Abschnitt; `git -C pm log --oneline -2` zeigt „Mensch via HMI"-Commits.
   - **Neu (B033/B034), die sieben Stichproben aus `p10/T-0004`:** Ticket bearbeiten und speichern · unerlaubten Status setzen → deutsche Ablehnung · zwei Labels vergeben und im Board danach filtern · `git -C projects log --oneline -3` zeigt „Änderung via HMI" mit BOARD.md im selben Commit · Konflikt erzwingen (Ticket am Handy offen, vom Rechner speichern, dann am Handy) → Klartextmeldung + „Ticket neu laden" · vom Handy ohne PIN speichern → Ablehnung, mit PIN → geht · erledigtes Ticket öffnen → nur „Wiedereröffnen", kein Formular.
   - **Neu (B028):** **Requirements-Reiter** — stehen ohne Projektwahl alle Dokumente da (22 aus 13 Projekten/Teams)? Filter „Projekt/Team: p10" und Volltext „SWR-085" prüfen. Auch auf dem Handy.
   - **Aus B029:** **Reiter „Projekt-Pool"** — beide Kategorien (5 Team-, 7 Technik-Kandidaten) sichtbar? *(Kopfzeilentext hat sich seither zweimal geändert, siehe die beiden neuen Stichproben oben — diese hier prüft nur noch die Sichtbarkeit der Kategorien.)*
   - **Neu (B030):** **Eindeutige Kennung** — Board von `pm` zeigt `pm/T-0019`, Board von `p10` zeigt `p10/T-0001`; Ticket-Detail und Cockpit genauso.
   - **Aus B024:** **Inbox öffnen** — sie ist jetzt leer (alle DRs entschieden); der Nachweis, dass Anträge aus dem Sammel-Repo dort ankommen, wurde durch die P10-Freigabe um 08:18 bereits praktisch erbracht.
   - **Aus B023:** **Server-Log** — Handy verbinden, Bildschirm sperren: nur noch `Verbindung zu … vorzeitig beendet … kein Fehler`, kein Traceback. Nachweis geht nur auf Windows (WinError 10054).
   - **Aus B021:** **Kopfbereich** — nur feste Teams, Projekt-Teams und aktive Projekte anklickbar; Deep-Link `#/board/p3` klappt „weitere" von allein auf. Auch auf dem Handy.
   - P9-Cockpit: 3 Stichproben aus `p9/T-0004` (Gruppen, Einklappen, Aufgaben-Links).
   - Aus B010: Konfigurator öffnen → **KI-Modell** auswählen und **KI-Hinweis** eintragen, speichern, „Jetzt zusammenfassen" laufen lassen und den Digest inhaltlich bewerten.
   - Aus B013: **Selbst-Neustart** — Mission Control über `mission-control.cmd` starten, dann prüfen, ob der Server nach einer Session von allein hochkommt und die Seite nachlädt.
   - Aus B014: **Takt-Kennzeichnung** — Board von `pm` öffnen: `pm/T-0001`/`pm/T-0002` „wiederkehrend: je Session", `pm/T-0003` einmalig.
6. **Drei Tickets warten auf denselben Nachweis — einen grünen GitHub-Actions-Lauf; seit 17:30 mit Frist 18.08. (B049):** **`pm/T-0010`** (board-check-Flake), **`pm/T-0013`** (Push-Reihenfolge platform zuerst), **`pm/T-0026`** (`projects`-Checkout in `ci.yml`). Alle drei bleiben `in_review`; lokal ist alles grün, und genau das war bei T-0026 der Fehler. **Reihenfolge beim Prüfen:** erst T-0026 — solange das Matrix-Gate rot ist, sagt ein roter Lauf nichts über T-0010/T-0013 aus. **Neu und wichtig:** Der Satz „Nachweis unerreichbar, kein `gh`/Netzzugriff" stand hier sieben Sessions lang und war in **zwei** Hinsichten falsch — der Wächter läuft seit **10:30** wieder (13 grüne Läufe, alle Repos `ahead 0`), und **Kriterium 1 von `T-0013` ist bereits erfüllt und war rein lokal prüfbar** (`platform` als erstes Repo in der Push-Ausgabe, seit 07:59:59 in jedem Lauf, siehe `abschluss-auto.log`). Am Host fehlt jetzt nur noch **ein Blick auf die Actions-Seiten**, die der Wächter in Schritt [5/5] ohnehin öffnet. **Regel daraus:** Ein Hinderungsgrund im Ticket ist ein Messwert mit Datum, keine Eigenschaft — wer ihn wiederholt, prüft ihn vorher nach; und Verifikationskriterien werden **einzeln** abgehakt, nie als Satz.
7. **Pilotreview:** team-mail ab 2026-08-29 (B002) — Digest-Format-Feedback, B003 (Werkzeug-Promotion), CR-Kandidat Markdown-Renderer für Briefe/Reports.
8. **Betriebs-Backlog** — BB-5 PAT-Erneuerung ab 2026-09-05 (ab 1.9. aktiv erinnern). CR-Kandidaten: **neu (aus B047): repo-übergreifendes `blocked_by`** — `board.py` prüft den Verweis gegen die IDs desselben Repos; seit `team-dashboard` fachlicher Auftraggeber von P11 ist, gibt es echte Abhängigkeiten über Repo-Grenzen (`p11/T-0003` wartet auf `team-dashboard/T-0001`) und der Status `blocked` ist dafür unbenutzbar. Berührt Board-Validierung, Cockpit-Anzeige und Fälligkeitslogik zugleich — gehört zu `pm/T-0032`/einer eigenen Session, nicht in eine Verbuchung. **Ebenfalls neu (16:15-Session): `preflight.unit_tests` gibt bei rotem Lauf nur die letzten drei Zeilen aus** — genau die Zusammenfassung; die `FAIL:`-Zeilen mit den Testnamen werden verworfen, ein Flake lässt sich hinterher nicht mehr untersuchen (heute einmal eingetreten, siehe oben). Fix wäre klein: bei `returncode != 0` zusätzlich die `FAIL:`/`ERROR:`-Zeilen durchreichen. **Ebenfalls neu (aus B047): eine Prüfung „entschieden, aber nicht verbucht"** — die Inbox kann das bauartbedingt nicht melden (SWR-039 filtert entschiedene DRs heraus); heute hängt der Fund an einer namentlichen Erwartung in der Agenda. **Neu (aus B038): der Auto-Push-Wächter meldet Fehlschläge nur nach `abschluss-auto.log`** — eine Warnmail nach dem n-ten Fehlversuch (die Mail-Strecke aus SWR-033 existiert bereits) hätte heute zwei Stunden Stillstand auf fünfzehn Minuten verkürzt. Bewusst nicht nebenbei gebaut: Mailversand ist Außenwirkung und gehört nicht in einen SUP.9-Fix; `abschluss.cmd`, `abschluss-auto.cmd` und die `mission-control*.cmd` liegen **unversioniert** im Wurzelordner (Vorschlag: nach `platform/infra/` versionieren, im Wurzelordner nur dünne Aufrufer); Projekt-Workflows checken `platform` auf einem **Tag** statt `main` aus; **neu:** Repo-Präfix auch im generierten `BOARD.md` (aus `pm/T-0021` zurückgestellt — Formatänderungen am Board haben heute schon einmal alle Prüf-Workflows rot gemacht, das gehört gebündelt mit `pm/T-0013`).

*Hinweis (D004): Diese Agenda wird automatisch alle 30 Min von der Cowork-Routine-Session abgearbeitet (solange die App offen ist) — Briefe genügen, Ankündigungen im Chat sind nicht mehr nötig.*

*Beobachtung 2026-08-16 (für die Retro/LeLe): Zwei Routine-Sessions können sich überlappen. Erkennungsmerkmal ist ein `.git/index.lock`, das die eigene Arbeit blockiert; Auflösung siehe Runbook Kap. 5 (Preflight erneut, ggf. Cowork-Löschrecht erteilen). Regel: erst Repo-Status prüfen, dann schreiben — nie doppelt verbuchen.*

*Lesson 2026-08-16 **verschärft** (aus B041): Die Überlappung ist eingetreten, und sie sah anders aus als erwartet — **nicht** als Lock, sondern als **fremde Änderung an einer Datei, die diese Session nur gelesen hatte** (`team-mail/tools/mail_digest.py`). Beide Sessions bearbeiteten denselben Brief; die parallele hatte den besseren Befund und zog ihre Arbeit dann selbst zurück, weil sie den Konflikt bemerkte. Übrig geblieben wäre eine Brief-Antwort, die auf ein Ticket verweist, das nicht mehr existiert (die Lesson aus B029), plus ein verschwundener, richtiger Befund. Gefunden wurde das nur, weil der Board-Check **2 statt 3 Tickets** meldete. **Neue Regeln: (1)** Vor dem Commit `git status` je Repo **lesen**, nicht nur auf sauber prüfen — eine Änderung an einer Datei, die man selbst nicht angefasst hat, ist ein Stoppsignal, kein Rauschen. **(2)** Wer fremde uncommittete Arbeit vorfindet, prüft sie gegen die Werkzeuge und benennt ihre Herkunft; übernehmen ohne Prüfung ist B025, verwerfen ohne Prüfung kostet den Befund. **(3)** Zahlen aus Werkzeugausgaben (Tickets, Tests) gegen die Erwartung lesen — „3 Tickets validiert" ist eine Aussage, „2" war hier der einzige Hinweis auf einen Verlust.*

*Lesson 2026-08-16 (aus pm/T-0023, B031): **Ein Werkzeug, das eine Blockade nur beschreibt, hat die halbe Arbeit getan.** Preflight erkannte den unlöschbaren `index.lock` vollständig richtig und verwies auf eine Handlung des Menschen am Host — währenddessen verlor eine fertige Session ihre komplette Verbuchung, obwohl der Ausweg (`rename` statt `remove`) auf demselben Mount die ganze Zeit offen war. DoD-Prüffrage für Diagnose-Ausgaben: **„Gibt es neben dem gesperrten Weg einen offenen, den das Werkzeug selbst gehen könnte?"** Verwandt zu B025: Dort log ein leeres Werkzeugergebnis über den Zustand, hier eine korrekte Meldung über die Handlungsmöglichkeiten.*

*Lesson 2026-08-16 (aus pm/T-0023, zweiter Befund): **Der Nachweis gehört ans Ende der Kette, nicht ans Ende der Änderung.** Der erste Lock-Fix war für sich richtig und mit 5 grünen Tests belegt — und ließ die Session trotzdem gesperrt zurück, weil Preflights eigene `git status`-Aufrufe neue Locks erzeugten, nachdem es aufgeräumt hatte. Geprüft war die Funktion, nicht der Zustand, in dem sie das System zurücklässt. DoD-Prüffrage: **„Ist der nächste echte Arbeitsschritt danach noch möglich?"** — einmal am echten System ausgeführt, nicht im Test nachgestellt.*

*Lesson 2026-08-16 (aus B031, für die Retro/LeLe): **Ein Statusbericht ist kein Beleg dafür, dass etwas in Git steht.** PROJEKTSTATUS-UPDATE.md und Agenda beschrieben B028/B029/B030 als geliefert — `git log` kannte nichts davon. Neue Pflicht am Session-Anfang (Punkt 0b) und am Session-Ende: Der Abschluss gilt erst als erreicht, wenn `git status` in **jedem** Repo sauber ist; „dokumentiert" und „verbucht" sind zwei verschiedene Zustände.*

*Lesson 2026-08-16 (aus p9/T-0007, für die Retro/LeLe): Wenn eine Anforderung „die Werkzeuge sollen X unterstützen" sagt, ist sie erst erfüllt, wenn jede Kopie der betroffenen Logik nachgezogen — besser: zu einer zusammengeführt — ist. DoD-Prüffrage: „Gibt es diese Auflösung noch ein zweites Mal im Repo?"*

*Lesson 2026-08-16 **verschärft** (aus pm/T-0017, B025): Die Prüffrage oben wurde am Vormittag nur auf die Skripte angewendet, in denen der Befund auftrat — im Backend blieben vier weitere Kopien stehen und machten am Nachmittag einen **Klasse-A-Entscheidungsantrag unsichtbar**. Ab sofort: Wer Discovery oder Pfadauflösung anfasst, sucht `grep "join(root," / "join(wurzel,"` über das **gesamte** Repo und zieht jede Fundstelle nach oder begründet sie. Zweite Lehre: **Ein leeres Werkzeugergebnis ist kein Beweis für „nichts zu tun."** Wo ein Statusdokument eine Erwartung formuliert, wird sie gegen die Werkzeugausgabe geprüft, nicht abgeschrieben.*

*Lesson 2026-08-16 (aus pm/N-0020, B029): **Eine Ticketnummer in einem Beschluss zu nennen, ist keine Beauftragung.** `pm/D005` kündigte den Pool-Knopf „als CR T-0011" an; die Nummer wurde danach von einem anderen Vorgang belegt, und die Zusage verschwand geräuschlos — bis der Auftraggeber zum zweiten Mal danach fragte. Ab sofort: Jeder Beschluss, der Arbeit ankündigt, wird in derselben Session mit einem **real angelegten** Ticket belegt; Nummern werden nie vorab vergeben. Verwandte Lehre zu B025: Auch hier meldete kein Werkzeug einen Fehler — es gab schlicht nichts Offenes, das hätte auffallen können.*

*Lesson 2026-08-16 (aus P10 Sprint 1, B033): **Ein zweiter Zugang ist noch kein zweites Regelwerk.** Beim Bau des HMI-Schreibpfads war der bequeme Weg, im Server „schnell" zu validieren — das hätte die Prüfregeln ein zweites Mal geführt (Risiko R2 des Sprint-0-Plans). Stattdessen liegt der Schreibpfad in `board.py`; das Backend ist Fassade. Beim Hinschauen fiel auf, dass dieselbe Falle schon zugeschnappt war: Die Zeitstempel-Formatierung (SWR-084) hätte für die Änderungshistorie ein zweites Mal entstehen müssen — jetzt delegiert `inbox` an `board.zeitpunkt`. DoD-Prüffrage beim Bau eines neuen Zugangs: **„Welche Regel wäre ich versucht, hier noch einmal zu schreiben — und wo steht sie schon?"***

*Lesson 2026-08-16 (aus pm/T-0024, B038): **Ein Fallback, der die Ursache verschweigt, ist eine Falschaussage mit Zeitverzögerung.** `except Exception: return True` war als Vorsicht gemeint und richtig gedacht — die Meldung, die daraus entstand („Git-Prozess aktiv"), war aber eine Behauptung über die Welt, die niemand mehr anzweifelte, weil sie wie eine Messung klang. Verwandt zu B025 (ein leeres Werkzeugergebnis ist kein Beweis) und pm/T-0023 (ein Werkzeug, das nur beschreibt, hat die halbe Arbeit getan) — diesmal war es kein leeres, sondern ein **plausibel klingendes falsches** Ergebnis. DoD-Prüffrage für Fallbacks: **„Wenn dieser Zweig greift — steht danach im Protokoll, dass geraten wurde, oder liest es sich wie eine Messung?"***

*Lesson 2026-08-16 (aus B038, zweiter Teil): **Der stille Ausfall einer Automatik ist teurer als ihr lauter.** Der Wächter brach zwei Stunden lang alle 15 Minuten ab und meldete das ausschließlich in eine Logdatei, die ohne Anlass niemand liest. Nach außen sah alles normal aus — Sessions liefen, committeten, meldeten STARTKLAR. Der einzige sichtbare Hinweis war, dass zwei Tickets nicht weiterkamen, und bemerkt hat ihn **der Auftraggeber**. DoD-Prüffrage für Automatiken: **„Wo wird ein Fehlschlag sichtbar für jemanden, der nicht danach sucht?"***

*Lesson 2026-08-16 (aus B038, dritter Teil): **Ein Test, der die Umgebung befragt, prüft die Umgebung.** `test_nur_locks_laesst_repos_unberuehrt` legte ein Fake-Repo in %TEMP% an und fragte über `git_prozess_aktiv()` den **gesamten Rechner** nach laufenden Git-Prozessen — ein Commit aus dem HMI oder der Wächter selbst genügten, um ihn rot zu machen und `abschluss.cmd` mitzureißen. Hermetik war am 15.08. schon einmal SUP.9-Befund. DoD-Prüffrage: **„Welche Aussage dieses Tests hängt an etwas, das außerhalb seines Temp-Ordners passiert?"***

*Einsprüche des Menschen gegen Agenda-Prioritäten: einfach im Briefkasten/Chat hinterlassen — wird als neue Log-Zeile verbucht.*
