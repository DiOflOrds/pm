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
