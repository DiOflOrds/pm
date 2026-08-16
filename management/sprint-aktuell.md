# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Geplant wird ab jetzt auf Sprints, nicht auf Kalenderdaten** (Auftraggeber, 2026-08-17).
   Ein Sprint = ein Routine-Lauf; der Takt ist **stündlich**, also rund **24 Sprints am Tag**.
2. **Wir sind in Sprint 1.** Der Zähler beginnt mit der Umstellung; die rund dreißig Läufe des
   16.08. bekommen **keine** Nummern — sie ließen sich nur schätzen, und Commits sind keine
   Läufe (B056).
3. **Alle 17 offenen Aufgaben sind auf Sprints geplant** — 6 in diesem, 4 in Sprint 2, 1 in
   Sprint 3, der Rest als geordnete Warteschlange bis Sprint 8.
4. **Nichts wartet mehr auf dich.** Die vier Host-Aufgaben von gestern sind entweder geschlossen
   (`pm/T-0034`) oder laufen jetzt über die CI-Statusprüfung aus SWR-105.
5. **`frist` und `geplant_sprint` laufen parallel** — Zusage nach außen und Planung des Teams.
   Widersprüche zwischen beiden meldet die Kachel; aktuell: **keiner**.

## Sprint-Plan

*Sprint 1 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (zerlegt) oder blockiert.
**Fest geplant** sind Sprint 1–3; ab Sprint 4 ist die Nummer eine **Reihenfolge**, keine Zusage.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0041 | pl | dieser Sprint | **erledigt** | Umstellung auf Sprintplanung: Zähler `sprints.jsonl`, Feld `geplant_sprint`, Widerspruchsprüfung, Kachel (SWR-106). |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — 48 Briefe, kein offener; 5 in diesem Lauf beantwortet. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons Learned sofort verankert (D005). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Werkzeugpflege — Preflight STARTKLAR, Tests grün, Matrix ohne Lücke. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest. **Nicht mehr blockiert** — IMAP und Ollama laufen, belegt durch den Autopilot-Digest vom 16.08. |
| platform/T-0003 | cm | Sprint 2 | in_review | Stichprobe auswerten, sobald der erste `CI-STATUS.md` am Host entstanden ist. |
| pm/T-0013 | prob | Sprint 2 | in_review | Kriterium 2 (grüner Actions-Lauf) kommt ab jetzt aus `CI-STATUS.md` statt aus einem Blick. |
| pm/T-0010 | prob | Sprint 2 | in_review | Dieselbe Quelle (board-check-Flake). |
| pm/T-0026 | cm | Sprint 2 | in_review | Dieselbe Quelle (CI-/Matrix-Gate). |
| team-dashboard/T-0001 | pl | Sprint 3 | offen | Widget-Vertrag; fachliche Sperre für `projects/p11/T-0003`. Vorgezogen auf Wunsch (Brief p11/N-0001). |
| pm/T-0036 | pl | Sprint 4 | offen | Ändert das `BOARD.md`-Format und gehört mit `pm/T-0038` in **einen** Sprint — zwei getrennte Formatänderungen haben am 16.08. alle board-checks rot gemacht (B053). |
| pm/T-0038 | pl | Sprint 4 | offen | Gebündelt mit `pm/T-0036`, gleicher Grund. |
| projects/p11/T-0003 | pl | Sprint 5 | blockiert | Wartet auf `team-dashboard/T-0001` (Sprint 3). Repo-übergreifendes `blocked_by` kann das Board nicht ausdrücken (B047) — die Sprintfolge trägt die Aussage. |
| pm/T-0039 | pl | Sprint 6 | offen | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — mit anderem zusammen wäre es B025. |
| pm/T-0028 | chg | Sprint 7 | offen | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); das HMI darf sie nur **vorbereiten**. |
| projects/p12/T-0003 | pl | Sprint 8 | offen | Sprint 1 des Projekts (Renderer zusammenführen) — Umfang mehrerer Läufe, nicht eines. |

**Warum fünf Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001` und `team-mail/T-0001` sind **Takt-Dauerläufer** (`takt: je-session`): sie laufen
in **jedem** Sprint. Eine Nummer daneben wäre eine zweite Aussage über dieselbe Sache und würde bei
jedem Lauf veralten — genau die Doppelung, die diese Umstellung beseitigen soll (B033).

**Rollenzuweisung in diesem Sprint:** keine Umhängung.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (Sprint 1, 2026-08-17)

**Geplant:** 17 Aufgaben, davon 6 in diesem Sprint. **Geschlossen:** `pm/T-0041` sowie die fünf
Takt-Pflichten. **Nicht geschlossen:** nichts, was für Sprint 1 geplant war.

Vorher, im selben Lauf: `pm/T-0034` geschlossen (Beleg im Repo statt Zusage), fünf Briefe
beantwortet, `platform/T-0003` / SWR-105 gebaut (CI-Status ohne Zugangsdaten).

## Wie geplant wird — die Regeln dieser Umstellung

**Ein Sprint ist ein Routine-Lauf.** Der Zähler steht in `pm/management/sprints.jsonl`, eine Zeile
je Sprint, nur angehängt. Er wird **nicht** aus der Git-Historie abgeleitet: eine Session schreibt
mehrfach, Commits sind keine Läufe (**B056**, belegt mit 42 Commits auf rund 30 Läufe). `beginne()`
ist über eine Laufkennung **idempotent** — derselbe Lauf zweimal gestartet erhöht nichts.

**Der Horizont ist ehrlich beschriftet.** Sprint 1–3 sind fest; ab Sprint 4 ist die Nummer eine
Reihenfolge. Bei 24 Sprints am Tag wäre „Sprint 150" eine Scheingenauigkeit, die bei jedem Lauf neu
geschrieben werden müsste — die Zahl steht trotzdem da, aber sie heißt *Warteschlange* und nicht
*Termin*.

**`frist` bleibt und beantwortet eine andere Frage.** Der Auftraggeber hat beide Felder gewählt:

| Feld | Frage | Wer liest es |
|---|---|---|
| `frist` | *Bis wann ist es jemandem außerhalb des Teams zugesagt?* | Eskalation B044/SWR-091, der Mensch |
| `geplant_sprint` | *In welchem Lauf fasst das Team es an?* | Sprintplanung, das Team |

Zwei Fakten dürfen nebeneinander stehen — zwei Angaben, die sich widersprechen, nicht. Deshalb
prüft `board.sprint_widerspruch` jedes Ticket, dessen geplanter Sprint **selbst bei
ununterbrochenem Takt** nach seiner Frist läge, und die Kachel zeigt die Treffer **über** der
Tabelle. Das ist die Gegenmaßnahme zu der Schwäche, die das Team bei dieser Wahl benannt hat
(B033): sie wird geprüft statt vorausgesetzt.

## Was sich gegenüber gestern geändert hat

* **Aus fünf „wartet-auf-Mensch" sind null geworden.** `pm/T-0034` ist geschlossen (die Digests im
  Repo belegen IMAP und Ollama), `team-mail/T-0001` ist damit entsperrt, und die drei
  CI-Tickets bekommen ihre Antwort ab jetzt aus `CI-STATUS.md` (SWR-105) statt aus einem Blick auf
  eine Webseite.
* **Aus Kalenderdaten sind Sprintnummern geworden.** Der Abstand zur Arbeitseinheit ist damit
  ablesbar: „Sprint 4" heißt drei Läufe, nicht „irgendwann nächste Woche".
