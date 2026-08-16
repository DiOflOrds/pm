# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **17 offene Aufgaben in 6 Repos, alle terminiert** — 6 in diesem Sprint, 5 warten auf eine
   Handlung am Host, 6 tragen ein späteres Datum mit Grund im Ticket.
2. **Sprintinhalt ist `pm/T-0032` Teil 2 (Bau)** — die früheste Frist der Organisation (19.08.)
   und das einzige offene Ticket, das nach der Zerlegung des Vorlaufs **keine Denkarbeit mehr
   trägt**. Es ohne Not liegen zu lassen, wäre der vierte Aufschub gewesen.
3. **Kein Ticket ist unterminiert, keins überfällig** — Stand beim Planen; `pm/T-0034` (17.08.)
   ist der früheste Termin und wartet auf den Host.
4. **Keine Rollenumhängung.** Die fünf Host-Aufgaben tragen fachlich korrekte Rollen; dass sie
   beim **Menschen** liegen, sagt bis `pm/T-0038` allein die Spalte *Status*.

## Sprint-Plan

*Sprint = dieser Lauf (2026-08-16 23:06–…). Default nach pm/D006: in diesem Sprint schließen.
Verschieben nur mit Grund — Mensch nötig, zu groß (zerlegt) oder blockiert.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0032 | pl | dieser Sprint | **erledigt** | Teil 2 gebaut: `takt: taeglich@HH:MM` / `woechentlich@Mo-HH:MM`, Feld `zuletzt_erledigt`, **eine** Fälligkeitsfunktion durch dieselbe `board.frist_ampel` (SWR-104). Vorgezogen vom 19.08. — nach der Zerlegung des Vorlaufs reine Bauarbeit. |
| pm/T-0001 | pl | dieser Sprint | erfüllt | Takt je Session: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | dieser Sprint | erfüllt | Takt je Session: Briefkasten qualifiziert — 43 Briefe, kein offener (zweimal geprüft, B036). |
| pm/T-0003 | coach | dieser Sprint | erfüllt | Takt je Sprint: Lessons Learned dieses Laufs sofort verankert (D005). |
| platform/T-0001 | cm | dieser Sprint | erfüllt | Takt: Werkzeugpflege — Preflight STARTKLAR, Tests grün, Matrix ohne Lücke. |
| pm/T-0034 | prob | 2026-08-17 | wartet-auf-Mensch | Ollama/`ASPICE-MailAutopilot` nur am Host prüfbar; in dieser Sandbox kein IMAP und kein Ollama (Guardrail 2). Ab 17.08. greift B044. |
| pm/T-0013 | prob | 2026-08-18 | wartet-auf-Mensch | Kriterium 1 lokal belegt (B049); Kriterium 2 braucht die GitHub-Actions-Seite. |
| pm/T-0010 | prob | 2026-08-18 | wartet-auf-Mensch | Derselbe Blick auf dieselbe Seite (board-check-Flake). |
| pm/T-0026 | cm | 2026-08-18 | wartet-auf-Mensch | Derselbe Blick auf dieselbe Seite (CI-/Matrix-Gate). |
| team-mail/T-0001 | dev | wartet-auf-Mensch | blockiert | Fachlich blockiert durch `pm/T-0034`: der Takt beginnt mit der IMAP-Einrichtung am Host. |
| pm/T-0036 | pl | 2026-08-23 | terminiert | Ändert das `BOARD.md`-Format und gehört mit `pm/T-0038` in **eine** Session — zwei getrennte Formatänderungen haben am 16.08. sämtliche board-checks rot gemacht (`pm/T-0013`). |
| pm/T-0038 | pl | 2026-08-23 | terminiert | Gebündelt mit `pm/T-0036`, gleicher Grund. Beide zusammen sind der nächste Sprint-Inhalt. |
| pm/T-0039 | pl | 2026-08-23 | terminiert | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — neben `T-0032` in einem Lauf wäre es B025. |
| pm/T-0028 | chg | 2026-08-23 | terminiert | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); Entwurf und Vorlage gehören in einen eigenen Lauf. |
| team-dashboard/T-0001 | pl | 2026-08-23 | terminiert | Widget-Vertrag; ist die fachliche Sperre für `projects/p11/T-0003`. |
| projects/p11/T-0003 | pl | 2026-08-30 | blockiert | Wartet auf `team-dashboard/T-0001`. Repo-übergreifendes `blocked_by` kann das Board nicht ausdrücken (B047) — der Termin trägt die Aussage, der Grund steht im Ticket. |
| projects/p12/T-0003 | pl | 2026-08-30 | terminiert | Sprint 1 (Renderer zusammenführen); Umfang eines eigenen Sprints, nicht einer Routine-Halbstunde. |

**Rollenzuweisung in diesem Sprint:** keine Umhängung. Alle fünf Host-Aufgaben tragen fachlich
korrekte Rollen (`prob`/`cm`/`dev`); dass sie tatsächlich beim **Menschen** liegen, ist genau die
Lücke, die `pm/T-0038` schließt (Feld `verantwortlich`) — bis dahin sagt es die Spalte *Status*
hier mit `wartet-auf-Mensch`.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (2026-08-16, 23:06-Lauf)

**Geplant:** 17 Aufgaben, davon 6 für diesen Sprint. **Geschlossen:** `pm/T-0032` (`done`, nach
`in_review` mit Reviewer `qm`) sowie die vier Takt-Pflichten `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`. **Nicht geschlossen:** nichts, was für diesen Sprint geplant war.

Der Sprint hat der Organisation **eine** Takt-Syntax mit Uhrzeit, **ein** neues Ticketfeld
(`zuletzt_erledigt`), **einen** neuen SWR (104, 0 Lücken), **22** neue Tests (402, vorher 380) und
**zwei** Befunde gebracht, die beide in `process/knowledge/cm/lessons.md` stehen: **B058** — die
Ampel war eine **Tagesregel** und musste zur **Momentregel** werden, ohne ihre Aussage für reine
Datumsfristen zu verändern; und **B059** — eine **unabhängige Gegenprüfung** fand bei **grüner
Suite** zwei Nachbarn, die denselben Wert weiter mit der alten Auflösung lasen (eine `frist` mit
Uhrzeit hätte die ganze Cockpit-Seite mitgerissen, der Ticket-Editor hätte den Takt beim Speichern
gelöscht). Beide behoben, beide mit Regressionstest.

**Was das für den nächsten Sprint heißt:** die Gegenprüfung ist ab jetzt **letzter Schritt** einer
Änderung an geteilten Regeln, nicht Zugabe (L-2026-08-16m).

## Wie dieser Plan entstanden ist

Gesichtet wurden **alle** Tickets **aller** entdeckten Repos (16 Git-Repos plus die drei Projekte
in `projects/`): **241 Tickets**, davon 220 `done`, 4 `rejected`, **14 `open`, 3 `in_review`**.
Die 17 nicht geschlossenen stehen oben vollständig — keine Auswahl, keine Kürzung.

**Warum `pm/T-0032` und nicht ein Ticket vom 23.08.** Die Vorsession hat `T-0032` zerlegt, statt
es zum vierten Mal zu verschieben, und schriftlich festgehalten: *„Ab hier trägt das Ticket keine
Denkarbeit mehr, sondern Bauarbeit."* Damit war die Auswahl nicht mehr frei — ein Ticket mit der
frühesten Frist, ohne offene Vorfrage und mit fertiger Abgrenzung noch einmal liegen zu lassen,
hätte genau das Muster fortgesetzt, gegen das die Zerlegung geschrieben wurde (B043/B049). Die
`23.08.`-Tickets ändern dagegen alle das `BOARD.md`-Format oder berühren Klasse A und gehören
gebündelt in einen eigenen Lauf (B053/B025).

## Nicht in diesem Sprint — und warum nicht

* **`pm/T-0036` + `pm/T-0038` (23.08.)** — beide fügen dem generierten `BOARD.md` eine Spalte
  bzw. Zeile hinzu. Zwei getrennte Formatänderungen am Board haben am 16.08. früh alle
  board-check-Workflows rot gemacht; sie gehören in **eine** Session (B053).
* **`pm/T-0039` (23.08.)** — Briefverlauf: Dateiformat, Schreibpfad, Statuslogik, Preflight-Zahl
  und HMI gleichzeitig. Neben `T-0032` in einem Lauf wäre es die zweite große Fläche (B025).
* **`pm/T-0028` (23.08.)** — Team-Gründung ist Klasse A (Playbook Kap. 16). Das HMI darf sie
  **vorbereiten**, entscheiden darf sie nur der Mensch; der Entwurf braucht einen eigenen Lauf.
* **`team-dashboard/T-0001` (23.08.)** — Widget-Vertrag, Sperre für P11. Ein Vertrag, der in einer
  Restviertelstunde entsteht, ist der Grund für den nächsten Vertrag.
* **`projects/p11/T-0003` (30.08.)** — fachlich blockiert; `blocked_by` über Repo-Grenzen kennt das
  Board nicht (B047).
* **`projects/p12/T-0003` (30.08.)** — voller Sprint 1 mit ADR, Teststrecke und G4.

## Was am Host hängt (fünf Aufgaben, zwei Handgriffe)

`pm/T-0034` (17.08.) ist der eine: läuft Ollama, ist `ASPICE-MailAutopilot` eingerichtet? Daran
hängt `team-mail/T-0001` — der Digest-Takt beginnt erst mit IMAP. `pm/T-0010`, `pm/T-0013` und
`pm/T-0026` (alle 18.08.) sind der andere: **ein** Blick auf die GitHub-Actions-Seite, die der
Push-Wächter in Schritt [5/5] ohnehin öffnet. Ein grüner Lauf schließt alle drei.
