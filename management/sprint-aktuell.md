# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **18 offene Aufgaben in 6 Repos, alle terminiert** — 6 in diesem Sprint, 5 warten auf eine
   Handlung am Host, 11 tragen ein Datum mit Grund im Ticket.
2. **`pm/T-0016` ist erledigt** — und war das einzige unterminierte Ticket der Organisation, in
   keiner Agendaliste. Ausgerechnet der CR, der diese Sicht sichtbar machen soll.
3. **Diese Tabelle steht ab jetzt in Mission Control**, Cockpit, direkt unter „Letzte Session" —
   samt Meldung, welche offenen Tickets in **keiner** Planzeile stehen.
4. **`pm/T-0032` ist zerlegt statt zum vierten Mal verschoben**: die Abgrenzung der drei
   Taktlogiken ist geschrieben, der Bau bleibt der 19.08.
5. **Was am Host hängt, hängt an zwei Handgriffen:** `pm/T-0034` (17.08.) und ein Blick auf die
   GitHub-Actions-Seite, der die drei `18.08.`-Tickets gemeinsam schließt.

## Sprint-Plan

*Sprint = dieser Lauf (2026-08-16 22:19–23:0x). Default nach pm/D006: in diesem Sprint schließen.
Verschieben nur mit Grund — Mensch nötig, zu groß (zerlegt) oder blockiert.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0016 | chg | dieser Sprint | **erledigt** | Workflow-Sicht im HMI gebaut (SWR-103, `GET /api/sprint`, Kachel „Sprint aktuell"). War das einzige unterminierte Ticket der Organisation. |
| pm/T-0032 | pl | dieser Sprint | **Teil 1 erledigt** | Abgrenzung der drei Taktlogiken schriftlich geklärt. Teil 2 (Bau) bleibt 19.08. — jetzt ohne offene Vorfrage. |
| pm/T-0001 | pl | dieser Sprint | erfüllt | Takt je Session: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | dieser Sprint | erfüllt | Takt je Session: Briefkasten qualifiziert — 43 Briefe, kein offener (zweimal geprüft, B036). |
| pm/T-0003 | coach | dieser Sprint | erfüllt | Takt je Sprint: Lessons Learned dieses Laufs sofort verankert (D005). |
| platform/T-0001 | cm | dieser Sprint | erfüllt | Takt: Werkzeugpflege — Preflight STARTKLAR, 380 Tests grün, Matrix 103/0. |
| pm/T-0034 | prob | 2026-08-17 | wartet-auf-Mensch | Ollama/`ASPICE-MailAutopilot` nur am Host prüfbar; in dieser Sandbox kein IMAP und kein Ollama (Guardrail 2). Ab 17.08. greift B044. |
| pm/T-0013 | prob | 2026-08-18 | wartet-auf-Mensch | Kriterium 1 lokal belegt (B049); Kriterium 2 braucht die GitHub-Actions-Seite. |
| pm/T-0010 | prob | 2026-08-18 | wartet-auf-Mensch | Derselbe Blick auf dieselbe Seite (board-check-Flake). |
| pm/T-0026 | cm | 2026-08-18 | wartet-auf-Mensch | Derselbe Blick auf dieselbe Seite (CI-/Matrix-Gate). |
| team-mail/T-0001 | dev | wartet-auf-Mensch | blockiert | Fachlich blockiert durch `pm/T-0034`: der Takt beginnt mit der IMAP-Einrichtung am Host. |
| pm/T-0036 | pl | 2026-08-23 | terminiert | Ändert das `BOARD.md`-Format und gehört mit `pm/T-0038` in **eine** Session — zwei getrennte Formatänderungen haben am 16.08. sämtliche board-checks rot gemacht (`pm/T-0013`). |
| pm/T-0038 | pl | 2026-08-23 | terminiert | Gebündelt mit `pm/T-0036`, gleicher Grund. Beide zusammen sind der nächste Sprint-Inhalt. |
| pm/T-0039 | pl | 2026-08-23 | terminiert | Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik, HMI) — neben `T-0016` in einem Lauf wäre es B025. |
| pm/T-0028 | chg | 2026-08-23 | terminiert | Team-Gründung im HMI berührt Klasse A (Playbook Kap. 16); Entwurf und Vorlage gehören in einen eigenen Lauf. |
| team-dashboard/T-0001 | pl | 2026-08-23 | terminiert | Widget-Vertrag; ist die fachliche Sperre für `projects/p11/T-0003`. |
| projects/p11/T-0003 | pl | 2026-08-30 | blockiert | Wartet auf `team-dashboard/T-0001`. Repo-übergreifendes `blocked_by` kann das Board nicht ausdrücken (B047) — der Termin trägt die Aussage, der Grund steht im Ticket. |
| projects/p12/T-0003 | pl | 2026-08-30 | terminiert | Sprint 1 (Renderer zusammenführen); Umfang eines eigenen Sprints, nicht einer Routine-Halbstunde. |

**Rollenzuweisung in diesem Sprint:** keine Umhängung. Alle vier Host-Tickets tragen fachlich
korrekte Rollen (`prob`/`cm`); dass sie tatsächlich beim **Menschen** liegen, ist genau die Lücke,
die `pm/T-0038` schließt (Feld `verantwortlich`) — bis dahin sagt es die Spalte *Status* hier
mit `wartet-auf-Mensch`.

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (2026-08-16)

**Geplant:** 18 Aufgaben, davon 6 für diesen Sprint. **Geschlossen:** `pm/T-0016` (`done`) sowie
die vier Takt-Pflichten `pm/T-0001`, `pm/T-0002`, `pm/T-0003`, `platform/T-0001`.
**Teilweise:** `pm/T-0032` — Teil 1 (Abgrenzung) erledigt, Teil 2 (Bau) terminiert auf 19.08.
**Nicht geschlossen:** nichts, was für diesen Sprint geplant war.

Der Sprint hat der Organisation **einen** neuen Endpunkt, **eine** neue Kachel, **27** neue Tests
(380 gesamt, vorher 353) und **einen** neuen SWR (103 gesamt, 0 Lücken) gebracht — und zwei
Befunde, die beide in `process/knowledge/cm/lessons.md` stehen.

## Wie dieser Plan entstanden ist

Gesichtet wurden **alle** Tickets **aller** entdeckten Repos (16 Git-Repos plus die drei Projekte
in `projects/`): **241 Tickets**, davon 219 `done`, 4 `rejected`, **15 `open`, 3 `in_review`**.
Die 18 nicht geschlossenen stehen oben vollständig — keine Auswahl, keine Kürzung.

**Befund dieses Laufs: `pm/T-0016` war unsichtbar.** `cockpit_alle` meldete organisationsweit
`unterminiert = 1`; dahinter stand `pm/T-0016` (`typ: change-request`, `prio: hoch`, ohne Frist,
ohne `takt`). Es stand in **keiner** der drei Agendalisten — weder unter „Für dich", noch unter
„Für das Team", noch bei den Takt-Dauerläufern. Das ist der **vierte** Auftritt des Musters aus
**B049**: die Eskalationsregel B044 sieht nur Tickets **mit** Frist, und der einzige Melder für den
Rest ist eine Zahl je Kachel. Dass es diesmal ausgerechnet den CR traf, der die Workflow-Sicht
liefern soll, ist kein Zufall, sondern derselbe blinde Fleck aus der anderen Richtung.

**Warum die Sicht den Plan gegen den Bestand prüft.** Diese Tabelle ist eine **Entscheidung** des
PM (welches Ticket in diesen Sprint geht) und steht deshalb hier und nicht in den Tickets — dort
gibt es kein Feld dafür. Genau darum kann sie aber vom Bestand abdriften: ein Ticket, das nach dem
Schreiben entsteht, fehlt hier und fällt niemandem auf. Der Endpunkt aus `pm/T-0016` meldet
deshalb ausdrücklich, welche offenen Tickets in **keiner** Planzeile vorkommen
(`nicht_geplant`). Eine Sicht, die nur wiedergibt, was ihr vorgelegt wird, hätte den Befund von
oben nicht finden können.

## Nicht in diesem Sprint — und warum nicht

* **`pm/T-0036` + `pm/T-0038` (23.08.)** — beide fügen dem generierten `BOARD.md` eine Spalte
  bzw. Zeile hinzu. Zwei getrennte Formatänderungen am Board haben am 16.08. früh alle
  board-check-Workflows rot gemacht; sie gehören in **eine** Session (B053).
* **`pm/T-0039` (23.08.)** — Briefverlauf: Dateiformat, Schreibpfad, Statuslogik, Preflight-Zahl
  und HMI gleichzeitig. Neben `T-0016` in einem Lauf wäre es die vierte Fläche (B025).
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
