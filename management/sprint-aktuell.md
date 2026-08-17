# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 3** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **Die Zwickmühle aus Sprint 2 ist entschieden** (`pm/T-0042`, B061) — und nicht als
   Reihenfolgefrage. Das Matrix-Gate hat die CI von `platform` **verlassen** und läuft dort, wo
   es einen gleichzeitigen Stand sehen kann. Der Preis steht im Ticket **und** im Kopf der
   Workflow-Datei.
3. **Der Widget-Vertrag steht** (`team-dashboard/T-0001`) — normativ als YAML, begründet als
   Dokument. Damit ist die Eingangsbedingung für P11 und der Bezugspunkt von SWR-096 erfüllt.
4. **⚠ Beim Prüfen des Vertrags fiel ein falscher Wert auf, kein fehlender:** `p11` und `p12`
   trugen die Baseline von `p10` (**B064**) — seit P10 in Mission Control, nicht erst im
   künftigen Dashboard. **In diesem Sprint behoben** (`platform/T-0005`).
5. **Eine Annahme des Auftrags wurde widerlegt:** Ticket und Team-Charter hielten fest, kein
   Projekt liefere heute Widget-Daten. Gegen den echten Bestand geprüft liefern **alle 16**
   Einträge **dieselben 17 Felder**. Gefehlt hat die Zusage, nicht die Lieferung.
6. **471 Tests grün** (+8), Matrix **107 SWRs / 0 Lücken**, Preflight STARTKLAR, **kein offener
   Brief** (48), unterminiert **0**, überfällig **0**.

## Sprint-Plan

*Sprint 3 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (zerlegt) oder blockiert.
**Fest geplant** sind Sprint 4–5 (HORIZONT 2); ab Sprint 6 ist die Nummer eine **Reihenfolge**,
keine Zusage.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0042 | prob | dieser Sprint | **erledigt** | Weg 3 gewählt: das Matrix-Gate verlässt die CI, weil eine Repo-CI eine Cross-Repo-Aussage grundsätzlich nicht atomar prüfen kann. Preis benannt. `pm/T-0013` trägt den Verweis. |
| team-dashboard/T-0001 | pl | dieser Sprint | **erledigt** (Takt läuft weiter) | Erster Entwurf: `vertrag/widget-vertrag-v1.yaml` (normativ) + `docs/02-widget-vertrag.md` (Begründung). Alle 17 Feldnamen gegen den echten Payload aller 16 Einträge geprüft. |
| platform/T-0005 | cm | dieser Sprint | **erledigt** | B064, **in diesem Sprint entstanden und geschlossen**: `projekt_tags` filtert im Sammel-Repo nach Projektnamen. 8 Tests (6 mit nachgewiesener Deckung), Gegenprobe gegen den Altstand. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, **kein offener**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert — L-2026-08-17e (B064), L-2026-08-17f (B061-Auflösung), L-2026-08-17g (die Gegenprüfung prüft auch die Begründung). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, 471 Tests grün, Matrix 107/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest. |
| platform/T-0004 | cm | Sprint 4 | in_review | SWR-107. Netzweg weiterhin unbelegt: seit dem Bau (01:17) **kein Hostlauf**, `CI-STATUS.md` steht auf 00:46. **Keine Arbeit, keine Handlung** — der Beleg kommt mit dem nächsten `abschluss.cmd`. |
| pm/T-0043 | prob | Sprint 4 | offen | `p3`/`p5` rot. DoD 1 verlangt den Schritt aus `CI-STATUS.md` **nach** SWR-107 — der liegt nicht vor. Dieser Sprint hat stattdessen „anderer Workflow" ausgeschlossen (p3/p5/p7 unterscheiden sich nur in Kommentarzeilen, keine zweite Workflow-Datei). Kein `blocked`: der Verweis ginge über Repo-Grenzen (B047). |
| platform/T-0006 | cm | Sprint 4 | offen | **Neu aus dem Vertrag.** `kpi: {laeufe: 0}` bei 15 von 16 — „0 gemessen" und „nichts erhoben" sind derselbe Wert. SWR-096 verlangt die Unterscheidung und kann sie heute nicht bekommen. Weg bewusst offen. |
| projects/p11/T-0003 | pl | Sprint 5 | offen | Sperre gefallen (Vertrag liegt), aber **bewusst nicht vorgezogen**: drei Vertragsfelder werden bis `platform/T-0006` nur über eine Behelfsregel bedient. Davor zu bauen hieße, die SWR-096-Tests zweimal zu schreiben. Frist 20.08. bleibt gewahrt. |
| pm/T-0036 | pl | Sprint 6 | offen | Ändert das `BOARD.md`-Format, gebündelt mit `pm/T-0038` (B053). Hinter P11, weil dessen Frist früher liegt (20.08. gegen 23.08.). |
| pm/T-0038 | pl | Sprint 6 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| pm/T-0039 | pl | Sprint 7 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 8 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 9 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe, nicht eines. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und **seit diesem Sprint auch `team-dashboard/T-0001`** sind
Takt-Dauerläufer (`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre
eine zweite Aussage über dieselbe Sache (B033).

**Rollenzuweisung in diesem Sprint:** `platform/T-0005` und `platform/T-0006` liegen bei `cm`
(Plattformfläche), `pm/T-0042` bei `prob` (Problemanalyse), der Vertrag bei `pl` /
DASH-RED. Es wurde keine Aufgabe zwischen Rollen umgehängt.

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
