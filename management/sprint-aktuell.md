# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 4** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **`platform/T-0006` ist geschlossen** — der Cockpit-Payload unterscheidet seit
   **SWR-108** „echte Null" von „nicht geliefert". Gewählt wurde `null` als Marke, weil
   der Payload sie mit `team: null` **schon hatte**; ein Zusatzfeld neben dem Wert wäre
   B033 gewesen, ein Herkunfts-Vokabular eine Pflegelast ohne heutigen Bedarf.
3. **Der Widget-Vertrag steht als v2** — die drei `null_unklar`-Marken und alle
   `bis_dahin`-Behelfsregeln sind **ersatzlos** weg, nicht umformuliert. `v1` bleibt als
   Beleg daneben stehen.
4. **⚠ Eine Annahme des eigenen Tickets war falsch.** `platform/T-0006` führte
   `team-dashboard` als „führt Digests, hatte noch keinen". Am eigenen Steckbrief geprüft:
   drei SLAs, kein Digest — es führt keine. Ohne diesen Fund wäre die naheliegende
   Implementierung (`isdir("digest")`) gebaut worden, und die hätte genau den Moment vor
   dem ersten Digest falsch gemeldet.
5. **`p11/T-0003` wurde zerlegt statt verschoben.** Mit `T-0006` fiel der Grund weg, mit dem
   es in Sprint 3 auf Sprint 5 gesetzt worden war. Übrig blieb „zu groß" — und dafür sieht
   `pm/D006` Zerlegen vor: **`p11/T-0004` (ADR) ist in diesem Sprint erledigt**,
   `p11/T-0005` (Layout-Entwurf) geht auf Sprint 5.
6. **486 Tests grün** (+15), Matrix **108 SWRs / 0 Lücken** (+1), Preflight STARTKLAR,
   **kein offener Brief** (48), unterminiert **0**, überfällig **0**.

## Sprint-Plan

*Sprint 4 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder blockiert.
**Fest geplant** ist Sprint 5 (HORIZONT 2); ab Sprint 6 ist die Nummer eine **Reihenfolge**,
keine Zusage.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0006 | cm | dieser Sprint | **erledigt** | SWR-108: `null` = nicht geliefert. Je Feld eine benannte Tatsache — Registry-**Datei** (nicht `laeufe == 0`), SLA-**Zusage** (nicht das Verzeichnis), **Profil** (nicht die Gruppe). Leser `app.js` mitgezogen. |
| team-dashboard/T-0001 | pl | dieser Sprint | **erledigt** (Takt läuft weiter) | Vertrag **v2**: `null_unklar`/`bis_dahin` ersatzlos entfernt, `herkunft` je Feld ergänzt. Eine Begründung der v1 widerlegt (team-dashboard führt keine Digests). |
| projects/p11/T-0004 | arch | dieser Sprint | **erledigt** | **Neu aus der Zerlegung.** ADR-P11-001: Widget-Logik am Rand, keine zweite Aufbereitung. Auflage: die „keine Daten"-Übersetzung aus `cockpitKarte` herausziehen, nicht abschreiben. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, **kein offener**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert — L-2026-08-17h (leere Stelle sieht nach „noch nicht" aus), L-2026-08-17i (fällt die Sperre, fällt der Verschiebungsgrund). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, 486 Tests grün, Matrix 108/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| platform/T-0004 | cm | Sprint 5 | in_review | SWR-107. `CI-STATUS.md` steht **unverändert auf 00:46**, vor dem Bau (01:17). **Keine Arbeit, keine Handlung** — der Beleg kommt mit dem nächsten Hostlauf. Frist 18.08.: reißt sie ohne Hostlauf, ist das kein Verzug des Teams und wird als solcher gemeldet. |
| pm/T-0043 | prob | Sprint 5 | offen | `p3`/`p5` rot. Beleg fehlt weiterhin. Dieser Sprint hat eine Möglichkeit **ausgeschlossen**: der `board-check` läuft über alle 16 Einträge fehlerfrei, auch über `p3`/`p5` — am Ticketbestand liegt es nicht. Kein `blocked` (Verweis ginge über Repo-Grenzen, B047). |
| projects/p11/T-0005 | pl | Sprint 5 | offen | **Neu aus der Zerlegung.** Layout-Entwurf (16 Kacheln auf FHD), `blocked_by: T-0004` — im eigenen Repo, deshalb diesmal als Status ausdrückbar. |
| projects/p11/T-0003 | pl | Sprint 5 | offen | Restumfang nach der Zerlegung: Konfiguration, Detailseiten, Mail-Widget, Tests je SWR, G4 als Inbox-DR. Frist 20.08. unverändert. |
| pm/T-0036 | pl | Sprint 6 | offen | Ändert das `BOARD.md`-Format, gebündelt mit `pm/T-0038` (B053). Hinter P11, weil dessen Frist früher liegt (20.08. gegen 23.08.). |
| pm/T-0038 | pl | Sprint 6 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| pm/T-0039 | pl | Sprint 7 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 8 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 9 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe. **Vorgemerkt:** dieselbe Zerlegungsfrage wie bei p11/T-0003, sobald es an der Reihe ist. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033).

**Rollenzuweisung in diesem Sprint:** `platform/T-0006` bei `cm` (Plattformfläche), der
Vertrag bei `pl` / DASH-RED, der neue ADR bei **`arch`** — das ist die einzige Umhängung
dieses Sprints, und sie ist eine Sachfrage: ein ADR ist Architekturarbeit, `T-0003` (`pl`)
ist Projektleitung.

---

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
  `CI-STATUS.md` nach 01:17. Der letzte Hostlauf war 00:46 und die Datei ist unverändert.
  Sprint 5, keine Handlung. **Zweiter Sprint in Folge** — das ist der Punkt, an dem es
  ausdrücklich in die Agenda für den Auftraggeber gehört, statt still weiterzulaufen.
* `projects/p11/T-0003` (Rest) und `projects/p11/T-0005` — zerlegt statt verschoben,
  Frist 20.08. gewahrt.
* `pm/T-0036`, `pm/T-0038`, `pm/T-0039`, `pm/T-0028`, `projects/p12/T-0003` — unverändert
  in der Reihenfolge, Gründe je Zeile oben.

**Was dieser Sprint an der Planung geändert hat.** Sprint 5 hat zwei Zeilen mehr und trägt
damit den Rest von P11; die Warteschlange ab Sprint 6 ist unverändert. Neu als Regel im
Planning verankert: **jeder Sprint, der eine Sperre auflöst, fasst den Termin des gesperrten
Tickets an** (L-2026-08-17i). Ohne das überlebt eine Verschiebung ihren Anlass.

## Was dieser Sprint über die Planung gelernt hat

**Zum dritten Mal in vier Sprints kam der Ertrag aus dem gründlichen Durchgehen einer
Liste**, nicht aus dem Bauen. Sprint 3 fand B064 beim Feldabgleich; hier fiel beim
Implementieren auf, dass die **Problembeschreibung des eigenen Tickets** einen Fall falsch
beschrieb (`team-dashboard` „führt Digests" — tut es nicht). Der Fund hat nicht nur einen
Satz korrigiert, sondern die Bauart: ohne ihn wäre die Verzeichnisregel gebaut worden.

**Und ein Muster im Planen selbst.** Der Verschiebungsgrund von `p11/T-0003` war in Sprint 3
gut begründet und in Sprint 4 hinfällig — ohne dass irgendjemand ihn zurückgenommen hätte.
Gründe verfallen leise. Das ist der Grund für die neue Planning-Regel.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (Sprint 3, 2026-08-17)

**Geplant:** 15 nicht geschlossene Aufgaben beim Start, davon **8 in diesem Sprint**
(3 Sachtickets + 5 Takt-Pflichten).
**Geschlossen:** `pm/T-0042`, `team-dashboard/T-0001` (erster Entwurf; Takt läuft weiter),
`platform/T-0005` und die fünf Takt-Pflichten.
**Neu entstanden:** `platform/T-0005` (im selben Sprint geschlossen) und `platform/T-0006`.

**Nicht geschlossen, mit Grund und neuem Termin** — beide warten auf **denselben** Beleg, und
beide ohne Zutun eines Menschen:

* `platform/T-0004` und `pm/T-0043` brauchen einen `CI-STATUS.md`, der **nach** dem SWR-107-Commit
  (01:17) entstanden ist. Der letzte Hostlauf war 00:46. Sprint 4, keine Handlung.

**Was dieser Sprint an der Planung geändert hat.** Die Warteschlange ab Sprint 5 wurde neu
geordnet, weil `platform/T-0006` dazukam: P11 baut **hinter** T-0006 statt davor, und die
Board-Format-CRs rücken hinter P11, weil P11 die frühere Frist trägt (20.08. gegen 23.08.). Vier
Tickets haben eine neue Nummer bekommen — ab Sprint 6 ist sie ausdrücklich eine Reihenfolge und
keine Zusage, deshalb ist das Umsortieren normale Planarbeit und kein Verschieben.

## Was dieser Sprint über die Planung gelernt hat

**Der Plan hat gehalten und trotzdem zwei Tickets erzeugt** — dasselbe Muster wie in Sprint 2, aber
aus anderem Grund. In Sprint 2 brachte ein Bericht Neues; hier brachte es das **gründliche
Durchgehen einer Liste**. Der Widget-Vertrag zwang dazu, 17 Felder einzeln gegen den echten Bestand
zu halten, und genau dabei fiel B064 auf — ein Fehler, der seit P10 in Mission Control stand und
den niemand gesucht hat.

Das ist der zweite Beleg in zwei Sprints für Regel 1 aus **L-2026-08-16h** (*gegen den echten
Bestand laufen, nicht gegen die Testwelt*) und ein Argument dafür, Vertrags- und Katalogarbeit
nicht als Schreibarbeit zu behandeln: sie ist eine Prüfung, die nur zufällig ein Dokument
hinterlässt.

**Was auffällt und nicht in diesem Sprint gelöst wurde:** die Feldkorrektur aus Sprint 2 ist
erledigt — `team-dashboard/T-0001` trägt weder `frist` noch `geplant_sprint` mehr und steht damit
wie die fünf anderen Dauerläufer.

## ⚠ Die unabhängige Gegenprüfung hat vier falsche Sätze dieses Laufs gefunden

Nach dem ersten Commit lief die Gegenprüfung (L-2026-08-16m). Die Suite war grün. Sie fand elf
Punkte — bemerkenswert ist ihre **Art**: die schwersten waren keine Codefehler, sondern
**Behauptungen dieses Laufs über den eigenen Code**.

* *„Aus dem Substring-Test wurde ein Präfix-Test."* **Falsch.** Das galt nur für den Zeilenfilter;
  `einstufung` suchte weiter im ganzen Text **inklusive Tag-Annotation**. Nachgestellt: ein
  Zwischenstand `p11-v0.9` mit der Nachricht *„Vorbereitung auf p11-v1.0"* wies das Projekt als
  **abgeschlossen** aus, ohne dass es je eine Baseline hatte. Der Satz stand **dreimal** — im
  Ticket, in der Doku und in einem Test-Docstring. **Jetzt behoben:** Vergleich Name gegen Name.
* *„Getragen wird das von `preflight.py` und Schritt [2/5]."* **Falsch.** `preflight.py` kennt die
  Matrix nicht. Das ausgesprochene Sicherheitsnetz war doppelt so groß gemalt wie das echte —
  ausgerechnet in dem Absatz, der den Preis einer Gate-Entfernung ehrlich nennen sollte.
* *„Fünf Regressionstests."* Einer davon war **ohne** die Korrektur grün. Durch Rückbau in einer
  Kopie geprüft: 6 von 8 fallen um, einer ist eine Gegenprobe, einer bewies nichts — er ist jetzt
  um die fehlende Zusicherung ergänzt.
* *„Teams haben kein G4, also keine Baseline."* Am echten Payload **widerlegt**: `platform` ist
  `festes-team` und trägt eine. Ein Widget, das dem ersten Vertragsentwurf gefolgt wäre, hätte
  einen real vorhandenen Wert unterdrückt.

**Dazu ein weiterer echter Fehler am selben Feld — B065.** „Letzte Baseline" war die
**lexikografisch** letzte, nicht die jüngste: `platform` zeigte `p9-v1.0`, während `p10-v1.0`
dreieinhalb Stunden jünger war, und `p10-v1.10` stünde vor `p10-v1.2`. Behoben
(`--sort=creatordate`), mit einem Test, der ohne die Änderung umfällt.

**Die widerlegten Sätze stehen wörtlich als widerlegt in den Tickets** und wurden nicht
stillschweigend ersetzt — sonst fehlt dem nächsten Leser der Hinweis, welche Art Satz hier schon
einmal ungeprüft durchging. Verankert als **L-2026-08-17g**. Suite **463 → 471**.


## Zahlen dieses Sprints

| | Sprint 1 | Sprint 2 | Sprint 3 |
|---|---|---|---|
| Tickets gesamt | 243 | 246 | **248** |
| offen / in_review | 12 / 4 | 14 / 1 | 14 / 1 |
| nicht geschlossen | 16 | 15 | **15** |
| Tests | 444 | 463 | **471** |
| Matrix | 106 / 0 | 107 / 0 | **107 / 0** |
| offene Briefe | 0 | 0 | **0** |
| unterminiert / überfällig | 0 / 0 | 0 / 0 | **0 / 0** |
