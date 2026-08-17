# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 3, 2026-08-17)

1. **Die Zwickmühle aus Sprint 2 ist entschieden** — und nicht als Reihenfolgefrage. Das
   Matrix-Gate hat die CI von `platform` **verlassen**: eine CI, die je Repo läuft, kann eine
   Aussage über **alle Repos gleichzeitig** grundsätzlich nicht prüfen. Es läuft weiter, aber
   dort, wo es wahr sein kann — in `abschluss.cmd` vor dem Push, mit Abbruch (`pm/T-0042`).
2. **Der Widget-Vertrag steht** und damit die Eingangsbedingung für P11
   (`team-dashboard/T-0001`): normativ als YAML, begründet als eigenes Dokument.
3. **⚠ Beim Prüfen des Vertrags kam ein falscher Wert heraus, kein fehlender.** `p11` und `p12`
   trugen die Baseline von `p10` — seit P10 in Mission Control sichtbar. Ursache: `git tag`
   antwortet über das *Repository*, nicht über den Ordner. **In diesem Sprint behoben** (B064,
   `platform/T-0005`).
4. **Eine Annahme des Auftrags war falsch, zu unseren Gunsten.** „Kein Projekt liefert heute
   Widget-Daten" stimmt nicht: alle **16** Einträge liefern **dieselben 17 Felder**. Gefehlt hat
   die Zusage, nicht die Lieferung — das macht P11 kleiner als gedacht.
5. **468 Tests grün**, Matrix **107 SWRs / 0 Lücken**, Preflight STARTKLAR, **kein offener Brief**,
   unterminiert 0, überfällig 0.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| **Nichts Dringendes, nichts Blockierendes** | Kein Ticket wartet auf eine Handlung am Host. |
| Der nächste `abschluss.cmd` schließt zwei Tickets von selbst | `platform/T-0004` (Netzweg der Jobs-Abfrage) und `pm/T-0043` (welcher Schritt macht `p3`/`p5` rot) warten beide nur auf einen `CI-STATUS.md`, der **nach** 01:17 entstanden ist. Ohne dein Zutun. |
| Zur Kenntnis: `platform` sollte ab dem nächsten Lauf grün sein | Das ist eine **Vorhersage** und als solche notiert: trifft sie nicht ein, ist die Diagnose aus `pm/T-0042` widerlegt und das Ticket wird wiedereröffnet. |
| Zur Kenntnis: ein stiller Anzeigefehler ist weg | `p11` und `p12` zeigten im Cockpit die Baseline von `p10` als ihre eigene. Falls dir das je aufgefallen ist — es lag nicht an dir. |
| Optional, ohne Frist | Falls du ohnehin auf GitHub bist: die Lauf-Seite von `p3` nennt den roten Schritt sofort. Ist es das Secret `PLATFORM_READ_TOKEN`, ist die Behebung **Klasse A** (Zugang) und kommt dir als Inbox-DR vor — nicht vom Team entschieden. |
| ⚠ `abschluss.cmd` prüfen (aus Sprint 1, weiter offen) | Die Datei wurde in Sprint 1 versehentlich geleert und aus dem Protokoll **rekonstruiert**. Wenn du eine Vorgängerversion hast, vergleiche sie. Dieser Sprint hat **eine Zeile** darin geändert (`process` wird vor `platform` gepusht), sauber kommentiert. |

## Für das Team — die nächsten Sprints

| Sprint | Ticket | Inhalt |
|---|---|---|
| jeder | `pm/T-0001`, `pm/T-0002`, `pm/T-0003`, `platform/T-0001`, `team-mail/T-0001`, **`team-dashboard/T-0001`** | Takt-Dauerläufer |
| **4** | `platform/T-0006` | Cockpit unterscheidet „echte Null" nicht von „nicht geliefert" — Eingangsbedingung für SWR-096 |
| **4** | `platform/T-0004`, `pm/T-0043` | Beide nur Beleg lesen, sobald der nächste `CI-STATUS.md` vorliegt |
| **5** | `projects/p11/T-0003` | Widget-Dashboard — **hinter** `platform/T-0006`, sonst werden die SWR-096-Tests zweimal geschrieben |
| 6 | `pm/T-0036` + `pm/T-0038` | Board-Format, gebündelt (B053) |
| 7 | `pm/T-0039` | Am Brief weiterkommentieren |
| 8 | `pm/T-0028` | Projekt-Pool: Team gründen im HMI (Klasse A — nur vorbereiten) |
| 9 | `projects/p12/T-0003` | Renderer zusammenführen |

**Ab Sprint 6 ist die Nummer eine Reihenfolge, keine Zusage.** Der vollständige Plan steht in
`pm/management/sprint-aktuell.md`. Die Warteschlange wurde in diesem Sprint neu geordnet, weil
`platform/T-0006` dazukam — Gründe je Zeile im Plan.

**Die Feldkorrektur aus Sprint 2 ist erledigt:** `team-dashboard/T-0001` trägt weder `frist` noch
`geplant_sprint` mehr und steht damit wie die fünf anderen Takt-Dauerläufer.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint 3 (2026-08-17)

**`pm/T-0042` — die Entscheidung, die keiner der vier vorgeschlagenen Wege war.** Das Ticket bot
vier Wege an, drei davon Reihenfolge- oder Wiederholungsvarianten. Sprint 3 hat die Frage eine
Ebene tiefer gestellt: *Kann dieses Gate den Zustand, über den es urteilt, überhaupt jemals
sehen?* Nein — die SWR↔Test-Matrix ist eine Aussage über **alle** Repos **zur gleichen Zeit**, und
eine CI je Repo sieht die anderen immer so, wie der Push sie hinterlassen hat. Gewählt ist Weg 3,
aber als **Ortswechsel** und nicht als Abschwächung: dieselbe Prüfung läuft in `abschluss.cmd`
[2/5] über den vollständigen, gleichzeitigen lokalen Stand — **vor** dem Push, mit Abbruch. Für
jeden Push über `abschluss.cmd` konnte das Gate in der CI nur überflüssig (grün) oder falsch (rot)
sein. **Der Preis steht im Ticket und im Kopf der Workflow-Datei:** ein Push, der `abschluss.cmd`
umgeht, wird nicht mehr gegen die Matrix geprüft. Der Lauf checkt jetzt drei Repos aus statt
vierzehn.

**Bewusst nicht mitgerissen:** der Katalog-Check in derselben CI ist von derselben Bauart, hat aber
noch nie falsch rot gemeldet. Ein Gate auf theoretischen Verdacht abzuräumen wäre das Gegenteil der
Sorgfalt, die den Befund gefunden hat. Stattdessen eine Zeile in `abschluss.cmd`: `process` geht
vor `platform`, damit ist die häufigere Hälfte seines Rennens weg.

**`team-dashboard/T-0001` — der Widget-Vertrag.** `vertrag/widget-vertrag-v1.yaml` ist die
**einzige** Stelle mit der Feldliste; `docs/02-widget-vertrag.md` begründet und wiederholt sie
ausdrücklich nicht (zwei Listen wären B033 — eine schlechte erste Arbeit für ein Team, dessen Zweck
es ist, dass eine Seite dasselbe sagt wie ihre Quelle). Die wichtigste Frage ist damit beantwortet:
**die Felder kommen aus der vorhandenen Cockpit-Aggregation, aus keiner zweiten Quelle.**

**⚠ B064 — beim Feld-für-Feld-Prüfen fiel ein falscher Wert heraus.** `p11` und `p12` meldeten
`p10-v1.0` als ihre letzte Baseline. `git tag` beantwortet die Frage nach dem **Repository**; seit
`pm/D003` liegen Projekte ab P10 als Ordner in `projects`. Der Nachbar in derselben Funktion
(`einstufung`) war **zufällig** richtig — er sucht nach `"<projekt>-v1.0"` und filtert damit
implizit; nur die Baseline-Zeile las denselben Text ungefiltert. Dieselbe Familie wie B059.
Behoben über **eine** gemeinsame Funktion (`projekt_tags`), 5 Regressionstests, darunter der Fall,
der die Korrektur widerlegen würde (`p0` trägt `genesis-v1.0` — ein globaler Filter hätte ihm
Baseline und Status genommen). **Gegenprobe über den echten Bestand:** der Altstand aus
`git archive HEAD` meldet für p11/p12 weiterhin `p10-v1.0`, der Neustand leer.

**Neu und bewusst nicht in diesem Sprint: `platform/T-0006`.** 15 von 16 Einträgen melden
`kpi: {laeufe: 0}`, obwohl nur `p0` eine Run-Registry führt — „0 gemessen" und „nichts erhoben"
sind derselbe Wert. SWR-096 verlangt genau diese Unterscheidung. Der Weg dorthin ist **offen
gelassen**: drei Varianten stehen im Ticket, jede mit ihrem Preis, entschieden wird im Sprint, der
es baut.

**Verankert (D005, noch in diesem Lauf):** **L-2026-08-17e** (B064 — wechselt der Behälter,
wechselt die Bedeutung jeder Frage an ihn; ein Nachbar, der richtig aussieht, kann aus Versehen
richtig sein) und **L-2026-08-17f** (B061-Auflösung — vor dem Justieren eines Gates kommt die Frage
nach seinem Ort; wer ein Gate entfernt, schreibt auf, welcher echte Befund verloren geht).

**Board-Check gegen die Erwartung gelesen (B041 Regel 3):** platform **6** Tickets (+2: `T-0005`,
`T-0006`), pm **43** (unverändert — `T-0042` hat nur den Status gewechselt), gesamt **248** (+2).
Briefe organisationsweit **48**, davon **0 offen**. Matrix **107 SWRs / 0 Lücken** (unverändert —
dieser Sprint hat keine neue Anforderung gebracht, sondern einen Fehler behoben und einen Vertrag
geschrieben), **468 Tests** (vorher 463). Nicht geschlossen: **15** (unverändert — zwei zu, zwei
neu).

---

## Vorheriger Stand (Sprint 2, 2026-08-17)

## Das Wichtigste (Stand Sprint 2, 2026-08-17)

1. **Die CI-Statusprüfung hat beim ersten Lauf drei rote Repos gefunden** — `p3`, `p5` und
   `platform`. Zwei davon (`p3`, `p5`) waren seit dem 16.08. rot, rund **siebzehn Stunden
   unbemerkt**. Genau dafür wurde sie gebaut.
2. **Vier Tickets geschlossen**, alle mit dem Fremdnachweis, auf den sie seit gestern warteten:
   `platform/T-0003`, `pm/T-0010`, `pm/T-0013`, `pm/T-0026`.
3. **Eine plausible Erklärung wurde widerlegt statt übernommen.** Dass `p3`/`p5` an der
   Board-Formatänderung liegen, klang zwingend — `p7` trägt denselben Commit-Zeitpunkt **auf die
   Sekunde**, dieselbe Workflow-Datei, dieselbe Formatänderung und ist **grün**. Ohne diese
   Gegenprobe wären zwei Tickets mit falscher Begründung geschlossen worden.
4. **`platform` ist rot, weil zwei Gates einander auschecken.** `platform` prüft `p0`/`p9`, die
   Projekt-Repos prüfen `platform` — und alle werden im selben Lauf gepusht. Wer zuerst geht, sieht
   den anderen alt. **Es gibt keine Push-Reihenfolge, die beide grün macht** (B061, `pm/T-0042`). Noch im selben Sprint am **zweiten** Push bestätigt: wieder rot, wieder genau die Anforderung dieses Sprints als Lücke — die Diagnose war eine Vorhersage.
5. **463 Tests grün**, Matrix **107 SWRs / 0 Lücken**, Preflight STARTKLAR, **kein offener Brief**,
   unterminiert 0, überfällig 0.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| **Nichts Dringendes, nichts Blockierendes** | Kein Ticket wartet auf eine Handlung am Host. |
| Zur Kenntnis: zwei Repos sind rot | `p3` und `p5` (board-check) seit 16.08. 07:00. Das Team hat die naheliegende Ursache **ausgeschlossen** und rät nicht weiter — der fehlgeschlagene Schritt kommt beim nächsten `abschluss.cmd` automatisch in `CI-STATUS.md` (SWR-107, in diesem Sprint gebaut). |
| Optional, ohne Frist | Falls du ohnehin auf GitHub bist: die Lauf-Seite von `p3` nennt den Schritt sofort. Sollte es das Secret `PLATFORM_READ_TOKEN` sein, ist die Behebung **Klasse A** (Zugang) und wird dir dann als Inbox-DR vorgelegt — nicht vom Team entschieden. |
| Kleinigkeit am Host (R7) | `team-mail` zeigt seit Stunden eine „geänderte" Datei, deren Inhalt **identisch** ist: der Mount darf `.git/index` nicht neu schreiben, also bleibt die Stat-Markierung stehen. Kein Datenverlust, keine Auswirkung — `preflight` räumt die Lock-Artefakte in `.git/verwaiste-locks/`, der Parkplatz gehört gelegentlich geleert. |
| ⚠ `abschluss.cmd` prüfen (aus Sprint 1, weiter offen) | Die Datei wurde in Sprint 1 versehentlich geleert und aus dem Protokoll **rekonstruiert**. Wenn du eine Vorgängerversion hast, vergleiche sie. |

## Für das Team — die nächsten Sprints

| Sprint | Ticket | Inhalt |
|---|---|---|
| jeder | `pm/T-0001`, `pm/T-0002`, `pm/T-0003`, `platform/T-0001`, `team-mail/T-0001` | Takt-Dauerläufer |
| **3** | `platform/T-0004` | Hostlauf nennt einen Schritt → schließt SWR-107 (ohne Handlung) |
| **3** | `pm/T-0042` | Push-Reihenfolge-Zwickmühle: einen der vier Wege wählen und den Preis nennen |
| **3** | `pm/T-0043` | `p3`/`p5`: den Schritt aus `CI-STATUS.md` lesen und den Befund schreiben |
| **3** | `team-dashboard/T-0001` | Widget-Vertrag — die Sperre für P11 |
| 4 | `pm/T-0036` + `pm/T-0038` | Board-Format, gebündelt (B053) |
| 5 | `projects/p11/T-0003` | Widget-Dashboard |
| 6 | `pm/T-0039` | Am Brief weiterkommentieren |
| 7 | `pm/T-0028` | Projekt-Pool: Team gründen im HMI (Klasse A — nur vorbereiten) |
| 8 | `projects/p12/T-0003` | Renderer zusammenführen |

**Ab Sprint 5 ist die Nummer eine Reihenfolge, keine Zusage.** Der vollständige Plan steht in
`pm/management/sprint-aktuell.md`.

**Kleine Feldkorrektur für Sprint 3 (kein eigenes Ticket):** `team-dashboard/T-0001` trägt
**sowohl** `takt: je-session` **als auch** `geplant_sprint: 3`. Nach der Regel aus SWR-106 ist das
eine Doppelaussage (B033) — Takt-Dauerläufer tragen keine Nummer. Die Widerspruchsprüfung schlägt
nicht an, weil keine Frist verletzt wird; die Doppelung bleibt trotzdem eine.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint 2 (2026-08-17)

**Was der Lauf tun sollte.** Der Plan aus Sprint 1 lautete: „CI-Status auswerten, sobald
`CI-STATUS.md` existiert" — vier Tickets, die alle auf denselben Blick warteten. Der Bericht lag
vor (Stand 00:31, 15 Abfragen, `budget_erschoepft: false`).

**Was der Bericht sagte.** Acht Repos grün **für ihren eigenen Commit** (`p0`, `p1`, `p2`, `p4`,
`p7`, `p8`, `p9`, `pm`), `team-dashboard` als „kein CI zu erwarten", und **drei rot**: `p3`, `p5`,
`platform`.

**`pm/T-0010` (Stand-Datum-Flake) — geschlossen.** Acht grüne board-checks, darunter `p0` und `pm`
mit Commits **nach** Mitternacht. Der `-I "^Stand:"`-Fix trägt über die Datumsgrenze. Gegenprobe zu
den roten: alle 16 Repos regenerieren ihre `BOARD.md` heute byte-gleich — eine Stand-Drift ist als
Ursache ausgeschlossen.

**`pm/T-0013` (Push-Reihenfolge für den board-check) — geschlossen, mit einer Rückseite.**
Kriterium 2 ist erfüllt. Aber dieselbe Reihenfolge macht den CI-Lauf von `platform` rot: dessen
Matrix-Gate checkt `p0`/`p9` aus und sieht sie einen Commit alt. **Nachgestellt, nicht vermutet** —
`platform@34a44d57` gegen zwei Stände von `p0`/`p9`: vor dem Push **Exit 1, 104 SWRs, 1 Lücke
(SWR-105)**; nach dem Push **Exit 0, 105 SWRs, 0 Lücken**. Neuer Befund: `pm/T-0042` (B061).

**`pm/T-0026` (Matrix-Gate ohne `projects`) — geschlossen.** In beiden Durchläufen war `projects`
ausgecheckt; die Lücke entsteht durch die Reihenfolge, nicht durch eine fehlende Quelle. Der Fix
dieses Tickets trägt.

**`platform/T-0003` (SWR-105) — geschlossen.** Alle fünf DoD-Punkte belegt; der **Netzweg** ist
nachgewiesen, das war die offene Stelle. Die vorgesehene Stichprobe des Auftraggebers („stimmt das
Urteil mit der Actions-Seite überein?") wurde **stärker als vorgesehen** erbracht: das rote Urteil
über `platform` ließ sich lokal **unabhängig rekonstruieren**.

**Was danach kam: `platform/T-0004` / SWR-107, im selben Sprint gebaut.** Der Bericht sagt `ROT`
und nicht **warum** — und lässt damit genau die Lücke offen, die er schließen sollte. `GET
/repos/{slug}/actions/runs/{id}/jobs` ist dieselbe anmeldefreie API-Familie. Der Bericht nennt jetzt
Job und Schritt. **19 neue Tests**, alle mit injizierter Abruffunktion; die Nachfrage läuft **nach**
der Warteschleife (rot ist ein Endzustand), **einmal je rotem Repo**, gegen **dasselbe** Budget,
und ein Scheitern lässt das Repo **rot** mit „Schritt unbekannt". `in_review`, weil der Netzweg der
Jobs-Adresse erst der nächste Hostlauf belegt.

**Zwei Fälle, die beim Bauen auffielen und in keinem Ticket standen:** `skipped` ist die **Folge**
eines Fehlers und nicht der Fehler (sonst meldet die Diagnose den falschen Schritt und liest sich
trotzdem wie eine Antwort); und ein roter Lauf ohne `id` kostet jetzt keine Abfrage.

**Verankert (D005, noch in diesem Lauf):** **L-2026-08-17b** (B061 — zwei Gates, die einander
auschecken, haben keine gemeinsame Push-Reihenfolge; die Asymmetrie entscheidet, nicht die
Symmetrie) und **L-2026-08-17c** (B062 — ein Zustand ohne Grund ist eine Farbe und verschiebt die
Arbeit nur; die erste Erklärung wird gegen einen Nachbarn geprüft, bevor sie eine Ursache heißt).

**Board-Check gegen die Erwartung gelesen (B041 Regel 3):** pm **43** Tickets (+2: `T-0042`,
`T-0043`), platform **4** (+1: `T-0004`), gesamt **246** (+3). Briefe organisationsweit **48**,
davon **0 offen**. Matrix **107 SWRs** (vorher 106) / 0 Lücken, **463 Tests** (vorher 444).
Nicht geschlossen: **15** (vorher 16).

---

## Vorheriger Stand (Sprint 1, 2026-08-17)

## Das Wichtigste (Stand Sprint 1, 2026-08-17)

1. **Geplant wird ab jetzt auf Sprints, nicht auf Kalenderdaten.** Ein Sprint = ein Routine-Lauf,
   Takt **stündlich**, also rund **24 Sprints am Tag**. Wir sind in **Sprint 1** — der Zähler
   beginnt mit der Umstellung, rückwirkend wird nicht nummeriert (B056).
2. **Alle 17 offenen Aufgaben sind auf Sprints geplant**: 6 in diesem, 4 in Sprint 2, 1 in
   Sprint 3, der Rest als geordnete Warteschlange bis Sprint 8. Kein Ticket ohne Zuordnung.
3. **Für dich ist nichts mehr offen.** `pm/T-0034` ist geschlossen (die Digests im Repo belegen
   IMAP und Ollama), und der Blick auf die Actions-Seite ist mit **SWR-105** automatisiert.
4. **`frist` bleibt neben `geplant_sprint`** — Zusage nach außen und Planung des Teams. Die
   bekannte Schwäche dieser Wahl (zwei Angaben driften) wird **geprüft**: die Kachel meldet jedes
   Ticket, dessen Sprint nach seiner Frist läge. Aktuell: keins.
5. **444 Tests grün**, Matrix **106 SWRs / 0 Lücken**, Preflight STARTKLAR, kein offener Brief.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| **Nichts Dringendes** | Erstmals wartet keine Aufgabe auf eine Handlung am Host. |
| Stichprobe CI (ohne Frist) | Nach dem nächsten `abschluss.cmd`: nennt `CI-STATUS.md` denselben Commit wie die Actions-Seite? Das schließt `platform/T-0003`, `pm/T-0010`, `pm/T-0013`, `pm/T-0026`. |
| Stichprobe Sprintkachel | Cockpit öffnen: steht oben „Sprint 1 · Takt 60 Min", und sind die Warteschlangen-Zeilen als solche markiert? |
| ⚠ `abschluss.cmd` prüfen | Die Datei wurde in diesem Lauf versehentlich geleert und aus dem Protokoll **rekonstruiert**. Wenn du eine Vorgängerversion hast, vergleiche sie. |

## Für das Team — die nächsten Sprints

| Sprint | Ticket | Inhalt |
|---|---|---|
| jeder | `pm/T-0001`, `pm/T-0002`, `pm/T-0003`, `platform/T-0001`, `team-mail/T-0001` | Takt-Dauerläufer (keine Nummer, das Feld `takt` sagt es) |
| **2** | `platform/T-0003`, `pm/T-0010`, `pm/T-0013`, `pm/T-0026` | CI-Status auswerten, sobald `CI-STATUS.md` existiert |
| **3** | `team-dashboard/T-0001` | Widget-Vertrag — die Sperre für P11 |
| 4 | `pm/T-0036` + `pm/T-0038` | Board-Format, gebündelt (B053) |
| 5 | `projects/p11/T-0003` | Widget-Dashboard |
| 6 | `pm/T-0039` | Am Brief weiterkommentieren |
| 7 | `pm/T-0028` | Projekt-Pool: Team gründen im HMI (Klasse A — nur vorbereiten) |
| 8 | `projects/p12/T-0003` | Renderer zusammenführen |

**Ab Sprint 4 ist die Nummer eine Reihenfolge, keine Zusage** — bei 24 Sprints am Tag wäre alles
andere Scheingenauigkeit. Der vollständige Plan steht in `pm/management/sprint-aktuell.md`.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint 1 (2026-08-17)

**Geschlossen:** `pm/T-0041` (Umstellung auf Sprintplanung, **SWR-106**), davor im selben Lauf
`pm/T-0034` (Beleg im Repo statt Zusage) und `platform/T-0003` gebaut (**SWR-105**, CI-Status ohne
Zugangsdaten). **Fünf Briefe beantwortet** (`pm/N-0034`–`N-0037`, `projects/p11/N-0001`).

**Der Zähler ist eine Datei, keine Schätzung.** `pm/management/sprints.jsonl`, eine Zeile je
Sprint, nur angehängt, idempotent über eine Laufkennung — derselbe Lauf zweimal gestartet erhöht
nichts. **Nicht** aus der Git-Historie gezählt: eine Session schreibt mehrfach, Commits sind keine
Läufe (B056, belegt mit 42 Commits auf rund 30 Läufe).

**Gegenprobe über den echten Bestand.** Der Altstand aus `git archive HEAD`, gegen die **neue**
Plandatei gestartet, meldet **16 von 17 Zeilen als „ohne Zustand"** — grau, also ungeplant — und
kennt das Feld `sprint_nr` nicht. Der Neustand meldet 0. Das belegt den Schaden und nicht bloß ein
fehlendes Modul (Regel 3 aus L-2026-08-16h).

**Der Einwand des Teams steht im Ticket, nicht im Gedächtnis.** Der Auftraggeber hat `frist` und
`geplant_sprint` **parallel** gewählt — die Option, die das Team als schwächste bezeichnet hatte
(zwei Angaben zu „wann ist es dran" driften, B033). Umgesetzt **und** abgesichert: beide Felder
beantworten schriftlich zwei verschiedene Fragen, und `board.sprint_widerspruch` meldet jedes
Ticket, dessen Sprint **auch bei ununterbrochenem Takt** nach seiner Frist läge. Verankert als
**L-2026-08-17a**.

**Nachweis:** 444 Tests (vorher 424, +20), Matrix 106 SWRs / 0 Lücken, Preflight STARTKLAR,
`nicht_geplant: []`, `widersprueche: []`.

---

## Vorheriger Stand (2026-08-16 23:06)

## Das Wichtigste (Stand 2026-08-16 23:06)

1. **`pm/T-0032` ist erledigt — beide Teile.** Der Wunsch aus `pm/N-0025` („jeden tag, woche um
   14 Uhr") ist gebaut: `takt: taeglich@14:00`, `woechentlich@Mo-14:00`, Feld `zuletzt_erledigt`,
   Meldung in der Cockpit-Kachel als **„überfällig seit HH:MM"**. Verankert als **SWR-104**.
2. **Vorgezogen vom 19.08.**, weil das Ticket nach der Zerlegung des Vorlaufs keine Denkarbeit
   mehr trug und die früheste Frist der Organisation hielt. Damit ist die früheste Team-Frist
   jetzt der **23.08.**
3. **402 Tests grün** (vorher 380), Matrix **104 SWRs / 0 Lücken**, Preflight STARTKLAR.
4. **⚠ Zwei Befunde: B058 beim Bauen, B059 durch die Gegenprüfung** — letzterer bei
   **grüner Suite**: eine `frist` mit Uhrzeit hätte die ganze Cockpit-Seite mitgerissen, und der
   Ticket-Editor hätte den neuen Takt beim Speichern gelöscht. Beides behoben. B058: die geteilte Ampelregel rechnete in **Tagen** und hätte den
   um 15:00 versäumten 14:00-Takt als „gelb — heute fällig" ausgewiesen. Sie liegt jetzt auf
   Momenten; für reine Datumsfristen ist sie über 961 Tag-gegen-Tag-Vergleiche unverändert.
5. **Heute fällig, nur am Host lösbar: `pm/T-0034`** (17.08. — ab morgen greift B044).

---

## Für dich (E. John) — nur am Host lösbar

| Frist | Ticket | Was zu tun ist |
|---|---|---|
| **17.08.** | `pm/T-0034` | Am Host: Läuft Ollama? Ist `ASPICE-MailAutopilot` eingerichtet? |
| 18.08. | `pm/T-0013` | Blick auf die GitHub-Actions-Seite (board-check grün?) |
| 18.08. | `pm/T-0026` | derselbe Blick (CI/Matrix-Gate grün?) |
| 18.08. | `pm/T-0010` | derselbe Blick (board-check-Flake weg?) |

**Die drei 18.08.-Tickets sind ein Handgriff, nicht drei** — die Seite, die der Push-Wächter
ohnehin öffnet ([5/5] seiner Ausgabe). Ein grüner Lauf schließt alle drei.

**Neu dazu, ohne Frist: die Stichprobe zu `T-0032`.** Einem Takt-Ticket eine Uhrzeit geben, die
gerade vorbei ist (`takt: taeglich@HH:MM`) → die Cockpit-Kachel muss es als fällig melden und den
**übersprungenen** Termin nennen; nach einem Eintrag in `zuletzt_erledigt` verschwindet die Meldung
bis zum nächsten Takt. Die Stichprobe zu `T-0016` (Kachel „Sprint aktuell" unter „Letzte Session")
steht weiter offen. Beide Punkte sind **nicht** durch Tests gedeckt — die Organisation hat 400
Python-Tests und null JS-Tests; dass das offen dasteht, ist Absicht.

## Für das Team

| Frist | Ticket | Team | Inhalt |
|---|---|---|---|
| 23.08. | `pm/T-0036` | PM | „Ohne Frist"-Zähler als Org-Summe |
| 23.08. | `pm/T-0038` | PM | Feld `verantwortlich` — **mit `T-0036` bündeln** (Board-Format) |
| 23.08. | `pm/T-0039` | PM | Am Brief weiterkommentieren (`N-0031`) |
| 23.08. | `pm/T-0028` | PM | Projekt-Pool: Team gründen im HMI (Klasse A — nur vorbereiten) |
| 23.08. | `team-dashboard/T-0001` | team-dashboard | Widget-Vertrag — **die Sperre für P11** |
| 30.08. | `projects/p12/T-0003` | P12 | Sprint 1: Renderer zusammenführen |
| 30.08. | `projects/p11/T-0003` | P11 | Sprint 1: Widget-Dashboard bauen |

**Takt-Dauerläufer ohne Frist (kein Rückstand):** `pm/T-0001` (Agenda), `pm/T-0002` (Intake),
`pm/T-0003` (Lessons), `platform/T-0001` (Werkzeugpflege), `team-mail/T-0001` (wartet auf IMAP).

**Der vollständige Sprint-Plan mit Rollen, Fälligkeiten und Gründen steht in
`pm/management/sprint-aktuell.md`** — und im Cockpit. Diese Agenda bleibt die Kurzfassung; die
Workflow-Sicht ist die Plandatei (`pm/D006`).

**Reihenfolge-Hinweis für die nächste Session:** `T-0036` und `T-0038` gehören **zusammen** in
einen Lauf (beide ändern das `BOARD.md`-Format, B053) und sind damit der naheliegende nächste
Sprint-Inhalt. `T-0039` ist davon unabhängig; `T-0028` berührt Klasse A und darf nur **vorbereitet**
werden. Die neuen `takt`-Felder aus SWR-104 sind **kein** Anlass, Bestandstickets umzuschreiben —
sie sind optional, und ohne Uhrzeit verhält sich alles wie zuvor.

---

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 23:06–23:5x, Routine-Session als **Genesis-Gesamtsprint** (D004/D006).
Briefkasten beim Start: **43 Briefe, kein offener**; die **Zweitprüfung am Sessionende bestätigte
das** (B036, zehnter Lauf, dritter ohne Fund in Folge). Inbox beim Start und am Ende: **leer**.
**Kein überfälliges Ticket** (frühester Termin `pm/T-0034`, 17.08.). Fremde Änderungen: nur die
bekannte `team-mail`-Anzeige (`digest/2026-08-16-woche-digest.md`, `git diff --quiet` = 0) — der
Index-Refresh aus R7, erneut geprüft, erneut kein Commit.*

## Der Sprint dieses Laufs

**Geplant (Kernpflicht nach `pm/D006`):** **241 Tickets** aller 16 Repos gesichtet — 220 `done`,
4 `rejected`, **14 `open`, 3 `in_review`**. Die 17 nicht geschlossenen stehen **vollständig** in
`pm/management/sprint-aktuell.md`, je Zeile mit Rolle, Fälligkeit, Status und Grund.
**Unterminiert: 0. Überfällig: 0.**

**Warum `pm/T-0032` und nicht ein Ticket vom 23.08.** Die Auswahl war nach der Vorsession nicht
mehr frei. Sie hatte `T-0032` zerlegt, statt es zum vierten Mal zu verschieben, und schriftlich
festgehalten: *„Ab hier trägt das Ticket keine Denkarbeit mehr, sondern Bauarbeit."* Ein Ticket mit
der frühesten Frist, ohne offene Vorfrage und mit fertiger Abgrenzung noch einmal liegen zu lassen,
hätte genau das Muster fortgesetzt, gegen das die Zerlegung geschrieben wurde (B043/B049). Die
`23.08.`-Tickets ändern dagegen alle das `BOARD.md`-Format oder berühren Klasse A (B053/B025).

**Gebaut:** Uhrzeit-Syntax im Feld `takt` (`taeglich@HH:MM`, `woechentlich@<Mo–So>-HH:MM`, nur für
diese beiden Takte — für `monatlich@…` gäbe es keine Regel, welcher Tag gemeint ist, und sie zu
erfinden wäre Raten), neues Feld `zuletzt_erledigt`, **eine** Fälligkeitsfunktion, die durch
**dieselbe** `board.frist_ampel` mündet, und eine eigene Liste in der Cockpit-Kachel neben den
überfälligen Fristen. **Kein Scheduler:** läuft keine Session, feuert nichts — und die Anzeige sagt
„überfällig seit HH:MM" statt „erledigt" (B038).

**⚠ Der Befund dieses Laufs (B058), in eigener Sache.** Teil 1 hatte entschieden, den abgeleiteten
Termin durch die **bestehende** Ampel zu schicken — „eine Ampelregel, zwei Quellen", eine zweite
Rechnung wäre B033. Genau das wurde gebaut, und es war beim ersten Test falsch: `frist_ampel`
verglich **Kalendertage**. Der Termin „heute 14:00" ist um 15:00 verstrichen, der **Tag** aber
nicht — die geteilte Regel hätte ausgerechnet den **versäumten** Takt als „gelb, heute fällig"
ausgewiesen. Dieselbe Familie wie B057. Die Regel liegt jetzt auf **Momenten**; ein Test vergleicht
beide Fassungen für reine Datumsfristen **Tag für Tag gegen jeden Bezugstag desselben Monats**
(961 Vergleiche), damit SWR-091 seine Bedeutung behält. Und die naheliegende Abkürzung — den
Tagesbezug des Cockpits einfach als Moment zu behandeln — wurde **nicht** genommen: sie hätte
`taeglich@23:00` jeden Morgen als fällig gemeldet. Verankert als **L-2026-08-16l**.

**⚠ Zweiter Befund, gefunden von einer Gegenprüfung — nicht von der Suite (B059).** Nach dem
Commit prüfte eine unabhängige Instanz die Änderung und fand **zwei** echte Fehler, während **alle
400 Tests grün waren**: (1) `aggregation.cockpit` wäre an einer `frist` **mit Uhrzeit** gestorben —
der Filter akzeptierte sie seit SWR-104, die Tage-über-Rechnung daneben nicht; über `cockpit_alle`
hätte **ein** Ticket die **ganze** Cockpit-Seite mitgerissen, und zwar erst **nach** Ablauf des
Termins. (2) Der Ticket-Editor kannte den neuen Takt nicht und hätte ihn beim Speichern eines
**beliebigen anderen Feldes** stillschweigend gelöscht. Beides behoben, je ein Regressionstest
(Suite **402**). Die Lehre: **wer eine geteilte Regel erweitert, muss ihre Nachbarn mitziehen** —
und eine grüne Suite ersetzt keinen fremden Blick. Verankert als **L-2026-08-16m**.

**Nachweis:** **402 Tests** (vorher 380, +22), Matrix **104 SWRs / 0 Lücken**, Preflight STARTKLAR.
**Gegenprobe über den echten Abrufweg** (L-2026-08-16h): dieselbe Testwelt, dasselbe Ticket, beide
Server antworten `GET /api/cockpit` mit **HTTP 200** — der Altstand aus `git archive HEAD` meldet
`ueberfaellig: []`, `unterminiert: 0` und **kein Feld** `takt_faellig`. Das Ticket sah über die HMI
**kerngesund** aus, während sein 14:00-Termin seit Stunden versäumt war. Zweite Gegenprobe über die
Skript-Route, die auch die CI fährt: `board.py --check` endet im Altstand mit **exit 1**
(*„ungültiger takt: taeglich@14:00"*), im Neustand mit **exit 0** — der Wunsch war vorher nicht nur
unbeantwortet, er war **nicht aufschreibbar**.

**Nicht als getestet geführt:** die Kachelposition und die Telefondarstellung. 402 Python-Tests,
**null** JS-Tests (Pool-Kandidat #8, nicht beauftragt). Der Nachweis ist eine **Stichprobe des
Auftraggebers** und steht als solche im Ticket — das offen zu sagen ist B027, es als getestet zu
führen wäre B038.

---

## Vorheriger Stand (2026-08-16 22:19)

## Das Wichtigste (Stand 2026-08-16 22:19)

1. **Erster echter Gesamtsprint nach `pm/D006`:** alle Tickets aller Repos gesichtet, **18 offene
   Aufgaben, alle terminiert** — 6 in diesem Sprint, 5 warten auf dich, 11 mit Datum und Grund.
2. **Der Sprint-Plan steht ab jetzt in Mission Control**, Cockpit, direkt unter „Letzte Session".
   Die Kachel meldet auch, welche offenen Tickets in **keiner** Planzeile stehen.
3. **`pm/T-0016` ist erledigt** — und war das einzige unterminierte Ticket der Organisation, in
   keiner Liste sichtbar. Ausgerechnet der CR, der genau das beheben soll (B049, vierter Fall).
4. **`pm/T-0032` wurde zerlegt statt zum vierten Mal verschoben**: die Abgrenzung ist geschrieben,
   der Bau bleibt der 19.08. **380 Tests grün** (vorher 353), Matrix **103 SWRs / 0 Lücken**.
5. **Heute fällig, nur am Host lösbar: `pm/T-0034`** (17.08. — ab morgen greift B044).

---

## Für dich (E. John) — nur am Host lösbar

| Frist | Ticket | Was zu tun ist |
|---|---|---|
| **17.08.** | `pm/T-0034` | Am Host: Läuft Ollama? Ist `ASPICE-MailAutopilot` eingerichtet? |
| 18.08. | `pm/T-0013` | Blick auf die GitHub-Actions-Seite (board-check grün?) |
| 18.08. | `pm/T-0026` | derselbe Blick (CI/Matrix-Gate grün?) |
| 18.08. | `pm/T-0010` | derselbe Blick (board-check-Flake weg?) |

**Die drei 18.08.-Tickets sind ein Handgriff, nicht drei** — die Seite, die der Push-Wächter
ohnehin öffnet ([5/5] seiner Ausgabe). Ein grüner Lauf schließt alle drei.

**Neu dazu, ohne Frist: die Stichprobe zu `T-0016`.** Cockpit öffnen — steht „Sprint aktuell"
direkt unter „Letzte Session", und ist die Tabelle auch am Telefon lesbar? Der Punkt ist **nicht**
durch einen Test gedeckt (null JS-Tests in der Organisation); dass das offen dasteht, ist Absicht.

## Für das Team

| Frist | Ticket | Team | Inhalt |
|---|---|---|---|
| 19.08. | `pm/T-0032` | PM | Echter Uhrzeit-Takt — **Teil 1 (Abgrenzung) ist erledigt**, es bleibt der Bau |
| 23.08. | `pm/T-0036` | PM | „Ohne Frist"-Zähler als Org-Summe |
| 23.08. | `pm/T-0038` | PM | Feld `verantwortlich` — **mit `T-0036` bündeln** (Board-Format) |
| 23.08. | `pm/T-0039` | PM | Am Brief weiterkommentieren (`N-0031`) |
| 23.08. | `pm/T-0028` | PM | Projekt-Pool: Team gründen im HMI |
| 23.08. | `team-dashboard/T-0001` | team-dashboard | Widget-Vertrag — **die Sperre für P11** |
| 30.08. | `projects/p12/T-0003` | P12 | Sprint 1: Renderer zusammenführen |
| 30.08. | `projects/p11/T-0003` | P11 | Sprint 1: Widget-Dashboard bauen |

**Takt-Dauerläufer ohne Frist (kein Rückstand):** `pm/T-0001` (Agenda), `pm/T-0002` (Intake),
`pm/T-0003` (Lessons), `platform/T-0001` (Werkzeugpflege), `team-mail/T-0001` (wartet auf IMAP).

**Der vollständige Sprint-Plan mit Rollen, Fälligkeiten und Gründen steht in
`pm/management/sprint-aktuell.md`** — und ab jetzt auch im Cockpit. Diese Agenda bleibt die
Kurzfassung; die Workflow-Sicht ist die Plandatei (`pm/D006`).

**Reihenfolge-Hinweis für die nächste Session:** `T-0032` (19.08.) ist die früheste Frist und
**trägt keine Denkarbeit mehr** — die Abgrenzung steht, es ist Bauarbeit. Danach gehören `T-0036`
und `T-0038` zusammen (beide ändern das `BOARD.md`-Format); `T-0039` ist davon unabhängig.

---

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 22:19–23:05, Routine-Session als **Genesis-Gesamtsprint** (D004/D006). Briefkasten
beim Start: **43 Briefe, kein offener**; die **Zweitprüfung am Sessionende bestätigte das** (B036,
neunter Lauf, ohne Fund). Inbox beim Start und am Ende: **leer und beweisbar nichts Unverbuchtes** —
gegen die DR-Rohdaten geprüft (B047): **44 Decision Requests, alle `done`**. **Kein überfälliges
Ticket** (frühester Termin `pm/T-0034`, 17.08.). Fremde Änderungen: nur die bekannte
`team-mail`-Anzeige (`digest/2026-08-16-woche-digest.md`, `git diff --quiet` = 0) — der
Index-Refresh aus R7, erneut geprüft, erneut kein Commit.*

## Der Sprint dieses Laufs

**Geplant (Kernpflicht nach `pm/D006`):** **241 Tickets** aller 16 Repos gesichtet — 219 `done`,
4 `rejected`, **15 `open`, 3 `in_review`**. Die 18 nicht geschlossenen stehen **vollständig** in
`pm/management/sprint-aktuell.md`, je Zeile mit Rolle, Fälligkeit, Status und Grund. Keine Auswahl,
keine Kürzung — das war der Punkt.

**⚠ Der Befund, der den Sprintinhalt bestimmt hat.** `pm/T-0016` (`prio: hoch`, `change-request`)
hatte **keine Frist**, kein `takt` und stand in **keiner** der drei Agendalisten. Es war das
**einzige unterminierte Ticket der Organisation** (`cockpit_alle`: `unterminiert = 1`). Das ist der
**vierte** Auftritt von **B049** — und diesmal traf es den CR, der die Workflow-Sicht liefern soll.
Der Vorgang, der die Unsichtbarkeit beheben sollte, war selbst unsichtbar.

**Gebaut:** `platform/backend/sprint.py`, `GET /api/sprint`, Kachel **„Sprint aktuell"** unter
„Letzte Session". Gelesen wird die Datei, die die Session ohnehin schreibt — **kein zweiter Plan**
(B033). Der Zeitstempel kommt aus dem **Git-Commit**, und die Staleness-Regel wird aus
`session.stille` **importiert**, nicht abgeschrieben.

**Der Teil, der mehr tut als abschreiben.** Die Plantabelle ist von Hand geschrieben — sie ist eine
*Entscheidung* des PM und hat im Ticket kein Feld. Genau darum kann sie abdriften. Die Sicht
vergleicht sie deshalb **gegen den Bestand aller entdeckten Repos** und meldet jedes offene Ticket
ohne Planzeile (`nicht_geplant`), **über** der Tabelle. Eine Sicht, die nur wiedergibt, was ihr
vorgelegt wird, hätte den Befund oben nie finden können.

**⚠ Zweiter Befund, in eigener Sache (B057).** Beim **ersten Lauf gegen den echten Plan** meldete
der Zähler `wartet_auf_mensch = 1`, während der Klartext derselben Datei von **fünf** Aufgaben
sprach. Kein Tippfehler, ein Denkfehler: **Termin und Zuständigkeit sind zwei Fakten.** `pm/T-0034`
trägt ein Datum (17.08.) **und** wartet auf den Host. Alle 22 Tests der ersten Fassung waren grün,
weil die Testdaten dieselbe Annahme trugen wie der Code — gefunden hat es der Lauf gegen den
Bestand, wörtlich Regel 1 aus L-2026-08-16h. Die Zahl liegt jetzt **quer** zur Zerlegung.

**`pm/T-0032` zerlegt statt zum vierten Mal verschoben.** Die Vorsession hatte zugesagt, dass die
nächste freie Session `T-0032` nimmt und die Abgrenzung **schreibt statt baut**. Eingelöst: die
Trennlinie steht (*was ohne laufende Session feuern muss, gehört zum Host-Scheduler; was nur
bemerkt werden muss, ans Ticket*), die vier offenen Punkte sind entschieden, Teil 2 bleibt der
19.08. — **jetzt ohne offene Vorfrage**.

**Nachweis:** **380 Tests** (vorher 353, +27), Matrix **103 SWRs / 0 Lücken**, Preflight STARTKLAR.
Gegenprobe über den **echten Abrufweg**: der Server aus `git archive HEAD` beantwortet
`GET /api/sprint` mit **HTTP 404 „unbekannter Endpunkt"**, während `GET /api/session` im selben
Lauf **200** liefert.

**Nicht als getestet geführt: die Kachelposition.** 380 Python-Tests, **null** JS-Tests
(Pool-Kandidat #8, nicht beauftragt). Der Nachweis ist eine **Stichprobe des Auftraggebers** und
steht als solche im Ticket — das offen zu sagen ist B027, es als getestet zu führen wäre B038.

---

## Vorheriger Stand (2026-08-16 21:25)

## Das Wichtigste (Stand 2026-08-16 21:25)

1. **Du kannst diesen Block ab jetzt in Mission Control lesen** — Reiter *Cockpit*, Kachel
   „Letzte Session" ganz oben. Genau das war dein Wunsch aus `pm/N-0032`/`N-0033`.
2. **`pm/T-0040` ist erledigt** (Frist war 23.08.). Nichts lag an — 43 Briefe, **kein offener**,
   Inbox leer, kein überfälliges Ticket —, also wurde der nächste geplante CR gebaut.
3. **Fällt eine Session aus, sagt die Kachel das:** *„seit HH:MM keine Session"*. Ihr Zeitstempel
   kommt aus dem Git-Commit, nicht aus dem Text — sonst sähe ein alter Stand frisch aus.
4. **Doppelklick auf „Absenden" erzeugt keinen zweiten Brief mehr** (Ursache von `N-0028`/`N-0029`
   und `N-0032`/`N-0033`). **353 Tests grün** (vorher 336), Matrix **102 SWRs / 0 Lücken**.
5. **Heute fällig, nur am Host lösbar: `pm/T-0034`** (17.08. — ab jetzt greift B044).

---

## Für dich (E. John) — nur am Host lösbar

| Frist | Ticket | Was zu tun ist |
|---|---|---|
| **17.08.** | `pm/T-0034` | Am Host: Läuft Ollama? Ist `ASPICE-MailAutopilot` eingerichtet? |
| 18.08. | `pm/T-0013` | Blick auf die GitHub-Actions-Seite (board-check grün?) |
| 18.08. | `pm/T-0026` | derselbe Blick (CI/Matrix-Gate grün?) |
| 18.08. | `pm/T-0010` | derselbe Blick (board-check-Flake weg?) |

**Die drei 18.08.-Tickets sind ein Handgriff, nicht drei** — die Seite, die der Push-Wächter
ohnehin öffnet ([5/5] seiner Ausgabe). Ein grüner Lauf schließt alle drei.

**Neu dazu, ohne Frist: die Stichprobe zu `T-0040`.** Cockpit öffnen — steht „Letzte Session" ganz
oben, ohne Scrollen, auch am Telefon? Und einmal absichtlich doppelt auf „Absenden" klicken: es
darf **ein** Brief entstehen. Der zweite Punkt ist **nicht** durch einen Test gedeckt (null
JS-Tests in der Organisation); dass das offen dasteht, ist Absicht.

## Für das Team

| Frist | Ticket | Team | Inhalt |
|---|---|---|---|
| 19.08. | `pm/T-0032` | PM | Echter Uhrzeit-Takt (Abgrenzung zu F14) — **jetzt das früheste** |
| 23.08. | `pm/T-0036` | PM | „Ohne Frist"-Zähler als Org-Summe |
| 23.08. | `pm/T-0038` | PM | Feld `verantwortlich` — **mit `T-0036` bündeln** (Board-Format) |
| 23.08. | `pm/T-0039` | PM | Am Brief weiterkommentieren (`N-0031`) |
| 23.08. | `pm/T-0028` | PM | Projekt-Pool: Team gründen im HMI |
| 23.08. | `team-dashboard/T-0001` | team-dashboard | Widget-Vertrag — **die Sperre für P11** |
| 30.08. | `projects/p12/T-0003` | P12 | Sprint 1: Renderer zusammenführen |
| 30.08. | `projects/p11/T-0003` | P11 | Sprint 1: Widget-Dashboard bauen |

**Takt-Dauerläufer ohne Frist (kein Rückstand):** `pm/T-0001` (Agenda), `pm/T-0002` (Intake),
`pm/T-0003` (Lessons), `platform/T-0001` (Werkzeugpflege), `team-mail/T-0001` (wartet auf IMAP).

**Reihenfolge-Hinweis für die nächste Design-Session:** `T-0036` und `T-0038` gehören zusammen
(beide ändern das `BOARD.md`-Format). `T-0039` ist davon unabhängig (Briefkasten). **`T-0032` hat
jetzt die früheste Frist und ist zum dritten Mal aufgeschoben worden** — jedes Mal mit derselben
Begründung („Abgrenzungsfrage zwischen drei Taktlogiken trägt keine halbe Stunde"). Das ist das
Muster aus **B043/B049**: eine Begründung, die sich wortgleich wiederholt, ist keine Begründung
mehr, sondern ein Rückstand. Die nächste Session mit freiem Routine-Teil nimmt **`T-0032`** und
klärt zuerst die Abgrenzung schriftlich, statt zu bauen.

---

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 21:06–21:25, Routine-Session (D004, alle 30 Min). Briefkasten beim Start:
**43 Briefe, kein offener** (alle Projekte/Teams auf `status: offen` durchsucht) — die
**Zweitprüfung am Sessionende bestätigte das** (weiterhin 43, keiner offen; B036 zum achten Mal
gefahren, diesmal ohne Fund). Inbox beim Start **und** am Ende: **leer und beweisbar nichts
Unverbuchtes** — gegen die DR-Rohdaten geprüft (Ablaufregel aus B047): **44 Decision Requests,
alle `done`**. **Kein überfälliges Ticket** (frühester Termin `pm/T-0034`, 17.08. — ab morgen
greift B044). Fremde Änderungen: nur die bekannte `team-mail`-Anzeige
(`digest/2026-08-16-woche-digest.md` in `git status`, `git diff --quiet` = 0) — der Index-Refresh
aus R7, erneut geprüft, erneut kein Commit. Push: `PUSH-ANFORDERUNG.txt` war beim Start **nicht
vorhanden** (die Zeile der 20:50-Session ist abgearbeitet). Diese Session legt sie neu an.*

**Der Routine-Teil war leer — und statt „nichts zu tun" zu melden, hat die Session den nächsten
geplanten CR gebaut (`pm/T-0040` erledigt).**

Präzedenzfall ist die 19:06-Session (`pm/T-0037`). Die Wahl fiel **nicht** auf `pm/T-0032`, obwohl
es die frühere Frist trägt (19.08.): dort steht vor dem Bau eine Abgrenzungsfrage zwischen drei
Taktlogiken, die eine halbe Stunde nicht trägt — `T-0040` hatte eine ausgeschriebene DoD. Dass
diese Begründung jetzt zum dritten Mal wortgleich dasteht, ist oben als Rückstand vermerkt und
nicht als Erledigung.

**Was jetzt anders ist.** `GET /api/session` (neues Modul `platform/backend/session.py`) und die
Kachel **„Letzte Session"** als **erstes** Element des Cockpit-Tabs. Sie zeigt genau diesen Block
— **wörtlich** aus dieser Datei. Es entsteht **kein zweiter Text**: eine zweite Quelle neben der
Agenda wäre B033 und würde irgendwann abweichen.

**⚠ Der Punkt, an dem die Kachel hätte lügen können.** Im Kopf dieses Blocks steht ein
„(Stand …)". Fällt der geplante Lauf aus, bleibt die Datei stehen — und diese Zeile behauptete
weiter Frische (B038). Deshalb kommt der Zeitstempel der Kachel **ausschließlich aus dem
Git-Commit**, und die Überschriftzeile wird **gar nicht erst mit ausgeliefert**: sie ist die
einzige Stelle, über die die Textzeit hätte hereinkommen können. Nach zwei stillen Takten (2 × 30
Min) sagt die Kachel *„seit HH:MM keine Session"*; ein unlesbarer Zeitpunkt gilt als veraltet, nie
als frisch. Die Überschrift selbst wird an ihrem **Anfang** erkannt, nicht an ihrer Fassung —
Regel 2 aus **L-2026-08-16h**, derselben Lehre, die am selben Tag 10 von 30 Briefen unlesbar
gemacht hat.

**Punkt 6 mitgeliefert: der Doppeleingang ist an der Ursache repariert.** Der Absende-Knopf im
Briefkasten bleibt gesperrt, bis der Verlauf neu gezeichnet ist. Vorher gab er sich sofort frei und
lud erst 900 ms später neu — ein zweiter Klick in dieses Fenster erzeugte einen zweiten Brief
(`N-0028`/`N-0029`, `N-0032`/`N-0033`). **Kein Filter, keine Dublettenerkennung** (B050
unverändert): der Klick wird verhindert, nie ein Brief verschluckt.

**⚠ Befund B056 — eine Zahl, die aus der Historie kommt, ist noch keine Messung dessen, wonach
gefragt war.** Die DoD verlangt „die Zahl der **Sessions** des Tages". Die Git-Historie kennt keine
Sessions, nur **Commits**: am 16.08. **42 Commits** auf diese Datei bei rund **30** Läufen. Die
naheliegende Brücke — Commits über eine Zeitlücke bündeln — unterschätzt nachweislich: zwischen
`16:35:24` und `16:51:41` liegen 16 Minuten und **zwei verschiedene** Sessions. Geliefert wird
deshalb `fortschreibungen_heute`, unter seinem eigenen Namen. Eine Schätzung unter dem Namen einer
Messung wäre B027/B038. Als **L-2026-08-16i** in `process/knowledge/cm/lessons.md`.

**⚠ Zweiter Befund, in eigener Sache und in derselben Familie.** Ein `board.py`-Aufruf in der
falschen CLI-Form (`pm --status T-0040=in_progress` statt `pm status T-0040 in_progress`) hat
klaglos nur `BOARD.md` neu erzeugt und `OK: 40 Tickets validiert` gemeldet. Der Statuswechsel fand
**nicht** statt — die schon geschriebene Commit-Botschaft behauptete ihn trotzdem. Gefunden nur
beim Nachlesen von `grep '^status:'`, von keiner Meldung. Richtiggestellt per `--amend`, danach die
drei Übergänge mit **je einem Commit** neu gefahren (B052). Eine Commit-Botschaft ist eine Aussage
über den Zustand und wird geprüft wie eine.

**⚠ Die erste Gegenprobe war wertlos, und sie steht trotzdem im Nachweis.** Gegen den Altstand
scheitert die neue Testdatei mit `ImportError: cannot import name 'session'` — das belegt, dass ein
Modul fehlt, und nichts über den Schaden; wortwörtlich Regel 3 aus L-2026-08-16h. Die zweite
Gegenprobe läuft über den **echten Abrufweg**: der Server aus `git archive HEAD`, gegen dieselbe
Agenda gestartet, beantwortet `GET /api/session` mit **HTTP 404 „unbekannter Endpunkt"**. Das ist
die Beschwerde aus `N-0032`/`N-0033`, nicht ein fehlender Import.

**Nicht als getestet geführt: Punkt 6.** Die Organisation hat **353 Python-Tests und null
JS-Tests**; „JS-Frontend-Tests" ist Pool-Kandidat #8 und nicht beauftragt. Der Nachweis für den
Absende-Knopf ist eine **Stichprobe des Auftraggebers** und steht als solche im Ticket und oben.

**Regel 1 aus L-2026-08-16h eingehalten: gegen den Bestand geprüft, nicht nur gegen Testdaten.**
Nach dem Schreiben dieses Blocks lief `session.stand()` über die **echte** Agenda: geliefert werden
**820 Zeichen** — genau die fünf Punkte, **ohne** die Überschriftzeile, **ohne** die Stand-Angabe
`21:25` und **ohne** den Folgeabschnitt „Für dich". Das ist derselbe billige Vollzug, dessen Fehlen
gestern B054 erzeugt hat: einmal über die Datei laufen, die im Repo steht, und nachzählen.

**Board-Check gegen die Erwartung gelesen (B041 Regel 3):** **pm 40 Tickets** (unverändert —
`T-0040` hat den Status gewechselt, es kam keins dazu), offene pm-Tickets **13 → 12**; Briefe
organisationsweit **43** (unverändert), davon **0 offen**. Matrix **102 SWRs / 0 Lücken** (vorher
101), **353 Tests** (vorher 336), Architektur-Gate grün.

**⚠ Heute fällig, nur am Host lösbar: `pm/T-0034`** (17.08., hoch) — unverändert, kein IMAP/Ollama
in dieser Sandbox (Guardrail 2). `pm/T-0010`/`T-0013`/`T-0026` bleiben `in_review`, terminiert auf
18.08.

---

## Vorheriger Stand (2026-08-16 20:50)

### Das Wichtigste (Stand 2026-08-16 20:50)

1. **Drei Briefe waren offen, alle drei sind beantwortet** — `pm/N-0031`, `pm/N-0032`, `pm/N-0033`.
   Beim Startcheck war nur `N-0031` da; `N-0032`/`N-0033` kamen um 20:40 herein und fand die
   Zweitprüfung (**B036**, siebter Fund).
2. **⚠ Befund in eigener Sache, behoben:** Bei **10 von 30** beantworteten Briefen hat Mission
   Control unsere Antwort als **deine** Nachricht dargestellt — Frage und Antwort in einem Block,
   ohne Absender, ohne Datum. Betroffen war auch `pm/N-0030`. **336 Tests grün** (vorher 334).
3. **Zwei CRs eingeplant, nicht gebaut:** `pm/T-0039` (am Brief weiterkommentieren) und
   `pm/T-0040` (Session-Zusammenfassung in Mission Control) — beide Frist **23.08.**
4. **Morgen fällig:** `pm/T-0034` (17.08., nur am Host lösbar) — ab morgen greift B044.
5. **Inbox leer, kein wartender und kein unverbuchter DR** (gegen die DR-Rohdaten geprüft, B047).

---

## Für dich (E. John) — nur am Host lösbar

| Frist | Ticket | Was zu tun ist |
|---|---|---|
| **17.08.** | `pm/T-0034` | Am Host: Läuft Ollama? Ist `ASPICE-MailAutopilot` eingerichtet? |
| 18.08. | `pm/T-0013` | Blick auf die GitHub-Actions-Seite (board-check grün?) |
| 18.08. | `pm/T-0026` | derselbe Blick (CI/Matrix-Gate grün?) |
| 18.08. | `pm/T-0010` | derselbe Blick (board-check-Flake weg?) |

**Die drei 18.08.-Tickets sind ein Handgriff, nicht drei** — die Seite, die der Push-Wächter
ohnehin öffnet ([5/5] seiner Ausgabe). Ein grüner Lauf schließt alle drei.

## Für das Team

| Frist | Ticket | Team | Inhalt |
|---|---|---|---|
| 19.08. | `pm/T-0032` | PM | Echter Uhrzeit-Takt (Abgrenzung zu F14) |
| 23.08. | `pm/T-0036` | PM | „Ohne Frist"-Zähler als Org-Summe |
| 23.08. | `pm/T-0038` | PM | Feld `verantwortlich` — **mit `T-0036` bündeln** (Board-Format) |
| 23.08. | `pm/T-0039` | PM | **neu:** Am Brief weiterkommentieren (`N-0031`) |
| 23.08. | `pm/T-0040` | PM | **neu:** Session-Zusammenfassung in Mission Control (`N-0032`) |
| 23.08. | `pm/T-0028` | PM | Projekt-Pool: Team gründen im HMI |
| 23.08. | `team-dashboard/T-0001` | team-dashboard | Widget-Vertrag — **die Sperre für P11** |
| 30.08. | `projects/p12/T-0003` | P12 | Sprint 1: Renderer zusammenführen |
| 30.08. | `projects/p11/T-0003` | P11 | Sprint 1: Widget-Dashboard bauen |

**Takt-Dauerläufer ohne Frist (kein Rückstand):** `pm/T-0001` (Agenda), `pm/T-0002` (Intake),
`pm/T-0003` (Lessons), `platform/T-0001` (Werkzeugpflege), `team-mail/T-0001` (wartet auf IMAP).

**Reihenfolge-Hinweis für die nächste Design-Session:** `T-0036` und `T-0038` gehören zusammen
(beide ändern das `BOARD.md`-Format). `T-0039` und `T-0040` sind davon **unabhängig** — sie
berühren Briefkasten bzw. Cockpit, nicht das Board, und können getrennt laufen.

---

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 20:36–20:50, Routine-Session (D004, alle 30 Min). Briefkasten beim Start:
**ein offener Brief** (`pm/N-0031`, 18:36), gefunden bei der Durchsuchung aller Briefe aller
Projekte/Teams auf `status: offen`; die **Zweitprüfung fand zwei weitere** (`N-0032` 20:40:14,
`N-0033` 20:40:32, wortgleich). **Alle drei beantwortet.** Inbox beim Start: **leer und beweisbar
nichts Unverbuchtes** — gegen die DR-Rohdaten geprüft (Ablaufregel aus B047): kein
`decision-request` mit Status ≠ `done`. **Kein überfälliges Ticket** (frühester Termin
`pm/T-0034`, 17.08.). Fremde Änderungen: nur die bekannte `team-mail`-Anzeige
(`digest/2026-08-16-woche-digest.md` in `git status`, `git diff --quiet` = 0) — der Index-Refresh
aus R7, erneut geprüft, erneut kein Commit. Push: `PUSH-ANFORDERUNG.txt` war beim Start **nicht
vorhanden** (die Zeile der 20:35-Session ist abgearbeitet). Diese Session legt sie neu an.*

**⚠ Der Befund dieser Session: Mission Control hat unsere Antworten als deine Nachrichten
dargestellt (B054).**

`briefkasten._parse` trennte Nachricht und Team-Antwort an einer **wörtlichen** Überschrift:
`## Antwort (Team, JJJJ-MM-TT)`. Genau diese Fassung erzeugt der zugehörige Test selbst — er war
seit P4 grün. Die **Routine-Sessions** schreiben seit dem 15.08. eine andere:
`## Antwort des Teams (Routine-Session, JJJJ-MM-TT HH:MM)`, mit Uhrzeit, weil bei einem
30-Minuten-Takt das Datum nicht mehr unterscheidet.

**Folge, gezählt statt vermutet:** bei **10 von 30** beantworteten pm-Briefen blieb `antwort` leer
und die vollständige Team-Antwort stand im **Nachrichtenblock**. Die Chat-Ansicht rendert den
Antwortblock nur bei gefülltem `b.antwort` (`app.js`) — sie zeigte Frage und Antwort als **einen**
Text, ohne Absender und ohne Datum. Betroffen war unter anderem **`pm/N-0030`**, also genau der
Brief, auf den sich `N-0031` bezieht. Die Vermutung, dass der Wunsch „direkt weiterkommentieren"
**daher** kommt, steht offen in der Antwort — sie ist nicht belegbar, aber sie zu verschweigen
wäre unredlich.

**⚠ Warum das niemandem auffiel.** Der Fehler hat keine Meldung, kein rotes Gate, keinen
Stacktrace. Er sieht nur falsch aus, und zwar ausschließlich dort, wo niemand aus dem Team
hinschaut: in der HMI des Auftraggebers. Der Preflight zählt Briefe nach `status`, nicht nach
Lesbarkeit; die Matrix meldete SWR-050 als verifiziert — durch einen Test, der seine eigene
Eingabe erzeugt. Als **L-2026-08-16h** in `process/knowledge/cm/lessons.md`.

**Behoben (Klasse C, Werkzeugpflege).** `briefkasten.spalte_antwort` erkennt die **Überschrift**
statt ihrer Fassung und liest das Datum (mit Uhrzeit, wenn vorhanden) aus der Kopfzeile. Alle 30
beantworteten Briefe werden jetzt getrennt gelesen; `N-0030` zeigt Nachricht **292** statt 5527
Zeichen und Antwort **5175** statt 0. **336 Tests** (vorher 334), Matrix **101 SWRs / 0 Lücken**,
SWR-050 von 1 auf **3** Tests.

**⚠ Der Test, der den Schaden benennt — und die Lehre daraus.** Der erste Gegenprobentest
scheiterte gegen den Altstand nur mit `AttributeError` (die Funktion gab es dort nicht) — das
belegt nichts über den Schaden. Der zweite geht über den echten Lesepfad `liste()` und sichert zu,
dass die Team-Antwort **nicht in `nachricht`** landet; gegen den Altstand scheitert er mit
`AssertionError`. Danach `briefkasten.py` bitgleich zurückgeschrieben.

**Nicht gebaut, eingeplant als `pm/T-0039`** (Klasse B, Frist **23.08.**): der Brief wird ein
Verlauf aus beliebig vielen Beiträgen, „Antworten"-Feld je Karte, bestehende 33 Briefe ohne
Migration lesbar. **Der Punkt, an dem die Minimallösung schaden würde:** Ein Kommentar an einem
Brief mit `status: beantwortet` wird von **keiner** Session gesehen — `offene()` zählt nur
`status: offen`, und genau diese Zahl trägt Preflight und Cockpit-Kachel. Ohne Status-Rücksetzung
wäre der CR schädlich statt nützlich (B038: der stille Ausfall ist teurer als der laute).

**Die zweite Frage aus `N-0031` beantwortet und als Punkt e) in `pm/T-0038` verbucht.**
*Warum stehen die Mensch-Tasks nicht in der Inbox?* Weil die Inbox **unentschiedene Decision
Requests** zeigt — zwei Filter in `inbox._dr_tickets`: `typ == "decision-request"` und kein
Entscheidungsvermerk im Text (SWR-039). `pm/T-0034`, `T-0013`, `T-0010`, `T-0026` haben
`typ: problem`. Die Inbox lehnt sie nicht ab, sie **kennt sie nicht**: für „der Mensch muss
handeln" gibt es keinen Kanal. Das ist derselbe Befund wie `N-0030`, von der anderen Seite — dort
fehlte das Feld, hier die Ansicht. **Nicht in dieselbe Liste**, sondern als eigener Abschnitt am
selben Ort: an der Inbox-Liste hängen die Entscheidungsknöpfe (`optionen`/`default`, SWR-042), und
ein Eintrag ohne Optionen erzwänge dort Knöpfe, die nichts tun — **B033** zum zweiten Mal in zwei
Tagen.

**`N-0032`/`N-0033`: der Inhalt existiert, die Ausgabe fehlt (`pm/T-0040`, Frist 23.08.).** Jede
Session schreibt den Stand in **diese Datei** (Block „Das Wichtigste", max. fünf Zeilen seit B050)
und in `PROJEKTSTATUS-UPDATE.md`. **Kein** HMI-Endpunkt liefert eine der beiden aus. Quelle wird
die Agenda, weil sie im pm-Repo liegt und committet ist; `PROJEKTSTATUS-UPDATE.md` liegt im
Wurzelordner, also in **keinem** Repo. **Die Kachel bekommt ihren Zeitstempel aus dem Commit, nicht
aus dem Text** — fällt der geplante Lauf aus, bleibt die Datei stehen, und ein alter Stand sähe aus
wie ein frischer (B038). Und sie muss sagen können, dass **keine** Session lief: *„seit HH:MM keine
Session"*.

**Zweiter Doppeleingang, Ursache lokalisiert, weiterhin kein Filter.** `N-0032`/`N-0033` kamen 18
Sekunden auseinander (nach `N-0028`/`N-0029`, B050). Der Absende-Knopf gibt sich frei, **bevor**
der Verlauf neu geladen ist (`app.js`, `setTimeout(lade, 900)`) — ein zweiter Klick in dieses
Fenster erzeugt einen zweiten Brief. Als Punkt 6 in `T-0040`. Eine Dublettenerkennung bleibt
abgelehnt, Begründung aus B050 unverändert: ein Filter, der Briefe still verschluckt, ist teurer
als ein doppelter Brief.

**Board-Check gegen die Erwartung gelesen (B041 Regel 3):** **pm 40 Tickets** (vorher 38,
+`T-0039`, +`T-0040`), offene pm-Tickets **11 → 13**; Briefe organisationsweit **43** (vorher 40),
davon **0 offen** nach dieser Session.

**⚠ Morgen fällig, nur am Host lösbar: `pm/T-0034`** (17.08., hoch) — unverändert, kein
IMAP/Ollama in dieser Sandbox (Guardrail 2). `pm/T-0010`/`T-0013`/`T-0026` bleiben `in_review`,
terminiert auf 18.08.

---

## Vorheriger Stand (2026-08-16 20:35)

1. **Dein Brief `pm/N-0030` ist beantwortet — und er hat einen echten Werkzeugbefund getroffen
   (B053).** Das Board kann „wer arbeitet daran?" **nicht** beantworten: die einzige
   Zuordnungsspalte ist `rolle`, und die nennt die Fachrolle, nicht den Ausführenden.
2. **Neu getrennt: „Für dich" und „Für das Team" (siehe direkt unten).** **4 Tickets** warten auf
   dich, **6** auf das Team, **5** sind Takt-Dauerläufer ohne Rückstand.
3. **Morgen fällig:** `pm/T-0034` (17.08., nur am Host lösbar) — ab morgen greift B044.
4. **Eingeplant, nicht gebaut: `pm/T-0038`** (Feld `verantwortlich`, Frist **23.08.** — bewusst
   dieselbe wie `pm/T-0036`, weil beide dem `BOARD.md` eine Spalte/Zeile hinzufügen und zwei
   getrennte Formatänderungen am 16.08. früh schon alle board-checks rot gemacht haben).
5. **Inbox leer, kein wartender und kein unverbuchter DR** (gegen die DR-Rohdaten geprüft, B047).

---

**Für dich (E. John) — nur am Host lösbar**

| Frist | Ticket | Was zu tun ist |
|---|---|---|
| **17.08.** | `pm/T-0034` | Am Host: Läuft Ollama? Ist `ASPICE-MailAutopilot` eingerichtet? |
| 18.08. | `pm/T-0013` | Blick auf die GitHub-Actions-Seite (board-check grün?) |
| 18.08. | `pm/T-0026` | derselbe Blick (CI/Matrix-Gate grün?) |
| 18.08. | `pm/T-0010` | derselbe Blick (board-check-Flake weg?) |

**Die drei 18.08.-Tickets sind ein Handgriff, nicht drei** — die Seite, die der Push-Wächter
ohnehin öffnet ([5/5] seiner Ausgabe). Ein grüner Lauf schließt alle drei.

**Für das Team**

| Frist | Ticket | Team | Inhalt |
|---|---|---|---|
| 19.08. | `pm/T-0032` | PM | Echter Uhrzeit-Takt (Abgrenzung zu F14) |
| 23.08. | `pm/T-0036` | PM | „Ohne Frist"-Zähler als Org-Summe |
| 23.08. | `pm/T-0038` | PM | Feld `verantwortlich` (dieser Brief) — **mit `T-0036` bündeln** |
| 23.08. | `pm/T-0028` | PM | Projekt-Pool: Team gründen im HMI |
| 23.08. | `team-dashboard/T-0001` | team-dashboard | Widget-Vertrag — **die Sperre für P11** |
| 30.08. | `projects/p12/T-0003` | P12 | Sprint 1: Renderer zusammenführen |
| 30.08. | `projects/p11/T-0003` | P11 | Sprint 1: Widget-Dashboard bauen |

**Takt-Dauerläufer ohne Frist (kein Rückstand):** `pm/T-0001` (Agenda), `pm/T-0002` (Intake),
`pm/T-0003` (Lessons), `platform/T-0001` (Werkzeugpflege), `team-mail/T-0001` (wartet auf IMAP).

---

*Ab hier: Belege und Details zum Nachlesen.*

*Stand: 2026-08-16 20:06–20:35, Routine-Session (D004, alle 30 Min). Briefkasten beim Start:
**ein offener Brief** — `pm/N-0030` (18:02), gefunden bei der Durchsuchung aller **40** Briefe
aller Projekte/Teams auf `status: offen`; **beantwortet**. Inbox beim Start: **leer und beweisbar
nichts Unverbuchtes** — gegen die DR-Rohdaten geprüft (Ablaufregel aus B047): **kein einziger
`decision-request` mit Status ≠ `done`** (47 DRs geprüft). **Kein überfälliges Ticket**
(frühester Termin `pm/T-0034`, 17.08.). Fremde Änderungen: nur die bekannte `team-mail`-Anzeige
(`digest/2026-08-16-woche-digest.md` in `git status`, `git diff --quiet` = 0) — der Index-Refresh
aus R7, erneut geprüft, erneut kein Commit. Push: `PUSH-ANFORDERUNG.txt` war beim Start **nicht
vorhanden** (die Zeile der 19:35-Session ist abgearbeitet). Diese Session legt sie neu an.*

**Der Brief war die Arbeit — und er war kein Auskunftswunsch, sondern ein Befund (B053).**

`pm/N-0030` stellt zwei Fragen in einem Satz, und nur die zweite ist ein Werkzeugbefund:

1. *Was ist als nächstes geplant?* — aus dem Bestand beantwortbar. Als Momentaufnahme mit
   Zeitstempel in der Antwort geliefert und ab jetzt hier oben als stehende Agenda-Struktur.
2. *Wer arbeitet daran — Team oder Mensch?* — **nicht** beantwortbar. Das ist `pm/T-0038`.

**⚠ Die Auflösung existiert seit der Rollen-Registry und wird von niemandem gelesen.**
`process/roles/registry.yaml` trägt je Rolle ein Feld `besetzung: ki | mensch | script` — elf
Rollen auf `ki`, genau eine (`MENSCH`, *Auftraggeber / Eskalationsinstanz*) auf `mensch`. Gelesen
wird es von **keiner** Ausgabe: nicht vom generierten `BOARD.md` (Spalten ID, Titel, Typ, Takt,
**Rolle**, Prio, Sprint, blockiert durch), nicht von der Cockpit-Kachel, nicht vom Preflight.

**⚠ Der Beleg, dass das nicht theoretisch ist.** Vier offene Tickets sind ausschließlich am Host
durch den Menschen lösbar und tragen trotzdem eine KI-Rolle: `pm/T-0034` und `pm/T-0013`/`T-0010`
(`prob`), `pm/T-0026` (`cm`). In `T-0034` lautet eine Abschnittsüberschrift wörtlich *„Was zu
prüfen ist (am Host, eine Handlung des Auftraggebers)"*, in `T-0026` *„Voraussetzung beim
Menschen"* — im **Fließtext**, in keinem Feld. **Vier von zehn terminierten offenen Tickets sehen
im Board aus wie Teamaufgaben.** Wörtlich das Muster aus **B043**: die Information ist vollständig
da, aber nur an einer Stelle, an die keine Übersicht sieht.

**⚠ Die naheliegende Abkürzung wäre ein stiller Schaden gewesen.** `rolle: mensch` auf die vier
Tickets zu setzen, hätte die Frage scheinbar gelöst. Das Feld hat in `board.py` aber eine
**zweite, verhaltensändernde** Bedeutung: Tickets mit `rolle: mensch` sind Gates und von der
Status-Übergangsprüfung **ausgenommen** (`t.get("rolle") != "mensch"` in `validiere`). Die
Umstellung hätte vier Tickets ohne eine einzige Meldung ihre Übergangsprüfung gekostet — ein Feld
für zwei Zwecke, die Familie aus **B033**. Deshalb ein **eigenes** Feld, kein umgedeutetes. Als
**L-2026-08-16g** in `process/knowledge/cm/lessons.md`.

**Nicht gebaut, eingeplant als `pm/T-0038` (Klasse B, Frist 23.08.):** Feld
`verantwortlich: team | mensch`, sichtbar als **Board-Spalte** und im Cockpit, Preflight-Zeile
*„n Tickets warten auf den Menschen"* **mit den Refs** statt nur einer Zahl (B038), und bei
`mensch` ein Pflichtabschnitt *„Handlung beim Menschen"* im Ticket — sonst wäre die Zuordnung eine
Behauptung ohne Beleg. **Warum nicht in dieser Session:** Ticket-Schema, Board-Format,
Cockpit-Vertrag und Preflight-Ausgabe gleichzeitig, in einer 30-Minuten-Routine, ist genau
B025/B038. **Warum dieselbe Frist wie `pm/T-0036`:** beide fügen dem generierten `BOARD.md` etwas
hinzu, und zwei getrennte Formatänderungen am Board haben am 16.08. früh sämtliche
board-check-Workflows rot gemacht (`pm/T-0013`).

**Sofort von Hand angewandt, was ohne Code geht:** die Trennung „Für dich" / „Für das Team" in
dieser Agenda — die beiden Tabellen oben. Sie ersetzt keinen Code, aber sie beantwortet die Frage
des Briefes ab sofort an der Stelle, an der der Auftraggeber ohnehin nachliest.

**Kein Code geändert, deshalb keine neuen Tests.** **334 Tests**, Matrix **101 SWRs / 0 Lücken**
unverändert. Board-Check gegen die Erwartung gelesen (B041 Regel 3): **pm 38 Tickets** (vorher 37,
+`T-0038`), offene pm-Tickets **10 → 11**; Briefe organisationsweit **40** (vorher 39), davon
**0 offen** nach dieser Session.

**⚠ Morgen fällig, nur am Host lösbar: `pm/T-0034`** (17.08., hoch) — unverändert, kein
IMAP/Ollama in dieser Sandbox (Guardrail 2).

---

## Vorheriger Stand (2026-08-16 19:35)

1. **Deine Inbox ist leer.** Du hast `p12/T-0002` um **19:11** mit **G1a** entschieden — mitten in
   dieser Session. **Verbucht:** G1-Vermerk in beiden Requirements-Dokumenten, Sprint 1 als
   `p12/T-0003` beauftragt (Frist **30.08.**), der DR geschlossen. SWRs bleiben `draft` (B027).
2. **Dein Brief ist beantwortet:** `team-dashboard/N-0001` („wie ist der stand zum projekt").
   Kurzfassung: P11 hat beide Freigaben, Sprint 1 läuft — was anhängt, ist **unsere** Aufgabe
   (der Widget-Vertrag `team-dashboard/T-0001`, Frist 23.08., noch nicht entworfen).
3. **Morgen fällig:** `pm/T-0034` (17.08., nur am Host lösbar) — ab morgen greift B044.
4. **Weiterhin für dich:** ein Blick auf die GitHub-Actions-Seiten schließt `pm/T-0010`,
   `T-0013`, `T-0026` (Frist 18.08.).
5. **Erledigt: `pm/T-0037` (B051).** Der „Starten"-Knopf verschiebt den Pool-Kandidaten jetzt nach
   „Realisiert" statt ihn zu löschen, und das erzeugte Decision-Log bekommt seinen Tabellenkopf —
   der nächste Knopfdruck braucht keine Handarbeit mehr. 334 Tests grün.

*Ab hier: Belege und Details zum Nachlesen.*

**⚠ Zwei Vorgänge kamen während der Session herein — beide fand erst die Zweitprüfung (B036,
sechster Fund).** Beim Start um 19:06 war der Briefkasten leer (38 Briefe) und `p12/T-0002`
unentschieden. Bei der Zweitprüfung am Sessionende: **39 Briefe, einer offen**, und `p12/T-0002`
trug den Vermerk **G1a (19:11)**. Beides ist verbucht bzw. beantwortet; die Zweitprüfung am
Sessionende ist damit zum sechsten Mal der Grund, dass ein Vorgang nicht bis zur nächsten Session
liegengeblieben ist.

**`p12/D001`/G1a verbucht (Klasse C — die Entscheidung war Klasse A und ist gefallen).**
G1-Vermerk in `requirements/stakeholder` **und** `requirements/software`; **SWR-097–101 bleiben
`draft`** (B027 — G1a beauftragt den Sprint, es verifiziert keine Anforderung); Sprint-1-Ticket
**`p12/T-0003`** (Frist 30.08.) mit ausgeschriebener **Reihenfolge**: erst die
Teststrecken-Entscheidung (R5) im ADR, dann das Delta zu ADR-002, dann der
Vollständigkeitsnachweis (SWR-099) **gegen den Bestand**, erst dann die Umstellung. Im Ticket
steht ausdrücklich: führt der Weg zu Kosten oder einem neuen externen Werkzeug, ist das **Klasse A**
und geht als DR in die Inbox, nicht in den Sprint. `T-0002` über die erlaubten Übergänge
geschlossen — **mit Commit je Übergang** (B052, siehe unten).

**Brief `team-dashboard/N-0001` beantwortet.** Der Stand zu P11 in kurz, und die ehrliche Zuordnung:
Nicht P11 hängt, sondern der Widget-Vertrag dieses Teams. Mitgenannt der bekannte Werkzeugbefund —
`p11/T-0003` steht `open` statt `blocked`, weil `blocked_by` nicht über Repo-Grenzen reicht; die
Frist trägt dort die Aussage, die sonst der Status getragen hätte.

*Stand: 2026-08-16 19:06–19:35, Routine-Session (D004, alle 30 Min). Briefkasten: beim Start
**leer** (38 Briefe aller Projekte/Teams auf `status: offen` durchsucht, kein Treffer) — die
**Zweitprüfung am Sessionende fand einen neuen**: `team-dashboard/N-0001`, **beantwortet**.
Inbox beim Start: **ein wartender DR** (`p12/T-0002`, G1), nichts Unverbuchtes — gegen die
DR-Rohdaten geprüft (Ablaufregel aus B047). Um **19:11** hat der Auftraggeber ihn mit **G1a**
entschieden, mitten in der Session; gefunden hat es die Zweitprüfung gegen die DR-Rohdaten,
**nicht** `inbox.liste` (die filtert entschiedene DRs bauartbedingt heraus, SWR-039/B047).
**Verbucht.** Am Ende: **kein wartender und kein unverbuchter DR — die Inbox ist leer.** **Kein
überfälliges Ticket** (frühester Termin `pm/T-0034`, 17.08.), **Org-Summe „ohne Frist" = 0**
(alle sieben Kacheln einzeln gelesen, nicht nur eine — B049); `mail_digest.faellig(1)` und
`faellig(7)` beide `False`. Push: `PUSH-ANFORDERUNG.txt` war beim Start **nicht vorhanden** — die
Zeile der 18:35-Session ist abgearbeitet (Wächter-Erfolg **18:30:26**, `OK - alles geprueft und
gepusht`, pm und projects gepusht). Diese Session legt sie neu an (Repos: platform, pm, process,
p0, projects).*

**Es lag nichts an — und genau dafür ist der geplante Backlog da (`pm/T-0037` gebaut).**

Der Routine-Durchlauf war in wenigen Minuten leer: kein offener Brief, keine gefallene
Entscheidung zu verbuchen, kein fälliges Takt-Ticket, kein Termin, der heute reißt. Statt die
Session mit „nichts zu tun" zu schließen, ist der **nächste geplante CR** gebaut worden —
`pm/T-0037`, eingeplant von der Vorsession mit der ausdrücklichen Begründung *„nicht nebenbei,
weil diese Session eine Klasse-A-Entscheidung zu vollziehen hat"*. Diese Session hatte nichts
daneben; damit fällt der Grund für den Aufschub weg. (Der frühere Termin liegt bei `pm/T-0032`,
19.08. — bewusst **nicht** genommen: dort steht vor dem Bau eine Abgrenzungsfrage zwischen drei
Taktlogiken, die eine halbe Stunde nicht trägt. `T-0037` hat eine ausgeschriebene DoD.)

**Was jetzt anders ist (`pm/T-0037`, Befund B051):**

1. `kandidat_starten` **verschiebt** die Kandidatenzeile nach „Realisiert" (`# | Kandidat | Wohin |
   Beleg`) statt sie zu löschen — im selben Schreibvorgang und Commit. Fehlt der Abschnitt, wird er
   angelegt. Die Nummer bleibt erhalten, „Wohin" nennt das Projekt, „Beleg" das G0-Ticket.
2. Das erzeugte Decision-Log trägt den **Tabellenkopf** (wortgleich zu P10/P11); der
   Platzhaltersatz entfällt, weil er nach der ersten Entscheidung falsch wurde.

**⚠ Der Test, der den Schaden wirklich benennt.** Für Befund 2 hätte ein „steht der Kopf da?"
gereicht. Stattdessen hängt `test_angehaengte_entscheidungszeile_steht_unter_gueltigem_kopf` eine
echte D000-Zeile an und lässt `aggregation.parse_md_tabellen` darüberlaufen: **gegen den Altstand
findet der Parser 0 Tabellen.** Die Entscheidung war im HMI also nicht als Eintrag lesbar — nicht
bloß unschön formatiert. Gegenprobe gefahren (DoD-Punkt 4): **alle fünf neuen Tests scheitern
gegen `git show HEAD:backend/pool.py`**, danach `pool.py` bitgleich zurückgeschrieben.
**334 Tests** (vorher 329), Matrix **101 SWRs / 0 Lücken** unverändert — SWR-089 zählt jetzt 22
statt 17 Tests, es entsteht keine neue Anforderungsfläche.

**⚠ Eigener Befund dieser Session: „über die erlaubten Übergänge geschlossen" war bisher nur zur
Hälfte belegt (B052).** Die Kette `open → in_progress → in_review → done` wurde in drei
`board.py status`-Aufrufen **ohne Zwischencommit** gefahren — so, wie es seit sieben Sessions in
den Fußzeilen steht. `board.py pm --check` meldete danach `unzulässiger Status-Übergang:
open -> done`: `board.validiere` vergleicht gegen **HEAD**, nicht gegen den vorigen Aufruf. Für die
Prüfung existieren Zwischenschritte nur, wenn sie committet sind. **Das ist die richtige Prüfung an
der einzigen Stelle, die sie belegen kann** — ein Ticket, dessen Zwischenschritte nur in der
Arbeitskopie stattgefunden haben, hat sie nicht nachweisbar durchlaufen (B038-Familie). Behoben mit
**einem Commit je Übergang**, jeder mit der Begründung in der Botschaft. Als **L-2026-08-16f** in
`process/knowledge/cm/lessons.md`.

**Fremde Änderung geprüft und verbucht (B041).** `projects/p12/tickets/T-0002.md` trug beim Start
eine uncommittete Zeile **„Benachrichtigt: 2026-08-16 per E-Mail (SWR-033)"** — der Marker aus
`platform/scripts/dr_benachrichtigung.py`, geschrieben vom DR-Mailversand am Host nach der
18:35-Session. Inhaltlich echt, deshalb **eigener Commit vor der Sessionarbeit**. Die bekannte
`team-mail`-Anzeige (`digest/2026-08-16-woche-digest.md` in `git status`, `git diff --quiet` = 0)
ist unverändert der nicht durchlaufende Index-Refresh aus R7 — **erneut geprüft, erneut kein
Commit**.

**⚠ Morgen fällig, nur am Host lösbar: `pm/T-0034`** (17.08., hoch) — unverändert, kein
IMAP/Ollama in dieser Sandbox (Guardrail 2). `pm/T-0010`/`T-0013`/`T-0026` bleiben `in_review`,
terminiert auf 18.08. — sie warten auf den Blick auf die GitHub-Actions-Seiten.

**Board-Check gegen die Erwartung gelesen (B041 Regel 3):** pm **37 Tickets** (unverändert,
`T-0037` gewechselt, nicht dazugekommen), offene pm-Tickets **11 → 10**; **p12 3 Tickets**
(vorher 2, +`T-0003`); Briefe organisationsweit **39** (vorher 38).

---

*Vorheriger Stand: 2026-08-16 18:04–18:35, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — alle
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
