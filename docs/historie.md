## Lauf 2026-08-21, später — **kein Sprint**, Shell erneut nicht verfügbar; ein Blocker VOR seinem Einsatz gefunden

**Kein Sprint 36 begonnen.** Die Linux-Shell war zum zweiten Lauf in Folge nicht
verfügbar (vier identische Startfehler, `useradd`/ENOSPC-Familie). Damit kein `git`, kein
`board.py`, kein `preflight`, keine Tests, kein Ollama-Tick, kein `sprint_register.py`.
Sprint 35 bleibt im Register **offen** (`s35-2026-08-21-1450`); nach **SWR-136** hätte
`beginne()` einen Sprint 36 ohnehin verweigert. Wieder **nichts** gebaut, geschlossen
oder terminiert.

### ⚠⚠ Der Fund: der nächste Takt-Blocker liegt schon fertig da — und zündet erst beim Sprintstart

Gemessen am Bestand (Frontmatter aller Ticketdateien, beide Ebenen): **zehn** offene bzw.
`in_review`-Tickets tragen `geplant_sprint: 35`:

`platform/T-0055`, `platform/T-0060` (in_review), `platform/T-0064`, `pm/T-0080`,
`pm/T-0082`, `team-dashboard/T-0004`, `team-dashboard/T-0006`, `team-mail/T-0006`,
`team-mail/T-0007`, `team-termine/T-0001`.

Neun davon hat der **Abschluss von Sprint 35 in Prosa nach Sprint 36 verschoben**
(*„→ Sprint 36, Grund je im Ticket"*). **Kein einziges Ticket trägt diese Verschiebung.**
Nachgesehen an `platform/T-0055`: `geplant_sprint: 35`, letzte Notiz
*„⚠ Verschoben nach Sprint 35"*. Es gibt keine Sprint-36-Notiz — auch die Zusicherung
„Grund je im Ticket" ist damit für diese Tickets **nicht eingelöst**.

**Warum es heute still ist und morgen nicht** (gelesen, nicht geraten):
`sprint_vergangen` (SWR-112) meldet offene und `in_review`-Tickets, deren
`geplant_sprint` **kleiner** ist als `sprint_register.aktuell()`; ausgenommen sind nur
`decision-request` und `blocked` (über `board.gesperrt`). `aktuell()` liefert die Nummer
des **zuletzt begonnenen** Sprints — heute **35**, also `35 < 35` = falsch, kein Befund.
Keines der zehn ist ein DR, keines ist `blocked`.

> **⚠⚠ In der Sekunde, in der `--beginne` Sprint 36 anlegt, meldet der Preflight alle
> zehn — und der Schnelltakt bricht wieder ab. Zum dritten Mal in Folge läge der Blocker
> im Abschluss des Vorsprints — aber zum ersten Mal sehen wir ihn, BEVOR er zuschlägt.
> Der Unterschied ist nicht Sorgfalt, sondern die Reihenfolge: wir haben die Regel
> gelesen, statt das Ergebnis abzuwarten.**

⚠ **Zwei Präzisierungen aus dem Gegenlesen, die die eigene erste Formulierung
korrigieren:** Es ist **ein** Befund, der zehn Tickets namentlich nennt (`befunde += 1`),
**nicht zehn Befunde** — für den Exit-Code gleichwertig, für jede Zählung nicht. Und die
Auslösung braucht **zwei** Schritte: solange die letzte Registerzeile kein `ende` trägt,
verweigert `beginne()` nach SWR-136 und nennt den laufenden Sprint; der Befund entsteht
nach `--beende` **und** `--beginne`.

⚠ **Und die „Erste Aufgabe des Folgelaufs", die Sprint 35 selbst aufgeschrieben hat,
führt genau hinein:** Schritt 1 `--beende`, Schritt 2 `kennzahlen`, Schritt 3 committen,
Schritt 4 Tests. Das Nachziehen der zehn Tickets kommt darin nicht vor. Die Liste ist in
`management/sprint-aktuell.md` in diesem Lauf **umgestellt** worden — das Nachziehen steht
jetzt als Schritt **0**, vor `--beende`.

### ⚠ Zweiter Fund: neun von elf geräumt, und keine Prüfung merkt den Rest

`team-termine/T-0011` und `T-0012` stehen auf `status: open` **und** tragen zugleich
`blocked_by: [T-0001]` bzw. `[T-0006]` — genau der Widerspruch, den Sprint 35 für
`T-0002…T-0010` aufgelöst hat (*„zwei Aussagen zu derselben Frage"*). Neun wurden gezogen,
**zwei blieben liegen**, und beide stehen im Sprint-35-Plan in der Zeile der
Takt-Dauerläufer („jeder Sprint", geplant).

Nachgesehen, warum es niemand meldet: `board.validiere` prüft nur **eine** Richtung
(`blocked` ohne `blocked_by` → Fehler), nicht die Gegenrichtung. `board.gesperrt` verlangt
**beides**, also gelten die zwei als planbar — während `board.offene_blocker` sie dem
Orchestrator dauerhaft entzieht.

> **Eine Regel, die von Hand auf neun Fälle angewandt wird und keine Prüfung hat, ist beim
> zehnten wieder weg. Sprint 35 hat den Bestand geräumt und die Regel nicht gebaut.**

### ⚠⚠ Warum beide Funde NICHT repariert wurden — und warum das diesmal die Arbeit ist

Beide wären mit wenigen Zeilen behoben. Bewusst nicht angefasst, und der Grund ist
**gelesen, nicht gefühlt**: `preflight.ist_verifikationsquelle` nennt drei Sorten Datei,
die eine Verifikation liest — `BOARD.md`, `*/requirements/**/software-requirements.md` und
**jede** Datei unter `*/tickets/`. Eine geänderte, **nicht committete** Verifikationsquelle
ist ein Preflight-Befund; genau das sind zwei der drei Befunde, die den Takt gerade
blockieren.

> **Ohne `git` verwandelt jede Ticket-Änderung Arbeit in einen neuen Takt-Blocker. Zehn
> Tickets richtigzustellen hieße, zehn Befunde anzulegen, um zehn Befunde zu vermeiden.**

Damit hat `L-2026-08-21db` aus dem Vorlauf zum ersten Mal eine **nachlesbare Grenze**:
`ist_verifikationsquelle` ist die Liste der Dateien, die ein Lauf ohne Shell nicht
anfassen darf — und alles andere (Erzähl-, Plan-, Lehrdateien) darf er.

⚠ **Zwei Schärfungen aus dem Gegenlesen:** (a) `management/sprint-aktuell.md` ist zwar
frei, wird aber von `plandrift`, `statusdrift`, `plannachlauf` und
`test_berichtskennzahlen` gelesen — dieser Lauf hat deshalb **Plantabelle und
Kennzahlenblock nicht angefasst**, und `plan_tabelle` schneidet ohnehin nur die **erste**
Tabelle nach der Plan-Überschrift, sodass die neuen Nachtragstabellen für den Plan
unsichtbar sind. (b) `PROJEKTSTATUS-UPDATE.md` und `PUSH-ANFORDERUNG.txt` sind
unbedenklich, aber aus einem **anderen** Grund als angenommen: die Arbeitswurzel ist kein
Git-Repo, sie erscheinen in keinem `git status`. **Die richtige Antwort aus dem falschen
Grund ist keine Messung.**

> **Lehre `L-2026-08-21dp`: Eine Verschiebung, die nur im Bericht steht, ist erst beim
> nächsten `--beende`/`--beginne` fällig — und dann der ganze Rückstand auf einmal.**
> **Lehre `L-2026-08-21dq`: Ohne `git` ist die Ticketdatei tabu, der Rest des Hauses
> frei.** Verbleib: `process/knowledge/pl/lessons.md` (beide mit `## L-`-Kopf), diese
> Chronik, Rollenkarte `pl` (Punkte 11 und 12).

⚠ **Zur ID-Vergabe, und das ist ein Befund über das Gegenlesen selbst:** die unabhängige
Prüfung meldete `dp` als „bereits vergeben" — sie las die Dateien, die **dieser Lauf
gerade geschrieben hatte**. Sie hat dabei zugleich etwas Richtiges gefunden: `dh` und `di`
sind vergeben (in `p9/requirements`), ohne je einen `## L-`-Kopf bekommen zu haben.

> **Eine Prüfung, die gegen die Arbeitskopie läuft, kann „vergeben" nicht von „soeben von
> dir vergeben" unterscheiden. Sie prüft den Stand, nicht die Herkunft.**

⚠ Die IDs sind gegen die **Arbeitskopie** geprüft (`da`–`do` belegt, `dq` aufwärts frei),
**nicht gegen HEAD** — dafür fehlt `git`.

**Gemessen in diesem Lauf:** Briefkasten **0 offen** (69 Briefe über beide Ebenen, kein
`status: offen`). Offene Aufgaben **34** = **20 `open` + 13 `blocked` + 1 `in_review`**.
⚠ Der Vorlauf nannte „22 `open` + 12 `blocked`" — **dieselbe Summe, andere Aufteilung**;
die 13 sind namentlich belegbar (9 × `team-termine`, `promt-team/T-0003`, `T-0012`,
`pm/T-0071`, `T-0079`). Nicht stillschweigend geglättet, sondern beide Zahlen genannt.
**Ollama-Offload:** 0 delegiert, Token-Ersparnis **0** — `pm/T-0071` hat weiterhin keinen
Tick mit `status ok` + Artefakt, und der Tick kann mangels Shell hier ohnehin nicht laufen.
**Nicht gelaufen und deshalb nicht behauptet:** Tests, Trace-Matrix, Organigramm,
`board.py --check`, `preflight`.

---

## Lauf 2026-08-21, ~16:4x — **kein Sprint**, Shell nicht verfügbar

**Kein Sprint 36 begonnen.** Die Linux-Shell dieser Session war durchgehend nicht
verfügbar (fünf identische Startfehler); damit kein `git`, kein `board.py`, kein
`preflight`, keine Tests, kein Ollama-Tick, kein `sprint_register.py`. Sprint 35 ist im
Register weiterhin **offen** (`s35-2026-08-21-1450`) — nach **SWR-136** hätte `beginne()`
einen Sprint 36 ohnehin verweigert. Bewusst **nichts** gebaut, geschlossen oder
terminiert.

**Gemessen (lesend, aus `ollama-schnelltakt.log`, Lauf 21.08. 16:01:20):** der Schnelltakt
bricht wieder ab — `PREFLIGHT: 3 Befund(e) (10 fortgeschrieben)`. **Alle drei stammen aus
dem Abschluss von Sprint 35:** zwei unverbuchte Dateien
(`p9/requirements/software/software-requirements.md`, `pm/tickets/T-0085.md`) und eine
Planzeile, die `pm/T-0085` auf Sprint 35 führte, während das Ticket `geplant_sprint: 36`
trägt.

> **⚠⚠ Zum zweiten Mal in Folge hat unser eigener Sprint-Abschluss den Takt gesperrt, den
> derselbe Sprint entsperrt hat. Beim ersten Mal haben wir es entdeckt; diesmal haben wir
> es beim Schreiben gewusst und trotzdem hinterlassen — weil die Shell mitten im Abschluss
> ausfiel und ein halber Abschluss schlimmer bucht als keiner.**

**Behoben:** genau die dritte — Planzeile `pm/T-0085` auf **Sprint 36** gezogen
(`management/sprint-aktuell.md`), belegt durch den Sprint-35-Eintrag unten
(„Entscheidung Sprint 36"). Das war das einzige der drei Dinge, das ohne Shell behebbar
war, **und zugleich das einzige, das `abschluss.cmd` nicht mit erledigt hätte** — ein
Commit der falschen Zeile hätte den Befund mitgenommen.

> **Lehre `L-2026-08-21db`: Wenn ein Werkzeug ausfällt, ist die nützlichste Arbeit die
> Teilmenge der Blockade, die das Werkzeug ohnehin nicht gelöst hätte. Verbleib: diese
> Chronik + Rollenkarte `pl` („Lehren aus dem Betrieb").**

⚠ **Nicht nachgemessen:** `preflight` konnte die Korrektur nicht bestätigen. Dass der
nächste Takt `STARTKLAR` meldet, ist eine **Erwartung, keine Messung** — bewusst so
ausgeschrieben statt als Erfolg gebucht.

**Briefkasten:** 0 offen über alle Repos (gemessen, 69 Briefe, kein `status: offen`).
**Offene Aufgaben:** 34 (22 `open`, 12 `blocked`). **Ollama-Offload:** 0 delegiert,
Token-Ersparnis 0 — `pm/T-0071` hat weiterhin keinen Tick mit `status ok` + Artefakt.

---

## Sprint 35 (2026-08-21) — Planung und Abschluss

**Geschlossen:** `platform/T-0065` (**SWR-213**). **In Review:** `platform/T-0060`
(**SWR-212**) — der Blocker ist geräumt, der Nachweis braucht den nächsten Takt auf dem
Rechner des Auftraggebers. **Gemessen statt verschoben:** `pm/T-0085` (DoD 1 und 3
beantwortet, Entscheidung Sprint 36). **Neu:** `platform/T-0066`, `T-0067`.
**Briefkasten:** 0 offen beim Start **und am Ende** (nachgemessen, `L-2026-08-21cs`).

**⚠⚠ Der Fund des Laufs war der MESSPUNKT, nicht die Messung.** Der Ollama-Takt läuft
seit dem 20.08. auf `DESKTOP-8OOO6JS` — **87 Läufe, 138 Abbrüche, 0 Erfolge** —, und sein
Protokoll lag die ganze Zeit unangetastet im Arbeitsordner. Sprint 34 hatte gemeldet, der
Nachweis sei „aus dieser Sandbox nicht führbar". Beides stimmt und beides misst den
falschen Rechner.

> **Drei Sprints lang haben wir die Erreichbarkeit einer Maschine diskutiert, auf der der
> Takt gar nicht läuft.**

**⚠⚠ Und alle 138 Abbrüche gehen auf unsere eigene Buchführung zurück:** *„Preflight hat
Befunde"* — vier Planzeilen mit der alten Sprintnummer und neun `team-termine`-Tickets
ohne Sprint, **beides von Sprint 34 selbst erzeugt**.

> **Unser eigener Sprint-Abschluss hat den Nachweis blockiert, den derselbe Sprint als
> „nicht führbar" gemeldet hat. Die Sperre trug den Namen der Sorgfalt.**

**⚠ Das Gegenlesen hat 17 Befunde gefunden — vierter Sprint in Folge, und wieder keinen
davon der Autor.** Darunter drei echte Defekte (ein Feld erbte den Wert seines
Vorgängers; ein unbekanntes Kettenglied löschte die Meldung des echten Versuchs; ein
Erstbrief mit datumslosem Zeitstempel fiel durch alle drei Zahlen), fünf Zusicherungen,
die bei kaputtem Code grün blieben, und vier falsche Zahlen in bereits geschriebenen
Anforderungen.

**⚠ Ein eigener Fehler, den das Gate gefunden hat und nicht der Autor:** die
Katalogzeile für `SWR-212` wurde ohne Zeilenumbruch **an die Zeile von `SWR-211`
angehängt**. Der Trace-Matrix-Lauf meldete daraufhin „1 Lücke" — die Anforderung war
vorhanden und für jedes Werkzeug unsichtbar. Getrennt, danach **213 SWRs / 0 Lücken**.

---

## Sprint 34 (2026-08-21) — Planung und Abschluss

**Geschlossen:** `platform/T-0062`, `T-0063`, `T-0061`, `T-0056` (**SWR-207–209, 211**),
`team-dashboard/T-0005` (**SWR-210**), `pm/T-0083`. **Verschoben:** sechs nach Sprint 35,
Grund je im Ticket. **Briefkasten:** 0 offen, am **Ende** gemessen — ⚠ **1 Beitrag** kam
um 12:26 während des Laufs und wurde im selben Sprint umgesetzt.

**Gegründet: P16 `team-termine`** (`pm/D016` = B, Brief `pm/N-0044`) — erstes Projekt
**oberhalb** von `projects/`, mit `.kein-remote`. ⚠ Die Planung des Tickets sagte
„als Ordner unter `projects/`“; das wäre falsch gewesen, weil `projects` gepusht wird und
das Projekt den Kalender eines **fremden Kontos** verarbeitet.

**⚠⚠ Der teuerste Fund: 91 Lehren waren gelöscht — und der Wächter meldete Fortschritt.**
Der Abschluss-Commit von Sprint 32 (`process@a82f207`, Betreff *„Lehren cq-cv verankert“*)
hat `cm/lessons.md` von 1931 auf 26 und `pl/lessons.md` von 831 auf 26 Zeilen gekürzt:
**91 Abschnitte gelöscht, 2 hinzugefügt**, geschrieben statt angehängt.

> **Ein Bestand kann verschwinden, während sein Wächter Erfolg meldet. Und die Erklärung
> aus Sprint 33 — die Lehren hätten „nie in einem Lehrbuch gelebt“ — war ebenfalls falsch:
> beide Male wurde der BESTAND gezählt und nie die GESCHICHTE der Datei.**

Wiederhergestellt; der Beweis ist eine Zahl, die niemand gewählt hat: `ohne_vertreter`
liefert wieder **exakt die 91** aus Sprint 31, in beide Richtungen leer.

**⚠⚠ Das Gegenlesen fand sieben Fehler in fertig gemeldeter Arbeit — keinen der Autor.**
Dritter Sprint in Folge. Der bitterste: derselbe Bau, der eine Doppelung **benennt**, hat
eine neue angelegt — mit einem Kommentar, der die Gleichheit zweier Listen *behauptet*.

> **Ein Kommentar behauptet. `assertIs` stellt her.**

**⚠ Zwei eigene Fehler, benannt statt geglättet:** derselbe Schreib-statt-Anhängen-Fehler
keine Stunde nach seiner Lehre (wiederhergestellt) — und die erste Erklärung dafür war
falsch: `board.py` **hat** ihn gefunden und den Dateinamen genannt, der Aufruf lief mit
weggeworfener Ausgabe. **Eine Prüfung, deren Ausgabe man wegwirft, ist teurer als keine.**

**Zahlen:** 211 SWRs / 0 Lücken, 1529 Tests / 107 Dateien, JS 114, Organigramm grün
(21 Dateien), Workflows 8 / 0 unabgedeckt, Work Products 56 / 0, offene Aufgaben 33,
auf den Menschen wartend 0, Baselines 13 abgenommen / 13 getaggt.

## Sprint 33 (2026-08-21) — Planung und Abschluss

**Geschlossen:** `platform/T-0054`, `T-0057`, `T-0058` (**SWR-204/205/206**).
**Verschoben:** acht nach Sprint 34, Grund je im Ticket. **Briefkasten:** 0 offen, am
**Ende** gemessen. **Auf den Menschen wartend:** 0 — `pm/T-0084` wurde **im Lauf**
beantwortet.

**Entscheidung `pm/D029` (Mensch, 10:41): C.** Die vier Aufgaben, die auf das
**entschiedene** `pm/T-0077` zeigten, verweisen ab jetzt auf die **offene**
`platform/T-0060`. Damit war die namentliche Ausnahmeliste `TOTE_SPERREN_BESTAND` nach
**vier Stunden leer**.

> **⚠⚠ Eine Ausnahmeliste, die man leer bekommt, war die richtige Bauform. Der verworfene
> vierte Ticket-Zustand hätte 9 Quelldateien und 153 Literale gekostet — für eine Lage,
> die keine vier Stunden bestanden hat.**

**⚠⚠ Der Ertrag war zum zweiten Mal in Folge das Review, nicht der Bau.** Das unabhängige
Gegenlesen fand drei ernste Fehler in bereits fertig gemeldeter Arbeit; der schwerste war
ein **Zeitzonenfehler** (UTC gegen Wanduhrzeit, zwei Stunden Versatz), der eine
**Anforderung** mit der falschen Aussage gefüllt und dabei ein Ticket zu Unrecht
„korrigiert" hatte.

**⚠ Eine eigene Zusage, die keinen Leser hatte:** `pm/T-0083` (Projektgründung
`team-termine` nach `pm/D016` = B) stand als *„nächster Schritt"* im Abschlussabsatz des
geschlossenen `pm/T-0078` — mit Nummer, aber ohne Ticket. Gefunden hat es die
Sprint-Planung dieses Laufs beim Abgleich der Zusagen gegen den Bestand.

> **Eine Zusage in einem geschlossenen Ticket ist keine Aufgabe. Und eine genannte Nummer
> deckt die Lücke besonders gut zu — sie sieht aus wie ein Verweis auf etwas Vorhandenes.**

**Lehren:** `L-2026-08-21cw` (Zeitzone ist eine Maßeinheit), `cx` (jede Ausnahme braucht
eine Verfallsprüfung), `cy` (eine Tür, ein Schlüssel), `cz` (Anwesenheit ist nicht
Verwendung; eine pauschal ausgenommene Datei ist ein blinder Fleck) — alle vier mit
Vertreter, dazu `cv` aus Sprint 32 nachgeholt.

**Nicht repariert, benannt (Kap. 16):** `platform/T-0061` — **84 von 119 Lehren** stehen in
keinem Lehrbuch; „Lehren: 121" zählt Zitate, „ohne Vertreter" zählt Buchköpfe.


## Sprint 32 (2026-08-21) — Planung und Abschluss

Briefkasten **0 offen beim Start — 7 offen beim Abschluss**. Alle sieben kamen **während**
des Laufs (06:32–07:03), alle vom Auftraggeber, alle in diesem Sprint **beantwortet und
qualifiziert**. ⚠⚠ Daraus die Lehre `L-2026-08-21cs`: **„Briefkasten zuerst" ist eine
Reihenfolge und keine Zusicherung** — ein Zustand, der einmal am Anfang gemessen und am
Ende als Ergebnis berichtet wird, ist eine Momentaufnahme in der Aufmachung einer
Garantie. Gefunden hat es nicht der Briefkasten-Schritt, sondern der Kennzahlenlauf am
Ende (`platform/T-0057`).

Alle offenen Aufgaben aller 17 Einheiten gesichtet und terminiert; **aus dem Plan nichts
verschoben**. Zwei Tickets geschlossen (`platform/T-0052` → `SWR-201`, `platform/T-0053` →
`SWR-202`), **zehn** neu angelegt — neun davon aus den sieben Briefen, eines aus einer
Messung beim Bau.

**Klasse A, nicht selbst entschieden:** `T-0078` (Gründung `team-termine` **und**
Schreibrecht auf `dimitri.john83@gmail.com`) und `T-0081` (Digest-Empfänger gegen
Guardrail 1 — der Brief nennt zwei Adressen, der Guardrail erlaubt eine). Beide mit
Optionen, Frist **28.08.** und Voreinstellung; bei Schweigen gilt jeweils **A**.
`T-0079` (Core-Rollen organisationsweit gleich **besetzen**) ist **Klasse B**, hängt aber
sachlich an `T-0077` und steht deshalb auf `blocked` ohne Termin.

⚠ Die Zahl „offene Tickets" steht ab diesem Lauf wieder **einfach** da: `SWR-202` hat die
drei Erzeuger auf die `SWR-113`-Festlegung zusammengeführt, und die Festlegung hat nach
zwanzig Sprints einen **Vertreter**.

## Sprint 31 (2026-08-21) — Planung und Abschluss

Briefkasten **0 offen / 0 eingegangen** (beim Start und beim Abschluss gemessen).
Alle offenen Aufgaben aller 17 Einheiten gesichtet und terminiert; **nichts verschoben**.
Drei Tickets geschlossen, zwei neu angelegt — beide aus **Messungen** dieses Laufs und
nicht aus einem Vorrat. `pm/T-0077` bleibt beim Auftraggeber (Frist 28.08., Default A).
⚠ Der Sprintplan trägt ab diesem Lauf **zwei** Zahlen für „offene Tickets" mit ihren
Definitionen (12 nach `SWR-113`, 9 nach `kennzahlen.py`), weil die Werkzeuge zwei geben —
eine still zu wählen wäre genau der Zustand, gegen den `SWR-113` gebaut wurde
(`platform/T-0053`).
