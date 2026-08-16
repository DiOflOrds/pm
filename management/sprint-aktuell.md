# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 2** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **Der erste Hostlauf von SWR-105 hat drei rote Repos gefunden** — `p3`, `p5`, `platform`. Das
   ist der erste Ertrag der CI-Statusprüfung und der Grund, warum dieser Sprint anders verlaufen
   ist als geplant.
3. **Vier Tickets geschlossen** (`platform/T-0003`, `pm/T-0010`, `pm/T-0013`, `pm/T-0026`) — alle
   mit dem Fremdnachweis, auf den sie seit dem 16.08. warteten.
4. **Drei Tickets neu**, weil der Lauf zwei Befunde brachte, die vorher niemand kannte:
   `platform/T-0004` (in diesem Sprint gebaut), `pm/T-0042`, `pm/T-0043`.
5. **Eine plausible Erklärung wurde widerlegt statt übernommen** — siehe `pm/T-0043`. Ohne die
   Gegenprobe wären zwei Tickets mit einer falschen Begründung geschlossen worden.
6. **Die Gegenprüfung fand fünf Mängel bei grüner Suite** (B063), darunter einen, der den ganzen
   Bericht verschluckt hätte. Alle behoben, jeder mit Test. **463 Tests grün**, Matrix
   **107 SWRs / 0 Lücken**, Preflight STARTKLAR, kein offener Brief.

## Sprint-Plan

*Sprint 2 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (zerlegt) oder blockiert.
**Fest geplant** sind Sprint 3–4; ab Sprint 5 ist die Nummer eine **Reihenfolge**, keine Zusage.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0003 | cm | dieser Sprint | **erledigt** | Erster Hostlauf liegt vor: 15 Abfragen, alle fünf DoD-Punkte belegt, Netzweg nachgewiesen. Die Stichprobe wurde **unabhängig rekonstruiert** statt angesehen. |
| pm/T-0010 | prob | dieser Sprint | **erledigt** | board-check grün für 8 Repos über die Mitternachtsgrenze — der `-I "^Stand:"`-Fix trägt. |
| pm/T-0013 | prob | dieser Sprint | **erledigt** | Kriterium 2 erfüllt. Die Reihenfolgeregel hat eine Rückseite; sie läuft als `pm/T-0042`. |
| pm/T-0026 | cm | dieser Sprint | **erledigt** | `projects`-Checkout als Ursache **ausgeschlossen** (zwei Durchläufe, 104/1 gegen 105/0). |
| platform/T-0004 | cm | dieser Sprint | **gebaut, in_review** | SWR-107: ein rotes Ergebnis nennt Job und Schritt. 19 Tests, davon 8 aus der Gegenprüfung (B063). Netzweg offen bis zum nächsten Hostlauf → Sprint 3, ohne Handlung. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, **kein offener**. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert — L-2026-08-17b (B061), L-2026-08-17c (B062), L-2026-08-17d (B063). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight STARTKLAR, 463 Tests grün, Matrix 107/0. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest. |
| team-dashboard/T-0001 | pl | Sprint 3 | offen | Widget-Vertrag; fachliche Sperre für `projects/p11/T-0003`. |
| pm/T-0042 | prob | Sprint 3 | offen | Push-Reihenfolge-Zwickmühle (B061). Vier Wege stehen im Ticket. **Nicht in diesem Sprint**, weil die Behebung `abschluss.cmd` oder ein Gate ändert und die Diagnose gerade erst entstanden ist (L-2026-08-17b Regel 3). |
| pm/T-0043 | prob | Sprint 3 | offen | `p3`/`p5` board-check rot seit dem 16.08. Die naheliegende Ursache ist **widerlegt**; der fehlende Schritt kommt aus SWR-107 beim nächsten Hostlauf. Kein Raten. |
| pm/T-0036 | pl | Sprint 4 | offen | Ändert das `BOARD.md`-Format, gebündelt mit `pm/T-0038` (B053). |
| pm/T-0038 | pl | Sprint 4 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| projects/p11/T-0003 | pl | Sprint 5 | blockiert | Wartet auf `team-dashboard/T-0001` (Sprint 3). Repo-übergreifendes `blocked_by` kann das Board nicht ausdrücken (B047) — die Sprintfolge trägt die Aussage. |
| pm/T-0039 | pl | Sprint 6 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 7 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 8 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe, nicht eines. |

**Warum fünf Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001` und `team-mail/T-0001` sind Takt-Dauerläufer (`takt: je-session`): sie laufen in
**jedem** Sprint. Eine Nummer daneben wäre eine zweite Aussage über dieselbe Sache (B033).

**Rollenzuweisung in diesem Sprint:** `platform/T-0004` liegt bei `cm` (dieselbe Fläche wie
SWR-105), die beiden neuen Befunde bei `prob` — Problemanalyse ist nicht Werkzeugbau.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (Sprint 2, 2026-08-17)

**Geplant:** 16 offene Aufgaben, davon 9 in diesem Sprint (4 Sachtickets + 5 Takt-Pflichten).
**Geschlossen:** `platform/T-0003`, `pm/T-0010`, `pm/T-0013`, `pm/T-0026` und die fünf
Takt-Pflichten. **Zusätzlich gebaut:** `platform/T-0004` / SWR-107, entstanden **innerhalb** dieses
Sprints aus dem Befund des Hostlaufs.

**Nicht geschlossen, mit Grund:** `platform/T-0004` bleibt `in_review` — der Netzweg der
Jobs-Abfrage ist nicht belegt, die Sandbox hat keinen GitHub-Zugang (in diesem Sprint erneut
bestätigt). Er wird beim nächsten `abschluss.cmd` von selbst nachgewiesen; **keine Handlung nötig**,
Sprint 3.

**Neu und bewusst nicht in diesem Sprint:** `pm/T-0042` und `pm/T-0043`, beide Sprint 3. Die
Gründe stehen in der Tabelle und ausführlich in den Tickets — bei `T-0042` die Trennung von
Diagnose und Behebung, bei `T-0043` das Fehlen des Schritts, den SWR-107 gerade erst holbar gemacht
hat. Beides ist kein Verschieben von Arbeit, sondern das Abwarten eines Belegs, der ohne Zutun
kommt.

## Was dieser Sprint über die Planung gelernt hat

Der Plan für Sprint 2 stand seit gestern: „CI-Status auswerten, sobald `CI-STATUS.md` existiert".
Er ist erfüllt worden — und hat unterwegs **drei neue Tickets** erzeugt, eines davon noch im selben
Lauf gebaut. Das ist kein Planungsfehler. Ein Sprint, dessen einzige Aufgabe das Auswerten eines
Berichts ist, kann nicht wissen, was der Bericht sagen wird; die Planung hat richtig gehandelt,
indem sie den Auswertungsschritt terminiert hat, statt sein Ergebnis vorwegzunehmen.

**Was auffällt und für Sprint 3 vorgemerkt ist:** `team-dashboard/T-0001` trägt **sowohl**
`takt: je-session` **als auch** `geplant_sprint: 3`. Nach der eigenen Regel dieser Umstellung ist
das eine Doppelaussage (B033). Es ist kein Widerspruch im Sinne der Prüfung
(`board.sprint_widerspruch` meldet nichts, weil die Frist nicht verletzt wird), aber es ist die
Sorte Doppelung, gegen die SWR-106 geschrieben wurde. Aufgenommen in die Agenda, nicht als eigenes
Ticket — es ist eine Feldkorrektur, keine Aufgabe.

## Zahlen dieses Sprints

| | Sprint 1 | Sprint 2 |
|---|---|---|
| Tickets gesamt | 243 | 246 |
| offen / in_review | 12 / 4 | 14 / 1 |
| nicht geschlossen | 16 | 15 |
| Tests | 444 | **463** |
| Matrix | 106 SWRs / 0 Lücken | **107 SWRs / 0 Lücken** |
| offene Briefe | 0 | 0 |
| unterminiert / überfällig | 0 / 0 | 0 / 0 |
