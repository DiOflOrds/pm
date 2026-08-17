# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 11** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **⚠⚠ Der Auftraggeber hat Kalenderfristen zum zweiten Mal gerügt — und die Ursache
   war unsere eigene Prüfung.** `unterminierte_tickets` (SWR-091 → SWR-114 → SWR-117)
   meldet jedes offene Ticket, das **kein `frist`-Feld** trägt. Also schreibt jeder Lauf
   ein Datum hinein. Die Gegenentscheidung steht seit **SWR-106** (Anforderungen v1.12):
   *„Terminierung auf Sprints statt auf Kalenderdaten"* — derselbe Satz steht im Kopf des
   Sprintzählers. **Die Entscheidung hat keine Prüfung mitgeändert.** Gebaut: **SWR-125**
   (`platform/T-0012`).
   > **Eine Entscheidung, die keine Prüfung mitgeändert hat, ist eine Absichtserklärung.**
   Spiegelbild zu SWR-122 aus Sprint 10 (Prüfung ohne Leser); hier: Regel ohne Prüfung.
3. **⚠ Der Befund wurde beim Bauen schärfer, nicht milder.** Der erste Entwurf der Antwort
   behauptete „sonst wird der Startcheck rot". **Nachgemessen im Code: falsch** — die Zeile
   wurde gedruckt und **nie gezählt** (`befunde += 1` fehlte). Die Prüfung musste nichts
   blockieren; es genügte, dass „unterminiert 0" zu den Zahlen gehört, die jeder
   Sprintabschluss **berichtet**.
   > **Eine Kennzahl steuert, sobald sie berichtet wird — auch wenn sie nichts blockiert.**
   Eine ungeprüfte Behauptung über eigenen Code, in der Antwort, die eine ungeprüfte Zahl
   aufarbeitet. Korrigiert im Brief selbst, mit dem Originalsatz daneben.
4. **Die Zahl des Auftraggebers, an unserem Bestand nachgemessen.** Er schrieb „über 240
   Durchläufe". Abstand zwischen geplantem Sprint und Sprint der Frist (24 Sprints/Tag):
   **14 von 14** offenen Teamaufgaben betroffen, **+168** bis **+408** Sprints, **Median
   +240**. *Er hat geschätzt, was wir hätten messen können.* Alle 14 standen auf **grün** —
   die vier unbemerkten Verschiebungen von `pm/T-0039` liefen die ganze Zeit unter einer
   grünen Frist. **Eine Frist, die nicht reißen kann, terminiert nicht.**
5. **✅ `pm/T-0059` als erste Sacharbeit erledigt, genau wie Sprint 10 zugesagt hat**
   (**SWR-126**). Der Brief ist ein Verlauf. Die Zerlegungsregel ist **am Bestand gemessen,
   nicht geraten**: 41 Briefe tragen **52** `## Antwort`-Überschriften (alle mit ISO-Datum —
   und 52 > 41 heißt: **Briefe mit mehreren Teambeiträgen gibt es längst, von Hand**; der
   Wunsch beschreibt eine bestehende Praxis ohne Werkzeug) und **11** weitere
   `##`-Überschriften, die Abschnitte *innerhalb* einer Antwort sind. Ein naives „jede `##`
   ist ein Beitrag" hätte **11 Briefe falsch zerlegt**.
6. **⚠ `pm/T-0028` nach vier Verschiebungen zerlegt statt ein fünftes Mal geschoben.**
   Gemessen: `geplant_sprint` 7→8→9→10→11. **Derselbe Zählerstand, an dem Sprint 10 bei
   `pm/T-0039` die Regel abgeleitet hat** — und `pm/T-0028` stand in *derselben
   Plantabelle desselben Laufs* und wurde ein viertes Mal verschoben, mit dem Vermerk
   „Rest = Umfang (3 Flächen)". **Umfang ist nach D006 kein Verschiebungsgrund, sondern der
   Zerlegungsgrund.** Erster Teil gebaut: **SWR-127** (`pm/T-0062`).
7. **⚠ Und die Klammer von `pm/T-0039` trug denselben Fehler.** Sprint 10 schrieb die Regel
   *„wer zerlegt, zieht die Klammer auf den Termin des letzten Teils nach"* — und ließ
   `T-0039` auf Sprint 11 stehen, während sein letzter Teil (`T-0060`) auf 12 liegt.
   Korrigiert. **Fünfter Sprint in Folge, in dem eine Verifikation einen Fehler des
   eigenen Vorlaufs findet** — der Fehler ist damit keine Nachlässigkeit einer Session,
   sondern eine Eigenschaft des Arbeitsschritts „Regel aufschreiben und weiterarbeiten".
8. **⚠⚠ Der wichtigste Planbefund: B025 ist für die HMI kein Grund, sondern ein
   Ausschluss.** Fünf offene Aufgaben liegen auf der HMI-Fläche (`pm/T-0052`, `T-0054`,
   `T-0058`, `T-0060`, Rest von `T-0028`). Die Arbeit jedes Laufs entsteht aus den Briefen
   des Auftraggebers — und die treffen **zuerst das Backend**. Solange jeder Lauf Backend
   baut und B025 eine zweite Fläche verbietet, **bekommt die HMI nie einen Lauf**.
   **Beschluss (Klasse B): Sprint 12 ist ein HMI-Sprint.** Damit ist der Grund nicht
   fortschreibbar, sondern durch einen Plan ersetzt.
9. **`p12/T-0003` zerlegt** (T-0004/T-0005/T-0006), wie Sprint 10 für diesen Fall wörtlich
   angeordnet hatte (*„beim Anfassen zerlegen, nicht schieben"*) — drittes Mal in einem
   Lauf, dass eine eigene, aufgeschriebene Regel erst beim Nachmessen angewandt wurde.
10. **Drei Sachtickets geschlossen** (`platform/T-0012`, `pm/T-0059`, `pm/T-0062`) plus
    sechs Takt-Pflichten. **Sechs neue Tickets** (`pm/T-0061`, `pm/T-0062`, `pm/T-0063`,
    `p12/T-0004`, `T-0005`, `T-0006`).
11. **⚠ Fünf Alttests fielen — und alle fünf hatten recht.** Zwei durch SWR-125
    (`test_ticket_mit_frist_ist_kein_treffer` prüfte eine Einheit, die SWR-106 fünf Sprints
    vorher abgeschafft hatte; `test_decision_request_ist_kein_treffer` nannte im Docstring
    `frist`+`default` als Steuerung und legte den DR **ohne frist** an — er belegte eine
    Nachsicht und nannte sie eine Steuerung), drei weitere in `test_org_cockpit` und
    `test_org_kopfblock` aus demselben Grund. **In allen fünf Fällen wurde die
    PROVOKATION ersetzt, nie die Erwartung.** Dritter bis siebter Fall dieser Sorte in
    zwei Sprints.
12. **738 Tests grün** (+15 gegenüber der Zwischenmessung, +49 gegenüber Sprint 10),
    Matrix **127 SWRs / 0 Lücken**. **Kein Kalenderdatum mehr an einer Teamaufgabe im
    ganzen Bestand.**

## Sprint-Plan

*Sprint 11 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem
Sprint schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 12; ab Sprint 13 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

*⚠ **Ab Sprint 11 gibt es in der Fälligkeitsspalte keine Kalenderdaten mehr** (SWR-125,
Brief `pm/N-0041`). Ein Datum steht nur noch dort, wo ein **Mensch** wartet
(Entscheidungsvorlagen) — seine Antwortzeit läuft in Tagen, nicht in 60-Minuten-Läufen.
Der Preflight liest beides: `unterminiert` (kein Sprint) **und** `kalenderfristen` (Datum
an einer Teamaufgabe), beide zählen als Befund.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0012 | cm | dieser Sprint | **erledigt** | **Neu, aus Brief `pm/N-0041`.** **SWR-125**: `unterminiert` fragt nach `geplant_sprint`; ein Kalenderdatum an einer Teamaufgabe ist **selbst** ein Befund (`kalenderfristen`); die Abgrenzung steht genau **einmal** (`_ist_unterminiert`) und wird von Kachel **und** Org-Summe gelesen. 16 Tests, Gegenprobe: 7 rot gegen die alte Regel. |
| pm/T-0059 | dev | dieser Sprint | **erledigt** | **Erste Sacharbeit, wie zugesagt.** **SWR-126**: `beitraege()`, `sende(brief=…)`, Statusrücksetzung auf `offen` im **selben** Commit. `spalte_antwort` ist ab jetzt eine **Sicht** darauf, kein zweiter Parser (B033/B054). 18 Tests, Gegenprobe: 4 rot gegen ein naives `##`. |
| pm/T-0062 | chg | dieser Sprint | **erledigt** | **Neu, erster Teil von `T-0028`.** **SWR-127**: die seit Sprint 10 entschiedene Steckbrief-Feldliste **gilt** im Code; bei `sensibel`/`geheim` verlässt eine Auflage im Klartext die Funktion als **Rückgabewert** (Lehre von SWR-122). 15 Tests. |
| pm/T-0028 | chg | Sprint 12 | **zerlegt** | ⚠ **Viermal um eins verschoben** (7→8→9→10→11), Grund zuletzt „Umfang" — nach D006 der **Zerlegungs**grund. Zerlegt in `T-0062` (erledigt) + `T-0063`. Klammer trägt den Termin des letzten Teils. Offen bleibt darin nur das HMI-Formular. |
| pm/T-0039 | pl | Sprint 12 | **zerlegt** | ⚠ **Klammer von 11 auf 12 korrigiert** = Termin des letzten Teils (`T-0060`). Die Regel dafür hat Sprint 10 aufgeschrieben und an genau diesem Ticket nicht angewandt. |
| pm/T-0063 | chg | Sprint 12 | offen | **Neu, aus `T-0028`.** Charter-Entwurf + Gründungs-DR; die SWR-127-Auflage muss im DR-Text **im Klartext** stehen. `blocked_by: [T-0062]` erfüllt. |
| pm/T-0061 | cm | Sprint 12 | offen | **Neu, Nebenbefund aus `platform/T-0012`.** `sprint_widerspruch` hat nach der Umstellung **keinen möglichen Fall** mehr (0 offene Tickets mit beiden Feldern). Klasse C. Vor der Entscheidung **messen**, ob die Prüfung je angeschlagen hat. |
| pm/T-0060 | dev | Sprint 12 | offen | ⚠ **Entblockt** — `blocked_by: [T-0059]` ist aufgelöst. Reine Darstellungsarbeit. HMI-Sprint. |
| pm/T-0052 | pl | Sprint 12 | offen | HMI-Abschnitt „Für dich: Handlungen". **2. Verschiebung.** Grund: drei Backend-Bauflächen in diesem Lauf, HMI wäre die vierte (B025) — **und genau dieser Grund ist als Ausschluss erkannt.** HMI-Sprint 12. |
| pm/T-0054 | chg | Sprint 12 | offen | Knopf zum Priorisieren (Brief `pm/N-0038`). **2. Verschiebung**, gleicher Grund, gleicher Beschluss. |
| pm/T-0058 | dev | Sprint 12 | offen | Anzeige ohne Reload. **1. Verschiebung.** HMI-Sprint 12. |
| projects/p11/T-0008 | dev | Sprint 12 | offen | Backend-Endpunkt + Widget-Konfiguration. **2. Verschiebung** — der Lauf lag auf Brief und Prüfstrecke. |
| projects/p11/T-0009 | dev | Sprint 12 | offen | Deep-Links + Mail-Widget hinter dem PIN-Lesegate. **1. Verschiebung.** |
| projects/p11/T-0003 | pl | Sprint 12 | offen | **Klammer** über `T-0007`/`T-0008`/`T-0009`, auf den Termin des letzten Teils nachgezogen. **Keine Verschiebung** — sie enthält selbst nichts. ⚠ Verfeinerung dieses Laufs: die Zählung „viermal verschoben" darf Klammern **nicht** mitzählen. |
| projects/p12/T-0004 | pl | Sprint 12 | offen | **Neu, erster Teil von `T-0003`.** Teststrecken-Entscheidung (R5) im ADR — der Teil, der alles danach freigibt. ⚠ 334 Python-Tests, **null** JS-Tests; „Tests" im Abnahmekriterium ersetzt keinen Nachweis (B027/B038). Kosten/neues Werkzeug → **Klasse A**, DR. |
| projects/p12/T-0005 | pl | Sprint 13 | offen | **Neu.** ADR-Delta + Vollständigkeitsnachweis, `blocked_by: [T-0004]`. |
| projects/p12/T-0006 | pl | Sprint 14 | offen | **Neu.** Umstellung, Tests, G4, `blocked_by: [T-0005]`. |
| projects/p12/T-0003 | pl | Sprint 14 | **zerlegt** | ⚠ **Dreimal verschoben** (8→9→10→11); Sprint 10 hatte *„beim Anfassen zerlegen"* wörtlich angeordnet. Zerlegt entlang der Reihenfolge, die das Ticket selbst „Teil des Auftrags" nennt. Klammer = Termin des letzten Teils. |
| promt-team/T-0001 | dev | Sprint 12 | offen | Telemetrie je KI-Rolle. **2. Verschiebung** — Grund: dieser Lauf war vom Brief bestimmt. **Verfallsdatum: gilt nur für Sprint 11.** |
| promt-team/T-0002 | test | Sprint 12 | offen | Goldset je KI-Rolle. **1. Verschiebung**, gleicher Grund. |
| promt-team/T-0003 | dev | Sprint 13 | blocked | ⚠ **Feld von 12 auf 13**: stand auf **demselben** Sprint wie seine beiden Blocker und behauptete damit, beides gehe in einem Lauf — während das Ticket selbst sagt *„ohne Baseline kein Optimierungslauf"*. Stiller Widerspruch; keine Prüfung hält `geplant_sprint` gegen den Sprint des Blockers. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — **drei** Briefe eingegangen (`pm/N-0041` beim Start, `promt-team/N-0001` und `team-dashboard/N-0002` **während** des Laufs), alle drei beantwortet, keiner offen. ⚠ Die beiden späten kannte der Startcheck nicht: **ein Briefkasten-Stand vom Laufbeginn ist am Laufende keine Aussage mehr.** |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight, Tests, Matrix. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Widget-Vertrag — Payload um `kalenderfristen` erweitert (SWR-125), Vertrag entsprechend gelesen. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033) — und genau deshalb nehmen `plan_drift`,
`status_drift`, `sprint_vergangen` **und jetzt `unterminiert`** sie aus.

**Rollenzuweisungen in diesem Sprint (D006):** `platform/T-0012` liegt bei `cm` (Werkzeug-
fläche der Prüfstrecke, dieselbe Begründung wie `platform/T-0011` in Sprint 10).
`pm/T-0062` und `pm/T-0063` bleiben bei `chg`, weil beide aus einem Betriebs-CR stammen und
die Feldliste eine Änderungsentscheidung ist, kein Bauweg. `pm/T-0061` ist an `cm`
gegangen: es geht um eine **Prüfung**, nicht um das Statusmodell — Gegenstück zur
Zuweisung von `pm/T-0053` an `pl` in Sprint 10.

## Sprint-Abschluss (Sprint 11, 2026-08-17)

**Geplant beim Start:** 20 nicht geschlossene Aufgaben (14 Sachtickets + 6 Takt-Pflichten),
dazu **ein offener Brief** (`pm/N-0041`), der Vorrang hatte — und **zwei weitere, die
während des Laufs eintrafen** (`promt-team/N-0001`, `team-dashboard/N-0002`) und noch in
ihm beantwortet wurden. Im Lauf kamen **sechs**
Tickets dazu: `platform/T-0012` aus dem Brief, `pm/T-0061` als Nebenbefund und vier aus
Zerlegungen (`pm/T-0062`, `pm/T-0063`, `p12/T-0004`, `T-0005`, `T-0006` — fünf, davon
`T-0062` im selben Lauf geschlossen).

**Geschlossen:** `platform/T-0012`, `pm/T-0059`, `pm/T-0062` und die sechs Takt-Pflichten —
**neun Stück**. Alle drei Sachtickets über den legalen Weg
(`open → in_progress → in_review → done`) mit je drei Commits.

**Verschoben, mit Grund und Verfallsdatum:** neun Sachtickets nach Sprint 12/13, zwei
weitere als Klammer nachgezogen (keine Verschiebung). **Der Grund ist bei allen derselbe
und wurde deshalb nicht wiederholt, sondern gemessen** — mit dem Beschluss, Sprint 12 zum
HMI-Sprint zu machen, statt eine sechste Runde B025 zu schreiben.

**Verifikation (nach allen Änderungen des Laufs gemessen, nicht davor):**
Preflight **STARTKLAR**, 738 Tests grün, Matrix **127 SWRs / 0 Lücken**, unterminiert **0**,
**Kalenderfristen 0**, Plan-Drift 0, überfällig 0, Statusdrift 0, Statusübergänge seit
Stichtag 0, Altbestand 52 (unverändert). Briefkasten: **drei Briefe eingegangen, drei
beantwortet, kein offener**.
