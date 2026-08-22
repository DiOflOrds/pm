# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Sprint-Plan (Sprint 38 — beim Abschluss auf Sprint 39 fortgeschrieben)

*Sprint 38 eröffnet 2026-08-22 16:30 (`s38-2026-08-22-1630`), 36 Min nach dem Ende von
Sprint 37. Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt
ihren Grund **im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet: **alle** Tickets
**aller** Repos über **beide** Ebenen (388 Ticketdateien, davon 40 nicht geschlossen).
Offen beim Start: **40** (32 `open`, 7 `in_review`, 1 `blocked`). Briefkasten beim Start:
**0 offen / 71 Briefe** — ⚠ Nachmessung am Ende ist Pflicht (`L-2026-08-21cs`).*

### Der Plan

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (beide Ebenen, inkl. `projects/*`) | pl | Sprint 39 | **geschlossen** | 0 offen / 71 beim Start, 0 offen / 71 am Ende. Nachgemessen, nicht angenommen. |
| **platform/T-0073** | dev | Sprint 39 | **in_review** | ⚠⚠ **Der Betriebsblocker, und er ist gefallen.** 77 Auto-Abschlüsse des Hosts, **kein einziger** mit `PREFLIGHT: 0`; 23 brachen an der Lock-Zeile ab. `SWR-217` (Räumung nach Alter statt Geräte-Prozessliste) + `SWR-218` (Teststrecke misst nie eine ältere Fassung). |
| **team-mail/T-0006** | dev | Sprint 39 | **in_review** | ⚖ **Fünfte Berührung — Entscheidung BAUEN endlich ausgeführt.** `SWR-219`: Digest endet im Ausgang, Versand aus dem Betrieb unerreichbar. ⚠ Der Versand war bereits verdrahtet und nur durch ein fehlendes `SMTP_HOST` gehemmt. |
| **pm/T-0079** | pl | Sprint 39 | **in_review** | ⚖ **Vierte Berührung → entschieden statt terminiert** (`pm/B061`). Lesart 1: Definition gleich, Besetzung je Instanz; Abweichung wird sichtbar (`SWR-220`). |
| **team-dashboard/T-0001** | pl | Sprint 39 | **in_review** | Takt `je-session` erfüllt: Vertrag **v2.9**, Obergrenze für Kacheln + `sicht_takt`. **Die gemeinsame Ursache von `T-0004`/`T-0006`/`T-0007` ist damit entschieden.** |
| **team-dashboard/T-0007** | dev | Sprint 39 | geplant | ⚠ **Der Auftraggeber wartet.** Ursache 1 und 3 sind in Sprint 38 **am laufenden Renderweg bestätigt** (3 Takte / 12 Kacheln; SPAM-Grund 3×). Offen: Ursache 2 (Browser), Umstellung auf `sicht_takt`, Kachelhöhe als Zahl, JS-Zusicherung, Screenshot. **Die Vertragsfrage ist ihm abgenommen.** |
| **team-dashboard/T-0004**, **team-dashboard/T-0006** | dev | Sprint 39 | geplant | Warteten auf den Kachel-Vertrag; **die Sperre ist mit v2.9 gefallen.** Erste Terminierung mit Arbeitsmöglichkeit. |
| **platform/T-0071** | dev | Sprint 39 | geplant | Aus Brief `platform/N-0010`: alle Script-Aufrufe in Mission Control + Wächter live sichtbar. ⚠ **In Sprint 38 zum vierten Mal in Produktion getroffen** — die Nachverbuchung des Hosts hat zweimal einen Session-Commit absorbiert und die Ticket-ID im Betreff verloren. Prio hoch. |
| **platform/T-0072** | dev | Sprint 39 | geplant | `start_genesis` als EIN Startpunkt. Hängt am Ergebnis von `T-0071` — nacheinander, nicht parallel. |
| **platform/T-0055** | dev | Sprint 39 | in_review | Teil A geliefert (`SWR-215`); Review offen. |
| **platform/T-0066** | pl | Sprint 39 | in_review | `SWR-214`; Review offen. ⚠ Die Besetzungsfrage dahinter ist mit `pm/B061` beantwortet — **und die Messung sagt, dass sie nicht der Engpass war.** |
| **platform/T-0068**, **platform/T-0069** | dev/prob | Sprint 39 | in_review | Review offen (Reviewer ≠ Autor). |
| **platform/T-0064** | cm | Sprint 39 | geplant | Anhänge-Dateien ohne Überschreibschutz. Zweite Terminierung. |
| **platform/T-0067** | coach | Sprint 39 | geplant | „Wer liest die maschinellen Befunde?" ⚠ **Sprint 38 ist der bislang schärfste Beleg:** der Lock-Befund stand 23 Läufe lang wörtlich im Protokoll, und im selben Protokoll stand die Begründung, warum er keiner ist. |
| **platform/T-0070** | coach | Sprint 39 | geplant | Acht Lehren ohne Vertreter. |
| **pm/T-0071** | pl | Sprint 39 | geplant | F18 Ollama-Schnelltakt. ⚠ Nachweis geführt; die **Wirkung** hängt an `aufgaben_typ`, nicht an der Besetzung (`pm/B061`). |
| **pm/T-0080** | dev | Sprint 39 | geplant | ⚖ Vierte Berührung → geschnitten, Teil A. |
| **pm/T-0082** | pl | Sprint 39 | geplant | ⚖ Wartete auf `pm/T-0085`; das ist `in_review`. |
| **pm/T-0085** | pl | Sprint 39 | in_review | `pm/B060` + `SWR-216`; Review offen. |
| **promt-team/T-0012** | prompt-opt | Sprint 39 | geplant | Ollama-Umstellungsprogramm, Baseline + Goldset je Aufgaben-Typ. ⚠ **Nach der Messung von `pm/B061` ist das der eigentliche Engpass**: 1 von 40 offenen Tickets trägt überhaupt einen `aufgaben_typ`. Prio hoch, und die Begründung ist neu. |
| **promt-team/T-0003** | dev | Sprint 39 | geplant | Erstaudit nach Ablauf S0–S7. |
| **team-mail/T-0007** | dev | Sprint 39 | geplant | Digest ohne SPAM-Rubrik. ⚠ Braucht **eine Zahl vom Auftraggeber** — als Rückfrage, nicht als Annahme. |
| **team-termine/T-0001**, **team-termine/T-0002** | pl/cm | Sprint 39 | in_review | Projektplan v1.0 und CM-Plan P16; QM-Review offen. |
| **team-termine/T-0003** | coach | Sprint 39 | geplant | Workflows + projektspezifische Rollenbeschreibungen. |
| **team-termine/T-0004**…**T-0010** | rm/arch/qm/test/dev/prob/chg | Sprint 39 | geplant | Rollen-Initialisierung P16. Zweite Terminierung mit Arbeitsmöglichkeit. |
| **team-termine/T-0011** | pl | Sprint 39 | geplant | PL-Monitoring. ⚠ Trägt `takt: je-session` **und** `geplant_sprint` — B033, weiter als Befund benannt. |
| team-termine/T-0012 | qm | jeder Sprint | blocked | Zeigt auf `team-termine/T-0006` (offen) — `SWR-204` erfüllt, Sperre zu Recht. |
| pm/T-0001, pm/T-0002, pm/T-0003 | pl/pl/coach | jeder Sprint | geplant | Takt-Dauerläufer (Session-Agenda, Intake-Queue, LeLe-Konsolidierung). |
| platform/T-0001, team-mail/T-0001 | cm/dev | jeder Sprint | geplant | Takt-Dauerläufer. |

**Unterminiert: nichts.** 40 offene Tickets, 40 Planzeilen (Takt-Dauerläufer gebündelt).

### Was Sprint 38 geliefert hat

| Ticket | Anforderung | Kern |
|---|---|---|
| `platform/T-0073` | `SWR-217` | Lock-Räumung nach **Alter** des Artefakts statt nach der **Prozessliste des Geräts** |
| `platform/T-0073` | `SWR-218` | Teststrecke mit Bytecode-Cache **außerhalb** des Mounts |
| `team-mail/T-0006` | `SWR-219` | Digest endet im **Ausgang**; Versand aus dem Betrieb **unerreichbar** |
| `pm/T-0079` | `pm/B061` + `SWR-220` | Definition gleich, **Besetzung je Instanz** — Abweichung wird **sichtbar** |
| `team-dashboard/T-0001` | Vertrag **v2.9** | **Obergrenze** für Kacheln + `sicht_takt`, im selben Lauf geliefert |

### ⚠⚠ Der Fund dieses Sprints: zwei Prüfungen desselben Hauses, ein Artefakt, entgegengesetzte Urteile

`raeume_locks` zählte die sieben `index.lock` als **Befund** und brach damit den
Auto-Abschluss ab. **160 Zeilen tiefer** beurteilt `repo_status` **dasselbe Artefakt im
selben Lauf** ausdrücklich als *„Auf dem Host löschbar; kein Befund"* — mit
ausgeschriebener Begründung (`SWR-191`, `SWR-166`).

> **Abgebrochen ist der Lauf an dem Pfad OHNE die Begründung.**

Dass es ein Falschbefund war, stand in demselben Protokoll: alle sieben Repos meldeten in
derselben Sekunde `sauber`. **Die Sperre hat nichts gesperrt.**

### ⚠⚠ Und der Lauf hat sechs eigene Messungen widerlegt, bevor er sie berichtet hat

Beim Nachmessen der Mutationsproben hielt Python ein `__pycache__/*.pyc` für gültig,
dessen Bytecode von einer **Probe** stammte: eine Probe ändert ein Zeichen
(`befunde += 1` → `+= 0`) und behält die **Größe**, die Rücknahme trifft dieselbe
`mtime`-Sekunde, und der Cache ist auf diesem Mount nicht löschbar (R7).

> **Eine Zusicherung, die eine andere Fassung misst als die im Repo, sieht genauso grün
> aus wie eine, die stimmt — und die Mutationsprobe ist genau die Bearbeitung, die diese
> Falle stellt.**

Gemessen: dieselbe Strecke meldete aus der Quelle `OK` und aus dem alten Cache
`FAILED (1)` bei byte-identischer Datei. **Alle Probenzahlen dieses Berichts sind mit
frischem Cache nachgemessen.**

### ⚠ Eine eigene Probe war ungültig und steht hier statt eines Hakens

Die sechste Probe zu `SWR-220` löschte den `except`-Block und erzeugte damit eine Datei,
die **nicht parst**. Der Lauf zählte „0 rot" und hätte das als Erfolg berichten können.
**Eine Probe, die den Bau zerstört statt die Regel zu verfälschen, misst nichts** —
korrigiert zu „Registerdefekt wird verschwiegen", Ergebnis rot.

### ⚠⚠ Schritt 1b vor der Planung: die Belege gelesen, die von allein entstanden sind

Lehre 13/14 (`L-2026-08-22a`, `-c`) verlangt Run-Registry, Decision-Log und
Takt-Protokolle **vor** der Planung. Gelesen, und drei der vier Funde sind Neuigkeiten:

| Quelle | Befund dieses Laufs |
|---|---|
| `waechter-status.json` | ✅ **Der Wächter LEBT wieder** — Herzschlag `2026-08-22 14:27:21`, PID 23284. Der Sprint-36-Befund „14 h tot" ist erledigt, und der Wächter sieht Sprint 37 korrekt (`s37-… laeuft`). **Ohne diesen Blick hätte Sprint 37 einen behobenen Ausfall weitergemeldet.** |
| `abschluss-logs/review-20260822-142500.md` | ⚠⚠ **ERGEBNIS: BEFUNDE (7)**, Exit-Code 1, letzter erreichter Schritt **[1/6]** — der Auto-Abschluss des Hosts bricht seit Stunden im Preflight ab. Kein Push, keine Teststrecke, kein CI. |
| `abschluss-20260822-142500.log`, Fenster `[1/6]`…`[2/6]` | ⚠⚠ **Der EINE Preflight-Befund ist identifiziert** — der, den Sprint 36 ausdrücklich nicht gefunden hat (siehe unten). |
| `*/management/runs/run-registry.jsonl` | Ollama-Tick `status: ok`, `gemma3:27b`, 2 Artefakte, seit 21.08. 20:59 — **unverändert der einzige**; keine neuen Ticks seit dem letzten Lauf. Kein neuer Beleg, aber auch kein übersehener. |
| Decision-Log (alle Einheiten) | `dr_entschieden_nicht_verbucht`: **0**. Lehre 14 greift diesmal ins Leere — richtig so. |

### ⚠⚠ Der Fund, der diesen Sprint eröffnet: unser eigener Plan sperrt den Betrieb des Auftraggebers

Der Schnelltakt des Hosts meldete seit Sprint 36 `PREFLIGHT: 1 Befund(e)`, ohne dass
jemand den Befund benannt hatte. Er steht wörtlich im Protokoll:

    [org] BEFUND: 12 Planzeile(n) nennen eine andere Sprintnummer als ihr Ticket:
        team-termine/T-0001: Plan sagt Sprint 36, Ticket sagt Sprint 37
        platform/T-0068, team-dashboard/T-0007, platform/T-0055, pm/T-0080,
        pm/T-0082, team-dashboard/T-0004, team-mail/T-0006, platform/T-0064,
        pm/T-0071, team-termine/T-0002, pm/T-0085                    (… 12 gesamt)

> **Sprint 36 hat seine Tickets vorbildlich auf 37 nachgezogen — und seine eigene
> Plantabelle nicht. Damit hat er `plan_drift` (SWR-109/122) von der anderen Seite
> ausgelöst: nicht der Plan lief dem Ticket davon, sondern das Ticket dem Plan.**

Das ist **exakt** `pl.md` Lehre 8 („ein halber Abschluss sperrt den Betrieb — mit dem
Namen der Sorgfalt"), zum dritten Mal in vier Sprints, und diesmal war die Ursache eine
Vorsichtsmaßnahme gegen genau denselben Fehler. ⚠ Die Behebung ist **diese Tabelle** —
keine Codeänderung, kein Ticket. Sie ist die erste Handlung des Sprints, weil bis dahin
jeder Host-Takt (alle 15 Min) erneut mit Exit 1 abbricht.

⚠ **Erwartung, keine Messung** (`pl.md` Lehre 10): dass `plan_drift` danach 0 meldet, ist
hier nachgewiesen (Preflight nach dem Schreiben, siehe Verifikation) — dass der
**Host-Abschluss** durchläuft, ist es nicht: Schritte [2/6]…[6/6] laufen auf dem Host.
**Stichprobe für den Menschen:** das nächste `abschluss-logs/review-*.md` nach 14:40 muss
`Schrittfolge: [6/6]` und `Push` statt `NICHT PRUEFBAR` zeigen.

### Verschiebungen mit Grund — vorab benannt, nicht nachträglich

Kein Ticket ist **vor** der Arbeit verschoben worden. Was am Ende nicht geschlossen ist,
trägt Grund und neuen Termin **im Ticket** und erscheint im Abschluss unten.

---

## Sprint-Abschluss (Sprint 37, 2026-08-22)

### Was dieser Sprint geschlossen hat

| Ticket | Wirkung |
|---|---|
| **Plantabelle auf Sprint 37** | ⚠⚠ räumt den **einen** Preflight-Befund, an dem der Auto-Abschluss des Hosts seit Stunden bei Schritt **[1/6]** mit Exit 1 abbrach — kein Push, keine Teststrecke, kein CI |
| `platform/T-0066` → **in_review** | `SWR-214` — der leere Ollama-Takt wird gemeldet, wo er gelesen wird; die maßgebliche Auflösung ist **gemessen**, nicht gewählt |
| `platform/T-0055` Teil A → **in_review** | `SWR-215` — der Herzschlag des Wächters bekommt einen Leser |
| `pm/T-0085` → **in_review** | `pm/B060` + `SWR-216` — die Projektkennung wird bewacht statt umnummeriert; räumt die Vorbedingung von `pm/T-0082` |
| `team-termine/T-0002` → **in_review** | CM-Plan P16 v1.0 — **10 Work Products, 0 Lücken**; die letzte aktive Einheit mit Workflows und ohne WP-Deklaration ist versorgt |

> **Vier Tickets, drei neue Anforderungen, 27 neue Zusicherungen — und die teuerste
> Handlung des Tages war eine Tabelle. Der Befund, den Sprint 36 ausdrücklich nicht
> gefunden hat, war unser eigener Plan.**

### ⚠⚠ Der Fund, der diesen Sprint eröffnet hat, und die Reparatur des Musters dahinter

`abschluss-logs/abschluss-20260822-142500.log`, Fenster `[1/6]`…`[2/6]`:

    [org] BEFUND: 12 Planzeile(n) nennen eine andere Sprintnummer als ihr Ticket

**Sprint 36 hat seine Tickets vorbildlich auf 37 nachgezogen und seine eigene Plantabelle
stehen lassen.** Damit hat er `plan_drift` von der anderen Seite ausgelöst: nicht der Plan
lief dem Ticket davon, sondern das Ticket dem Plan. Das ist `pl.md` Lehre 8 zum **dritten
Mal in vier Sprints**, und diesmal war die Ursache eine Vorsichtsmaßnahme gegen genau
denselben Fehler.

> **⚠⚠ Deshalb ist dieser Abschluss anders gebaut: die 32 Tickets sind auf `geplant_sprint:
> 38` gezogen UND die Fälligkeitsspalte der Plantabelle im SELBEN Schritt mit. Ticket und
> Plan sind zwei Aussagen zu einer Frage — wer nur eine nachzieht, tauscht einen Befund
> gegen den anderen** (`L-2026-08-22e`).

Nachgemessen nach dem Nachziehen, mit laufendem Sprint 37 und Tickets auf 38:
`plan_drift` **0**, `sprint_vergangen` **0**, `status_drift` **0**, `plan_nachlauf` **0**,
`nicht_geplant` **0**. **Beide Prüfungen sind grün, egal ob Sprint 37 läuft oder schon
geschlossen ist** — das war bisher nie der Fall.

### ⚠ Drei Befunde, die keine Planung, sondern Zusicherungen gefunden haben

1. **Ein Brief kam ZWISCHEN den Sprints an.** `platform/N-0010` (Auftraggeber) ist um
   **14:13:59** committet worden — 12 Min **nach** dem Ende von Sprint 36 (14:01), 9 Min
   **vor** dem Beginn von Sprint 37 (14:23). Er war beim Start beantwortet, der Briefkasten
   also zu Recht „0 offen"; dass sich der **Bestand** bewegt hat, sah nur
   `test_post_im_lauf` (70/75 → 71/76). **Dritter Lauf in Folge.**
2. **Ein falsches Grün im eigenen Bau, gefunden von der Nebenzahl.** Der erste Entwurf der
   Sprint-37-Plantabelle stellte die Befund-Tabelle **vor** die Plantabelle.
   `plan_tabelle()` liest die **erste** Tabelle nach der Überschrift — `plan_drift` meldete
   **0**, weil keine einzige Planzeile geparst wurde. Aufgefallen ist es nur an
   `nicht_geplant: 39`.
   > **Eine Prüfung, die nichts findet, weil sie nichts liest, sieht genauso aus wie eine,
   > die nichts zu finden hatte.**
3. **Eine Mutationsprobe hat den eigenen Test widerlegt.** Die Probe „jeder `p*`-Ordner ist
   eine Kennung" blieb **grün** gegen die erste Fassung von `test_projektkennung`: sie
   prüfte die **Ausgabe**, nicht die **Regel**. Geschärft, dann 4 von 4 rot.

### ⚠ Ein vierter Befund über den Betrieb, nicht über die Arbeit

**Die Nachverbuchung des Hosts läuft der Session in die Commits.** `abschluss.cmd` verbucht
alle 15 Minuten die Arbeitskopie unter *„Nachverbuchung … liegengebliebene Arbeitskopie
verbucht"*. Dieser Lauf hat **dreimal** erlebt, dass sein Diff schon verbucht war, während
er noch am `index.lock` wartete — und die Hausregel *„jede Aktion referenziert eine
Ticket-ID, auch im Commit"* ist dabei jedes Mal verloren gegangen.

**Behandlung, ohne Historie umzuschreiben:** die Begründung bekommt einen eigenen leeren
Commit **neben** dem Diff, mit Verweis auf dessen Hash. ⚠ Das ist eine Umgehung, keine
Lösung — die Lösung gehört zu `platform/T-0071`/`T-0072` (ein Startpunkt, ein Wächter, der
weiß, wer gerade schreibt).

### Nicht geschlossen — mit Grund und neuem Termin

| Ticket(s) | Grund | Neuer Termin |
|---|---|---|
| `platform/T-0071`, `T-0072` | Aus Brief `N-0010`, in diesem Lauf **entstanden**; dieser Sprint hat stattdessen die Pipeline entsperrt, ohne die sie niemand sähe | Sprint 38 |
| `team-dashboard/T-0007`, `T-0004`, `T-0006` | Gemeinsame Ursache **Kachel-Vertrag** (`T-0001`); der Vertrag ist nicht angefasst worden, und drei Tickets ohne ihn zu bauen wäre dreimal derselbe Fehler | Sprint 38 |
| `team-termine/T-0003`–`T-0011` | Rollen-Initialisierung P16; `T-0002` (CM-Plan) ist als **Träger der WP-Deklaration** vorgezogen worden und geliefert | Sprint 38 |
| `platform/T-0064`, `T-0067`, `T-0070`, `pm/T-0071`, `T-0079`, `T-0080`, `T-0082`, `promt-team/T-0003`, `T-0012`, `team-mail/T-0006`, `T-0007` | terminiert, nicht erreicht | Sprint 38 |
| `platform/T-0068`, `T-0069`, `team-termine/T-0001` | `in_review` — Reviewer ≠ Autor, das Review steht aus | Sprint 38 |

⚠ **`team-mail/T-0006` ist der einzige Posten mit einer Vierte-Berührung-Entscheidung
„BAUEN", der wieder nicht gebaut ist.** Das ist die fünfte Berührung. Er gehört in
Sprint 38 **vor** die Neuplanung, nicht hinein.

### Verifikation — gemessen, nicht behauptet

| Prüfung | Ergebnis |
|---|---|
| Teststrecke | **111 von 112 Modulen, 1567 Zusicherungen, 0 rot** (in Blöcken gefahren — die Sandbox deckelt einen Aufruf bei ~178 s) |
| ⚠ **nicht gemessen** | `test_js_teststrecke` — läuft in dieser Sandbox über die Zeitgrenze, **weder grün noch rot berichtet** (wie in Sprint 36) |
| Rot im Lauf | **1**, gefunden und geschlossen: `test_post_im_lauf` (Brief zwischen den Sprints) |
| `trace_matrix` | **216 SWRs, 0 Lücken** |
| `organigramm.py --check` | **grün** (21 Dateien) |
| `board.py --check` je Einheit | **grün** |
| `plan_drift` / `sprint_vergangen` / `status_drift` / `plan_nachlauf` / `nicht_geplant` | **0 / 0 / 0 / 0 / 0** — mit Tickets auf 38 **und** Plan auf 38 |
| Briefkasten am Ende | **0 offen / 71 Briefe** (beide Ebenen; die 71. liegt in `projects/p11` — `pl.md` Lehre 6) |
| Work Products | **66 deklariert über 8 Einheiten, 0 fehlend, 0 undeklariert** (vorher 56/7) |
| Workflows | **8 über 5 Einheiten, 0 unabgedeckte Takte, 0 Befunde** |
| Wächter | **lebt** — Herzschlag `2026-08-22 14:27:21`, PID 23284 (Sprint-36-Befund „14 h tot" erledigt) |
| ⚠ **nicht gemessen** | `preflight` vollständig — läuft in dieser Sandbox über die Zeitgrenze. Gemessen ist **wo**: `uebergangshistorie` allein braucht **45 s**, `parkplatz_stand` 0,3 s, `sprint.plan` 6 s, 18× `git status` 9 s |
| Ollama-Offload | **0 Tickets delegiert, Token-Ersparnis 0** — siehe unten |

### ⚠⚠ Ollama-Offload: 0 delegiert, und der Grund ist diesmal gezählt statt vermutet

| Größe | Wert | Quelle |
|---|---|---|
| Ollama aus dieser Sandbox erreichbar | **nein** (`curl 127.0.0.1:11434` leer) | gemessen |
| Ollama auf dem Host erreichbar | **ja** | `waechter-status.json` |
| Instanzen mit `motor: ollama` | **2** (`PROB@platform`, `MAIL-RED@team-mail`) | `besetzungen.yaml` |
| offene Tickets mit ollama-besetzter Rolle | **0 von 34** | `SWR-214` |
| Aufgaben-Typen mit ollama-Kette, die je ein Ticket getragen haben | **2 von 8** | gezählt über alle 383 Ticketdateien |
| Tickets im Gesamtbestand mit gesetztem `aufgaben_typ` | **4 von 383 (1,0 %)** | ebd. |

> **Selbst wenn Ollama von hier erreichbar wäre, hätte es nichts zu tun. Sechs von acht
> Aufgaben-Typen mit Ollama-Kette haben in 383 Tickets noch nie eines getragen — das ist
> keine Auslastungsfrage, das ist eine Absichtserklärung.**

Dieser Lauf hat deshalb den **Engpass** gebaut statt die Delegation zu behaupten
(`SWR-214`). Was fehlt, ist eine **Besetzungsentscheidung** — Klasse B des PM, ausdrücklich
nicht hier mitentschieden, übergeben an `pm/T-0079` mit der Zahl in der Hand.

### ⚠⚠ Nachtrag: die Stichprobe ist gefahren — und sie hat die Erwartung widerlegt

Dieser Sprint hat sich selbst eine Prüfung gestellt (*„das nächste `review-*.md` muss
`[6/6]` und `Push` zeigen"*). Sie ist **zweimal** gelaufen, das zweite Mal mit untätiger
Session:

| Lauf | Org-Prüfungen | Preflight gesamt | Schrittfolge |
|---|---|---|---|
| `review-…-142500` (vorher) | `Plan-Drift: **12 BEFUND**` | **1** | [1/6] |
| `review-…-155500` | `Plan-Drift **0**`, `vergangener Sprint **0**`, `Plannachlauf **0**`, `Statusübergänge **0**` | **7** | [1/6] |
| `review-…-161000` (Session idle) | dieselben **0** | **7** | [1/6] |

> **Die Reparatur hat gewirkt und der Abschluss steht trotzdem. Ein zweiter Befund war die
> ganze Zeit da und wurde von dem einen, der zählte, verdeckt.**

**Die 7 sind `index.lock`-Artefakte in `p9`, `pm`, `projects`, `promt-team`,
`team-dashboard`, `team-mail`, `team-termine` — und der eigentliche Fund ist, dass sie
drei verschiedene Antworten bekommen:**

| Wer fragt | Antwort für `pm/.git/index.lock` |
|---|---|
| Sandbox (`ls`/`stat`) | **existiert nicht** |
| `git` in derselben Sandbox | **existiert** — `unable to unlink … Operation not permitted`, Commit bricht ab |
| Host-Preflight | **existiert** — *„NICHT entfernt (Git-Prozess aktiv)"*, obwohl seit 10 Min kein `git` lief |

⚠ `preflight --nur-locks` meldet danach `STARTKLAR` und `ls` bestätigt es. **Beides ist
wahr und beides misst die falsche Seite des Mounts.**

Aufgenommen als **`platform/T-0073`** (prio hoch, Sprint 38) — im selben Zug mit seiner
Planzeile, nach der Lehre, die dieser Sprint gerade verankert hat. ⚠ Dazu gemessen: der
Lock-Parkplatz ist in **diesem einen Lauf** von 12 630 auf **12 841** gewachsen (+211).

> **Was dieser Sprint über sich selbst gelernt hat: eine Sperre zu räumen beweist nicht,
> dass der Weg frei ist. Es beweist nur, dass diese Sperre weg ist — und das ist genau der
> Unterschied, den eine Stichprobe misst und ein Haken behauptet.**

---

<details><summary>Archiv: Sprint 36 und früher</summary>

## Sprint-Plan (Sprint 36) — Planung VOR der Arbeit

*Sprint 36 eröffnet 2026-08-22 (`s36-2026-08-22-1300`) — der erste Cowork-Lauf mit Shell
seit fünf Sitzungen. Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede
Verschiebung trägt ihren Grund **im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet:
**alle** Tickets **aller** Repos über **beide** Ebenen. Offen beim Start: **38**.
Briefkasten beim Start: **0 offen / 69 Briefe** — ⚠ die Nachmessung am Ende hat das
widerlegt (siehe Abschluss).*

### ⚠ Schritt 0 war beim Start schon erledigt

Die zehn Tickets, die der Folgelauf vom 21.08. als Zeitbombe benannt hat (`geplant_sprint:
35`, obwohl nach 36 verschoben), tragen alle **36**. Der Host-Lauf hat sie nachgezogen.
`--beginne` konnte deshalb ohne Befundlawine laufen.

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (beide Ebenen) | pl | Sprint 36 | **geschlossen** | 0 offen beim Start; **1 neuer Brief im Lauf** (`p0/N-0002`, 12:51) beantwortet und als `team-dashboard/T-0007` qualifiziert. |
| **platform/T-0060** | dev | Sprint 36 | **done** | ⚠⚠ Der Nachweis war **seit dem 21.08. 20:59 geführt** und lag ungelesen im Register: `Gateway: status=ok provider=ollama`, `gemma3:27b`, **2 Artefakte**, 221,2 s. Entsperrt vier Tickets. |
| **team-termine/T-0001** | pl | Sprint 36 | **in_review** | `docs/projektplan.md` v1.0 vollständig (8 Kapitel, Z1–Z5, 6 Phasen, R1–R7). Entsperrt **zehn** Tickets. Review (QM+PM) offen — deshalb nicht `done`. |
| **pm/T-0086** | mensch | Sprint 36 | **done** | ⚠ `pm/D030` = **C** lag seit 00:23 im Log und war **unverbucht**; gefunden von `test_dr_verbuchung`, nicht von der Planung. Option A ist durch diesen Lauf selbst belegt. |
| **platform/T-0068** | dev | Sprint 36 | **in_review** | Vorabfragen **gezählt**: **1** Fundstelle im Bestand, **0 von 75** Belegen fälschlich durchgelassen. 2 neue Zusicherungen + Mutationsprobe (5 rot gegen alten Code). |
| **team-dashboard/T-0007** | dev | Sprint 36 | **neu, open** | Aus Brief `p0/N-0002`: Post-Widget sprengt das Raster (3 Ursachen getrennt). Prio hoch. |
| **platform/T-0055** | dev | Sprint 36 | ⚖ **geschnitten** | **Vierte Berührung.** Teil A (`waechter.py`) ist seit 21.08. **gebaut**; offen bleibt die DoD. ⚠⚠ Der Wächter selbst ist seit **23:25 tot** (14 h), während die Dienste laufen, die er bewacht. |
| **pm/T-0080** | dev | Sprint 36 | ⚖ **geschnitten** | **Vierte Berührung.** Teil A: **eine** Aufgabe, **eine** Spurenquelle (Ticket + `git log`). B/C terminiert. |
| **pm/T-0082** | pl | Sprint 36 | ⚖ **geschnitten** | **Vierte Berührung.** Teil A: Kennung klären (`pm/T-0085`, P13 doppelt) **vor** der Planung. |
| **team-dashboard/T-0004** | dev | Sprint 36 | ⚖ **geschnitten** | **Vierte Berührung.** Teil A: **Kachel-Vertrag** in `T-0001` — gemeinsame Ursache von `T-0004`, `T-0006`, `T-0007`. |
| **team-mail/T-0006** | dev | Sprint 36 | ⚖ **BAUEN** | **Vierte Berührung.** Als einziges **nicht** geschnitten: entsperrt, klein, scharf begrenzt. Auflage: kein Versandweg im Diff. |
| **platform/T-0064, T-0066, T-0067, T-0069, T-0070** | cm/pl/coach/prob | Sprint 36 | geplant | Sprint-36-Bestand aus der Teststrecken-Auswertung; `T-0069` `in_review`. |
| **pm/T-0071, T-0079, promt-team/T-0003, T-0012** | pl/dev/prompt-opt | Sprint 36 | **entsperrt** | Zeigten alle auf `platform/T-0060`; im selben Lauf geräumt (`SWR-204`). |
| **team-termine/T-0002–T-0011** | div | Sprint 36 | **entsperrt** | Rollen-Initialisierung P16; Sperre fiel mit dem Projektplan. `T-0012` bleibt auf `T-0006` gesperrt (zeigt auf ein offenes Ticket, `SWR-204` erfüllt). |
| pm/T-0085, team-mail/T-0007, team-dashboard/T-0006 | pl/dev | Sprint 36 | geplant | Unverändert terminiert. |
| pm/T-0001–T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | geplant | Takt-Dauerläufer. |

**Unterminiert: nichts.**

⚠ **Die Spalte „Fällig" oben ist der Stand der PLANUNG (Sprint 36).** Beim Abschluss sind
**30** nicht geschlossene Tickets im Ticket selbst auf `geplant_sprint: 37` gezogen worden —
**vor** `--beende`, nicht danach. Wer nur diese Tabelle liest, sieht den Plan; wer wissen
will, wann etwas fällig ist, liest das Ticket (`L-2026-08-17ag`).

---

## Sprint-Abschluss (Sprint 36, 2026-08-22)

### Was dieser Sprint geschlossen hat

| Ticket | Wirkung |
|---|---|
| `platform/T-0060` → **done** | entsperrt **4** Tickets |
| `team-termine/T-0001` → **in_review** | entsperrt **10** Tickets |
| `pm/T-0086` → **done** | `wartet_auf_mensch` **1 → 0** |
| `platform/T-0068` → **in_review** | 2 neue Zusicherungen, Mutationsprobe belegt |
| `p0/N-0002` beantwortet | → `team-dashboard/T-0007` |

> **Vierzehn Sperren sind in einem Lauf gefallen — und keine davon durch neuen Code.
> Zwei Nachweise lagen fertig im Haus (Registry-Tick, Decision-Log-Zeile) und ein Plan
> war ein Template geblieben. Der Engpass dieses Hauses war nicht die Arbeit, sondern
> das Lesen dessen, was schon dastand.**

### ⚠⚠ Drei Befunde über uns selbst — alle von Zusicherungen gefunden, keiner von einem Menschen

1. **`pm/D030` war 13 Stunden entschieden und unverbucht.** Gefunden von
   `test_dr_verbuchung`. Der DR zählte in `wartet_auf_mensch` mit, während der Mensch
   längst geantwortet hatte.
2. **Ein Brief kam im Lauf an und wäre unbemerkt geblieben.** `p0/N-0002` (12:51). Der
   Lauf hatte „0 offen / 69 Briefe" gemessen und wäre mit dieser Zahl in den Abschluss
   gegangen — gefunden von `test_post_im_lauf` (69 ≠ 70). **Genau der Fall, für den
   PL-Lehre 7 existiert.**
3. **⚠ Ein unzulässiger Status-Übergang stammt aus DIESEM Lauf.** `platform/T-0068`
   `open -> in_review` (Commit `04da965`) — der Zwischenschritt `in_progress` fehlt.
   Gefunden von `test_uebergang_historie`. **Ursache: `board.py` lief im selben Aufruf
   wie `git commit`, aber mit `;` statt als Tor — die Validierung meldete den Fehler,
   und der Commit lief trotzdem.** Siehe `L-2026-08-22d`.

### Nicht geschlossen — mit Grund und neuem Termin

| Ticket | Grund | Neuer Termin |
|---|---|---|
| `platform/T-0055/T-0064/T-0066/T-0067/T-0069/T-0070` | Bestand aus der Teststrecken-Auswertung; dieser Lauf hat die zwei größten Sperren des Hauses geräumt und die Vierte-Berührung-Entscheidungen gefällt | Sprint 37 |
| `pm/T-0080/T-0082/T-0085`, `team-dashboard/T-0004/T-0006/T-0007`, `team-mail/T-0006/T-0007` | geschnitten bzw. terminiert; erste Teile benannt | Sprint 37 |
| `team-termine/T-0002`–`T-0011`, `pm/T-0071/T-0079`, `promt-team/T-0003/T-0012` | **erst in diesem Lauf entsperrt** — sie waren bis heute nicht arbeitsfähig | Sprint 37 |

### Verifikation — gemessen, nicht behauptet

| Prüfung | Ergebnis |
|---|---|
| Teststrecke | **109 Module, 1553 Zusicherungen** — modulweise gefahren (die Sandbox deckelt einen Aufruf bei ~178 s) |
| Rot am Ende | **1** — `test_uebergang_historie` (Befund 3 oben, **selbst verursacht**) |
| `trace_matrix` | **213 SWRs, 0 Lücken** |
| `organigramm.py --check` | **grün** (21 Dateien) |
| `board.py` je Einheit | **grün** |
| `dr_entschieden_nicht_verbucht` | **[]** (vorher `['pm/T-0086']`) |
| Briefkasten am Ende | **0 offen / 70 Briefe** |
| Ollama-Offload | **0 Tickets delegiert, Token-Ersparnis 0** — Nachweis liegt vor, **aber Ollama ist aus dieser Sandbox nicht erreichbar** (`curl 127.0.0.1:11434` leer); der Takt läuft auf `DESKTOP-8OOO6JS` |

⚠ **Was NICHT gemessen ist:** `test_js_teststrecke` läuft in dieser Sandbox in eine
Zeitgrenze (Node vorhanden, Strecke > 100 s) und ist deshalb **weder grün noch rot**
berichtet. `preflight` ist aus demselben Grund nicht vollständig durchgelaufen — der
Schnelltakt des Hosts meldet zuletzt `PREFLIGHT: 1 Befund(e)`; dieser eine Befund ist in
diesem Lauf **nicht** identifiziert worden und bleibt offen.


### ⚠ Nachtrag zur Verifikation (nach `--beende`, ehrlich gehalten)

`test_uebergang_historie` ist nach dem Sprintende **grün** — und das ist **keine
Reparatur**. Die Zusicherung fragt ausdrücklich nach dem **laufenden** Sprint, also nach
dem, was ein Lauf noch beeinflussen kann (so steht es seit `platform/T-0029` in ihrem
Docstring). Mit dem Abschluss von Sprint 36 fällt der Verstoß aus ihrem Fenster.

> **Der Verstoß ist damit nicht weg, sondern nur nicht mehr rot.** Er steht dauerhaft und
> namentlich in der Liste der fortgeschriebenen Übergänge:
> `platform/tickets/T-0068.md: open -> in_review (Commit 04da965)`.
> Historie wird hier nicht umgeschrieben (Playbook Kap. 16).

**Endstand der Verifikation:**

| Prüfung | Ergebnis |
|---|---|
| `uebergang_historie` im laufenden Sprint | **0** Verstöße (nach Abschluss) |
| dauerhaft fortgeschriebene Verstöße | enthält den eigenen von heute |
| `organigramm.py --check` | grün (21 Dateien) |
| `trace_matrix` | 213 SWRs, **0 Lücken** |
| Briefkasten am Ende | **0 offen** |
| `dr_entschieden_nicht_verbucht` | **[]** |
| Sprint 36 im Register | **beendet** 2026-08-22 14:01 |

---

<details><summary>Archiv: Sprint 35 und früher</summary>


## Sprint-Plan (Sprint 35) — Planung VOR der Arbeit

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren Grund
**im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet: **alle** Tickets **aller** Repos
über **beide** Ebenen (19 Einheiten). Offen beim Start: **33**. Briefkasten beim Start:
**0 offen** — ⚠ nach `L-2026-08-21cs` ausdrücklich KEINE Zusicherung für den Abschluss;
die Nachmessung am Ende ist Pflichtteil dieses Plans.*

⚠⚠ **Sechs Tickets stehen bei ihrer DRITTEN Terminierung — eine vierte gibt es nicht.**
`platform/T-0055`, `platform/T-0060`, `pm/T-0080`, `pm/T-0082`,
`team-dashboard/T-0004`, `team-mail/T-0006` sind je zweimal verschoben. Nach `pl.md`
Regel 2 bekommt ein Ticket beim vierten Termin **keinen Termin, sondern eine
Entscheidung**. Das steht **vor** der Arbeit hier, nicht hinterher im Abschluss: wer
diese sechs erneut schiebt, schiebt sie in einen Zwang.

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (beide Ebenen) | pl | Sprint 35 | geplant | 0 offen beim Start. ⚠ Nachmessung am **Ende** ist Pflicht (`L-2026-08-21cs`). |
| **platform/T-0060** | dev | Sprint 36 | geplant | ⚠⚠ **Dritte Terminierung — und die Diagnose ist zum vierten Mal eine andere.** Vor der Arbeit gemessen am Log des Auftraggeber-Rechners: **87 Läufe, 138 Abbrüche, 0 Erfolge.** Zuerst die zwei Preflight-Befunde räumen, die den Takt abbrechen. ⚠ Sprintnummer am 21.08. vom Host-Lauf auf **36** gezogen — Ticket steht `in_review`, Nachweis entsteht beim Auftraggeber (Befund A). |
| **platform/T-0065** | dev | Sprint 35 | **geschlossen** | Geliefert als **SWR-213** (siehe Abschluss unten). ⚠ Planzeile am 21.08. vom Host-Lauf nachgezogen: solange Sprint 35 lief, war „Plan hinkt nach" geduldet (pm/D006); nach `--beende` wurde daraus der blockierende Befund „Planzeile widerspricht ihrem Ticket" — der Abschlusslauf brach genau daran ab. |
| **platform/T-0064** | cm | Sprint 36 | geplant | Nullte Terminierung. Ursache des 91-Lehren-Verlusts. ⚠ **Zusammen mit `T-0055` zu betrachten** — so steht es in `T-0055`. ⚠ Sprintnummer am 21.08. vom Host-Lauf auf **36** gezogen (Befund A). |
| **platform/T-0055** | dev | Sprint 36 | geplant | Dritte Terminierung. Gegenstand ist durch `T-0064` gewachsen; erst die Taktliste **zählen** (DoD 1). ⚠ Sprintnummer am 21.08. vom Host-Lauf auf **36** gezogen (Befund A); in Sprint 36 vierte Berührung → Entscheidung statt Termin. |
| **pm/T-0085** | pl | Sprint 36 | geplant | Erste Terminierung. DoD 1 und 3 sind in Sprint 35 **beantwortet** (siehe „Gemessen statt verschoben" unten); offen ist die Entscheidung. ⚠ Sprintnummer am 21.08. auf **36** gezogen — das Ticket sagte bereits `geplant_sprint: 36`, diese Zeile noch 35; die Abweichung war einer der drei Preflight-Befunde, die den Schnelltakt seit 16:01 abbrechen lassen. |
| **team-termine/T-0001** | pl | Sprint 36 | geplant | Projektplanung P16 — sie entsperrt neun Tickets. ⚠ Sprintnummer am 21.08. vom Host-Lauf auf **36** gezogen (Befund A). |
| **team-termine/T-0002–T-0010** | div | Sprint 36 | **blocked** | ⚠ Sie standen auf `open` **und** trugen `blocked_by: [T-0001]` — zwei Aussagen zu derselben Frage. Status auf `blocked` gezogen, Termin Sprint 36. |
| **pm/T-0080**, **pm/T-0082** | dev/pl | Sprint 36 | geplant | Je dritte Terminierung. ⚠ Sprintnummern am 21.08. vom Host-Lauf auf **36** gezogen (Befund A); in Sprint 36 vierte Berührung → Entscheidung statt Termin. |
| **team-dashboard/T-0004**, **T-0006** | dev | Sprint 36 | geplant | `T-0004` dritte, `T-0006` nullte Terminierung. ⚠ Sprintnummern am 21.08. vom Host-Lauf auf **36** gezogen (Befund A). |
| **team-mail/T-0006**, **T-0007** | dev | Sprint 36 | geplant | `T-0006` dritte Terminierung (entsperrt, `pm/D015` = B); `T-0007` braucht **eine Zahl vom Auftraggeber** — als Rückfrage, nicht als Annahme. ⚠ Sprintnummern am 21.08. vom Host-Lauf auf **36** gezogen (Befund A). |
| pm/T-0071, pm/T-0079, promt-team/T-0003, promt-team/T-0012 | pl/dev/prompt-opt | — | **blocked** | Alle vier zeigen auf **`platform/T-0060`**. ⚠ Wird `T-0060` in diesem Lauf geschlossen, sind sie **im selben Lauf** zu entsperren — sonst bleibt eine Sperre stehen, deren Hindernis weg ist (`SWR-204`). |
| pm/T-0001–T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | geplant | Takt-Dauerläufer. |
| team-termine/T-0011, T-0012 | pl/qm | — | **blocked** | ⚠ Standen auf `open` **und** trugen `blocked_by` (`[T-0001]` bzw. `[T-0006]`) — derselbe Widerspruch, den Sprint 35 für `T-0002`–`T-0010` aufgelöst hat (Befund B des Folgelaufs). Status am 21.08. vom Host-Lauf auf `blocked` gezogen. |

**Unterminiert: nichts.**

---

### ⚠⚠ Vor der Arbeit gemessen: der Ollama-Takt LÄUFT — auf dem Rechner des Auftraggebers, 87 Mal, ohne einen einzigen Erfolg

Der Offload-Vorbehalt der Session-Anweisung verlangt für `pm/T-0071` einen Tick mit
`status: ok` **und** mindestens einem Artefakt. Vor der Arbeit gemessen, nicht geschätzt:

| Größe | Wert | Quelle |
|---|---|---|
| Ticks mit `status: ok` in den Run-Registries **seit 20.08.** | **0** (über den ganzen Bestand: 4 von 16, einer davon ollama am 06.08.) | `*/management/runs/run-registry.jsonl` |
| Schnelltakt-Läufe seit 20.08. 17:15 (Stichzeit 14:46) | **87** | `ollama-schnelltakt.log` |
| Tick-Abbrüche, alle mit **derselben** Meldung | **138** (davon **110** nach dem Fix von 22:05) | ebd. |
| Erfolgszeilen im Log | **0** | ebd. |

⚠⚠ **Und die Diagnose aus Sprint 34 („aus dieser Sandbox unerreichbar") misst den
falschen Rechner.** Der Takt läuft nicht in der Sandbox, sondern per
`ollama-schnelltakt.cmd` auf `DESKTOP-8OOO6JS`. Dort ist Ollama **erreichbar** — es
antwortet, und zwar mit `404: model 'llama3.1:8b' not found`.

> **Drei Sprints lang haben wir die Erreichbarkeit einer Maschine diskutiert, auf der der
> Takt gar nicht läuft — während sein echtes Protokoll unangetastet im Arbeitsordner lag
> und 87 Mal dasselbe sagte.**

**Die Zeitachse, gemessen statt erzählt:**

| Zeit | Ereignis |
|---|---|
| 20.08. 20:44 | `SWR-167..170` — die „Reparatur", auf die Sprint 33 sich berief |
| 20.08. 21:15 / 21:30 / 21:45 | **6 Versuche, alle `404 llama3.1:8b`** — Sprint 33 schrieb „seither hat es keinen einzigen Versuch gegeben" |
| 20.08. 22:05 | `platform/T-0033` → `done`: Besetzung wird **vor** dem Aufruf geprüft (`SWR-171/172`) |
| seit 22:05 | **110 Abbrüche, 0 Versuche** — der eigentliche Fix ist **nie ausgeführt worden** |

⚠⚠ **Und der Grund der 138 Abbrüche ist unsere eigene Buchführung.** Der Preflight meldet
im Lauf von 14:46 **zwei** Befunde, und beide hat **Sprint 34 selbst erzeugt**:

1. *„4 Planzeile(n) nennen eine andere Sprintnummer als ihr Ticket"* — der Plan von
   Sprint 34 sagte „Sprint 34", die vier Tickets trugen bereits `geplant_sprint: 35`.
2. *„9 Ticket(s) ohne Sprint: `team-termine/T-0002` … `T-0010`"* — die Tickets der
   Projektgründung von Sprint 34.

> **⚠⚠ Unser eigener Sprint-Abschluss hat den Nachweis blockiert, den derselbe Sprint als
> „nicht führbar" gemeldet hat. Die Sperre trug den Namen der Sorgfalt.**

**Beides ist in diesem Plan geräumt** — Punkt 1 durch diese Datei, Punkt 2 durch die
`blocked`-Zeile oben. Der Nachweis ist damit **nicht geführt**, sondern **möglich
gemacht**: Er entsteht beim nächsten Schnelltakt-Lauf auf dem Rechner des Auftraggebers,
nicht hier.

⚠⚠ **Ollama-Offload in diesem Lauf: nichts delegiert, Token-Ersparnis 0 — gemessen.**
`pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt. Alles selbst
erledigt; der fehlende Nachweis ist im Fazit benannt.

---

## Sprint-Abschluss (Sprint 35, 2026-08-21)

> ⚠⚠ **ERSTER PUNKT FÜR DIE NÄCHSTE SESSION — SPRINT 35 IST IM REGISTER NICHT GESCHLOSSEN.**
> Die Sandbox-Shell ist während des Abschlusses ausgefallen (`ENOSPC`) und nicht
> wiedergekommen; `sprint_register.py --beende s35-2026-08-21-1450` konnte nicht laufen.
> `beginne()` verweigert nach `SWR-136` einen neuen Sprint, solange einer läuft, **und
> nennt den laufenden** — das ist die gewollte Wirkung und kein Defekt.
>
> **Zu tun, in dieser Reihenfolge:**
> 0. ⚠⚠ **ZUERST — und diese Zeile ist am 21.08. (Folgelauf) VOR die anderen gestellt
>    worden, nicht dazugeschrieben:** die **zehn** Tickets nachziehen, die noch
>    `geplant_sprint: 35` tragen, obwohl der Abschluss unten neun von ihnen nach
>    Sprint 36 verschoben hat — `platform/T-0055`, `platform/T-0060`,
>    `platform/T-0064`, `pm/T-0080`, `pm/T-0082`, `team-dashboard/T-0004`,
>    `team-dashboard/T-0006`, `team-mail/T-0006`, `team-mail/T-0007`,
>    `team-termine/T-0001`. Je Ticket `geplant_sprint: 36` **und** die
>    Verschiebungsnotiz (`L-2026-08-17ag`: der Grund wohnt im Ticket).
>    **Warum vor Schritt 1:** `sprint_vergangen` (SWR-112) vergleicht gegen
>    `sprint_register.aktuell()`. Solange 35 der laufende Sprint ist, schweigt die
>    Prüfung; nach `--beende` **und** `--beginne` meldet sie **alle zehn** — keines ist
>    `decision-request` oder `blocked`, also greift keine Ausnahme. Wer mit Schritt 1
>    anfängt, sperrt den Schnelltakt zum dritten Mal in Folge mit dem eigenen Abschluss
>    (`L-2026-08-21dp`). ⚠ Genau gezählt: **ein** Befund, der zehn Tickets namentlich
>    nennt (`befunde += 1`) — für den Exit-Code gleichwertig, für jede Zählung nicht.
> 1. `python platform/scripts/sprint_register.py --repos . --beende s35-2026-08-21-1450 --notiz "Sprint 35: Ollama-Blocker geraeumt, SWR-212/213, 17 Gegenlese-Befunde; Abschluss durch Sandbox-Ausfall nur teilweise committet"`
> 2. `python platform/scripts/kennzahlen.py --repos . --schreibe` — der Block unten ist
>    **nicht** fortgeschrieben, deshalb ist `test_berichtskennzahlen` rot.
> 3. Die unter „nicht committet" in `PUSH-ANFORDERUNG.txt` genannten Dateien verbuchen.
> 4. Die Teststrecke ab **Block 2** nachfahren (Module 28–109).
>
> ✅ **Stand 21.08., Host-Lauf des Auftraggebers:** Schritt 0 ist **erledigt** (zehn
> Tickets auf `geplant_sprint: 36` mit Notiz, dazu Befund B: `team-termine/T-0011`/`T-0012`
> auf `blocked`; Planzeilen oben nachgezogen). Schritt 1 und 2 übernimmt
> `reparatur-sprint35.cmd` auf dem Host; Schritt 3 erledigt ab jetzt der neue
> Schritt [0/6] „Nachverbuchung" in `abschluss.cmd`; Schritt 4 läuft dort als
> Schritt [2/6] ohnehin vollständig. ⚠ Neu im Arbeitsordner: `waechter.py`/`waechter.cmd`
> (Brief `platform/N-0008`, Ticket `platform/T-0055` — Betriebsmittel des Auftraggebers,
> DoD des Tickets bleibt offen).
>
> ⚠ **Nicht geglättet:** Der offene Registereintrag wird nicht nachträglich mit einer
> erfundenen Endezeit versehen. `L-2026-08-21da` sagt, „kein Ende" heißt **abgebrochen**
> und nicht aktiv — und dieser Lauf ist genau das: abgebrochen, nach getaner Arbeit.

---

## ⚠⚠ Nachtrag Folgelauf 2026-08-21 (kein Sprint 36, Shell erneut ausgefallen)

Die Shell war zum **zweiten Lauf in Folge** nicht verfügbar (vier identische
Startfehler). Kein `git`, kein `board.py`, kein `preflight`, keine Tests, kein
Ollama-Tick, kein Register. **Nichts gebaut, nichts geschlossen, nichts terminiert.**
Der Lauf hat **gelesen und gerechnet** — und dabei zwei Befunde gefunden, die keine
unserer Prüfungen heute meldet.

### Befund A — zehn Verschiebungen, die nur im Bericht stattgefunden haben

Der Abschluss oben schreibt: *„`platform/T-0055` (+`T-0064`), `pm/T-0080`, `pm/T-0082`,
`team-dashboard/T-0004`, `T-0006`, `team-mail/T-0006`, `T-0007`, `team-termine/T-0001`
→ **Sprint 36**"* und *„Grund je im Ticket"*.

Am Bestand nachgezählt: **kein einziges dieser Tickets trägt `geplant_sprint: 36`.** Alle
neun stehen auf **35**, dazu `platform/T-0060` (`in_review`, ebenfalls 35) — zusammen
**zehn**. `platform/T-0055` trägt als letzte Notiz *„⚠ Verschoben nach Sprint 34"* und
*„⚠ Verschoben nach Sprint 35"*; eine Sprint-36-Notiz existiert nicht. Damit ist auch
„Grund je im Ticket" für diese Tickets **nicht eingelöst** — dieselbe Lücke, die
`L-2026-08-17ag` schon einmal benannt hat.

> **⚠⚠ Eine Verschiebung, die nur im Abschlussbericht steht, hat nicht stattgefunden.
> Sie ist eine Zeitbombe mit Zünder am `--beginne`: heute still, weil `sprint_vergangen`
> gegen den LAUFENDEN Sprint vergleicht — und alle zehn auf einmal in der Sekunde, in der
> der nächste beginnt.**

⚠ **Zwei Korrekturen der eigenen Erstfassung, vom Gegenlesen gefunden:** es ist **ein**
Befund mit zehn genannten Tickets, nicht zehn Befunde; und die Auslösung braucht
`--beende` **und** `--beginne`, weil `beginne()` nach SWR-136 verweigert, solange die
letzte Registerzeile kein `ende` trägt.

Behandlung: **Schritt 0** oben, vor `--beende`. **Nicht in diesem Lauf repariert** — der
Grund steht unter Befund C und ist der wichtigere Teil dieses Nachtrags.

### Befund B — neun von elf geräumt, und keine Prüfung merkt den Rest

`team-termine/T-0011` und `T-0012` stehen auf `status: open` **und** tragen
`blocked_by: [T-0001]` bzw. `[T-0006]` — genau der Widerspruch, den die Planzeile oben
für `T-0002…T-0010` aufgelöst hat (*„zwei Aussagen zu derselben Frage"*). **Neun gezogen,
zwei liegengeblieben** — und beide stehen in der Zeile der Takt-Dauerläufer als
„jeder Sprint / geplant", während `board.offene_blocker` sie dem Orchestrator dauerhaft
entzieht.

Warum es niemand meldet: `board.validiere` prüft nur `blocked` **ohne** `blocked_by`,
nie `open` **mit** `blocked_by`. `board.gesperrt` verlangt beides, also gelten die zwei
als planbar.

> **Eine Regel, die von Hand auf neun Fälle angewandt und nicht als Prüfung gebaut wird,
> ist beim zehnten wieder weg.**

⚠ Als Ticket gehört das in `platform` (Prüfung in `board.validiere`) — **in diesem Lauf
bewusst nicht angelegt**: die nächste freie ID lässt sich ohne `git` nicht gegen HEAD
prüfen (harte Regel), und eine Ticketdatei ist eine Verifikationsquelle (Befund C).

### Befund C — warum A und B NICHT repariert wurden, und warum das die Arbeit ist

`preflight.ist_verifikationsquelle` nennt drei Sorten Datei, die eine Verifikation liest:
`BOARD.md`, `*/requirements/**/software-requirements.md` und **jede** Datei unter
`*/tickets/`. Eine geänderte, **nicht committete** Verifikationsquelle **ist** ein
Preflight-Befund — genau die Sorte, die den Takt gerade blockiert (`pm/tickets/T-0085.md`,
`p9/.../software-requirements.md`).

> **⚠⚠ Ohne `git` verwandelt jede Ticket-Änderung Arbeit in einen neuen Takt-Blocker.
> Zehn Tickets richtigzustellen hieße, zehn Befunde anzulegen, um zehn Befunde zu
> vermeiden.**

Damit bekommt `L-2026-08-21db` („die Teilmenge, die das Werkzeug ohnehin nicht gelöst
hätte") zum ersten Mal eine **nachlesbare Grenze** statt eines Gefühls:
`ist_verifikationsquelle` **ist** die Liste dessen, was ein Lauf ohne Shell nicht anfassen
darf. Alles andere — Plan, Chronik, Rollenkarte, Agenda, Statusbericht — darf er, und
genau das ist in diesem Lauf geschrieben worden (`L-2026-08-21dq`).

⚠ **Zwei Schärfungen, die das Gegenlesen erzwungen hat — „frei" heißt nicht
„folgenlos":**

1. **Diese Datei ist frei, aber nicht ungelesen.** `plandrift`, `statusdrift` und
   `plannachlauf` lesen sie über `backend.sprint.plan`, und `test_berichtskennzahlen`
   vergleicht ihren Kennzahlenblock gegen `kennzahlen.miss()` — über
   `preflight.unit_tests()` ist eine veraltete Kennzahlenzeile also sehr wohl ein
   Blocker. **Dieser Nachtrag hat deshalb weder die Plantabelle noch den
   Kennzahlenblock angefasst.** Zusätzlich abgesichert durch den Bau selbst:
   `plan_tabelle` schneidet ausschließlich die **erste** Tabelle nach der
   Plan-Überschrift; die Tabellen dieses Nachtrags sind für den Plan unsichtbar.
   ⚠ Verbleibende Bruchstelle, benannt statt übermalt: eine Tabelle, die **zwischen**
   Plan-Überschrift und Plantabelle geriete, würde die Plantabelle verdrängen.
2. **`PROJEKTSTATUS-UPDATE.md` und `PUSH-ANFORDERUNG.txt` sind unbedenklich — aber aus
   einem anderen Grund als angenommen.** Sie liegen in der **Arbeitswurzel**, und die ist
   kein Git-Repo; `repos_im_root` sammelt nur Unterverzeichnisse mit `.git`. Sie
   erscheinen in keinem `git status`, statt von `ist_verifikationsquelle` verneint zu
   werden.
   > **Die richtige Antwort aus dem falschen Grund ist keine Messung.**

### Zahlen dieses Laufs — gemessen, mit Definition

| Größe | Wert | Wie gemessen |
|---|---|---|
| Briefkasten offen | **0** | 69 Briefe, beide Ebenen, kein `status: offen` |
| Offene Aufgaben | **34** = 20 `open` + 13 `blocked` + 1 `in_review` | Frontmatter aller `*/tickets/T-*.md` |
| Tickets auf `geplant_sprint: 35`, nicht geschlossen | **10** | Befund A |
| Ollama-Offload | **0** delegiert, Ersparnis **0** | `pm/T-0071` ohne Tick `status ok` + Artefakt; Tick lief mangels Shell nicht |
| Tests / Matrix / Organigramm / `board --check` / `preflight` | **nicht gelaufen** | keine Shell — deshalb **keine Zahl behauptet** |

⚠ **Abweichung zum Vorlauf, benannt statt geglättet:** dieser meldete „34 = 22 `open` +
12 `blocked`". **Die Summe stimmt in beiden Fällen**, die Aufteilung nicht. Die 13
`blocked` sind namentlich: `team-termine/T-0002…T-0010` (9), `promt-team/T-0003`,
`promt-team/T-0012`, `pm/T-0071`, `pm/T-0079`.


**Geschlossen: eins** — `platform/T-0065` (**SWR-213**).
**In Review: eins** — `platform/T-0060` (**SWR-212**); der Blocker ist geräumt, der
Nachweis entsteht auf dem Rechner des Auftraggebers.
**Gemessen statt verschoben: eins** — `pm/T-0085` (DoD 1 und **3** beantwortet).
**Verschoben: der Rest** — Grund je im Ticket.
**Neu angelegt: zwei** — `platform/T-0066`, `platform/T-0067`.
**Briefkasten: 0 offen beim Start UND am Ende** (nachgemessen, `L-2026-08-21cs`);
Post im Lauf **0 Erstbriefe / 0 Beiträge**.

---

## ⚠⚠ Nachtrag Folgelauf 2026-08-21 (DRITTER Lauf ohne Shell — kein Sprint 36)

Fünf identische Startfehler (`useradd failed: exit status 12`, kein Wiederanlauf). Kein
`git`, kein `board.py`, kein `preflight`, keine Tests, kein Ollama-Tick, kein Register.
**Nichts gebaut, nichts geschlossen, nichts terminiert, kein Ticket angefasst** — die
Grenze aus Befund C (`ist_verifikationsquelle`) ist eingehalten.

Dieser Lauf hat **eine** Aufgabe erfüllt, die ohne Shell erfüllbar ist: er hat
nachgemessen, ob die Reparaturen, die der Host-Lauf für sich **berichtet** hat,
im Bestand auch **stehen** — `L-2026-08-17ag` („eine Korrektur, die nur im Bericht
steht, ist keine") gilt auch für Korrekturen, die uns willkommen sind.

### Befund A — nachgemessen: eingelöst

| Ticket | `status` | `geplant_sprint` |
|---|---|---|
| `platform/T-0055` | open | **36** |
| `platform/T-0060` | in_review | **36** |
| `platform/T-0064` | open | **36** |
| `pm/T-0080` | open | **36** |
| `pm/T-0082` | open | **36** |
| `team-dashboard/T-0004` | open | **36** |
| `team-dashboard/T-0006` | open | **36** |
| `team-mail/T-0006` | open | **36** |
| `team-mail/T-0007` | open | **36** |
| `team-termine/T-0001` | open | **36** |

**Zehn von zehn.** Die Zeitbombe am `--beginne` ist entschärft; `sprint_vergangen`
findet nach `--beende` + `--beginne` keines dieser Tickets mehr.

### Befund B — nachgemessen: eingelöst, und die vermutete Folgelücke gibt es nicht

`team-termine/T-0011` und `T-0012` stehen auf `status: blocked` mit `blocked_by`
(`[T-0001]` bzw. `[T-0006]`). ⚠ **Beide tragen kein `geplant_sprint`** — das war der
Verdacht dieses Laufs auf einen neuen `ohne Sprint`-Befund. **Am Code widerlegt, nicht
am Gefühl:** `aggregation._ist_unterminiert` nimmt `blocked` **mit** `blocked_by`
ausdrücklich aus (SWR-198, `platform/T-0051`). Kein Befund. Der Verdacht ist hier
notiert, damit ihn der nächste Lauf nicht ein zweites Mal prüfen muss.

### ⚠ Eine Zählung dieses Laufs war falsch, bevor sie berichtet wurde

Die Erstzählung ergab **19** `open`. Nachgeprüft: `pm/T-0049` steht im Frontmatter auf
`done` und trägt die Zeichenfolge `status: open` im **Fließtext** (Zeile 28, Zitat eines
Befunds). Ohne Shell wird mit einem Zeilenmuster gezählt, nicht mit
`board.parse_frontmatter` — und ein Zeilenmuster kennt die Grenze des Frontmatters nicht.

> **Ein Ersatzwerkzeug misst nicht dieselbe Größe, nur weil es dieselbe Zahl ausgibt.**

### Zahlen dieses Laufs — gemessen, mit Definition und mit ihrer Unschärfe

| Größe | Wert | Wie gemessen |
|---|---|---|
| Briefkasten offen | **0** | 70 Briefdateien, beide Ebenen, kein `status: offen` |
| Offene Aufgaben | **34** = 18 `open` + 15 `blocked` + 1 `in_review` | Zeilenmuster auf `*/tickets/T-*.md`, **ein** Fließtext-Treffer von Hand entfernt |
| `blocked` namentlich | **15** | `team-termine/T-0002…T-0012` (11), `promt-team/T-0003`, `promt-team/T-0012`, `pm/T-0071`, `pm/T-0079` |
| Ollama-Offload | **0** delegiert, Ersparnis **0** | `pm/T-0071` unverändert ohne Tick `status: ok` + Artefakt; `tick.py` mangels Shell nicht gelaufen |
| Tests / Matrix / `organigramm.py --check` / `preflight` | **nicht gelaufen** | keine Shell — **keine Zahl behauptet** |

⚠ `platform/T-0066` und `T-0067` fehlen in der Plantabelle oben — **kein Befund**: sie
tragen `geplant_sprint: 36`, die Tabelle plant Sprint 35. Sie gehören in den Plan, den
der nächste Lauf nach `--beginne` aufmacht.

### Was dieser Lauf NICHT tun durfte und deshalb nicht getan hat

* **Kein Inbox-DR zur Shell.** Drei Läufe ohne Shell sind kein Betriebsunfall mehr,
  sondern eine Frage an den Auftraggeber (Betriebsmittel/Zugänge → **Klasse A**): den
  Takt in der Sandbox reparieren oder ihn ganz auf den Host ziehen, wo
  `abschluss.cmd` und `reparatur-sprint35.cmd` ohnehin laufen. Ein DR ist eine
  Ticketdatei und damit Verifikationsquelle (Befund C) — **benannt statt angelegt**,
  zum zweiten Mal.
* **Kein Commit, kein Push, keine Zeile über gepushte Inhalte.** Es gibt keinen
  Commit, den man pushen könnte.
* **`PROJEKTSTATUS-UPDATE.md` nicht fortgeschrieben** — dieser Lauf hat keinen
  Zustand geändert, den sie melden müsste. Nichts geglättet, kein Termin verschoben.

---

### ⚠⚠ Der Fund des Laufs war der MESSPUNKT, nicht die Messung

Der Ollama-Takt läuft. Er läuft seit dem 20.08. auf dem Rechner des Auftraggebers, und
sein Protokoll lag die ganze Zeit unangetastet im Arbeitsordner.

| Größe (Stichzeit 14:46) | Wert |
|---|---|
| Schnelltakt-Läufe seit 20.08. 17:15 | **87** |
| Tick-Abbrüche, alle mit **derselben** Meldung | **138** |
| davon **nach** dem eigentlichen Fix (20.08. 22:05) | **110** |
| Erfolgszeilen | **0** |

> **⚠⚠ Drei Sprints lang haben wir die Erreichbarkeit einer Maschine diskutiert, auf der
> der Takt gar nicht läuft. Sprint 34 hat sauber gemessen — nur den falschen Rechner.**

Und die 138 Abbrüche sind **unsere eigene Buchführung**: vier Planzeilen mit der alten
Sprintnummer, neun `team-termine`-Tickets ohne Sprint — **beides von Sprint 34 selbst
erzeugt**.

> **Unser eigener Sprint-Abschluss hat den Nachweis blockiert, den derselbe Sprint als
> „nicht führbar" gemeldet hat. Die Sperre trug den Namen der Sorgfalt.**

**Geräumt und nachgemessen:** `unterminierte_tickets` = **0**, `plandrift` = **0**.

---

### ⚠⚠ Das Gegenlesen hat SIEBZEHN Befunde gefunden. Keinen davon der Autor.

**Vierter Sprint in Folge.** Die schwersten drei sind echte Defekte in bereits fertig
gemeldeter Arbeit:

| # | Befund | Kern |
|---|---|---|
| 2 | Ein Feld erbte den Wert seines **Vorgängers** | `provider='claude' modell='gemma3:27b'` — claude hat gemma3 nie angefasst |
| 3 | Ein unbekanntes letztes Kettenglied **löschte die Meldung** des echten Versuchs | `meldung` folgte der Kette, `provider` dem Versuch |
| 10 | Ein Erstbrief mit datumslosem Zeitstempel fiel durch **alle drei** Zahlen | weder gezählt noch `unbestimmbar` — spurlos weg |
| 1 | *„never re-resolved in the core"* hatte **keinen Vertreter** | die verbotene Kopie ließ sich einbauen, **6/6 grün** |
| 4 | Die Klassifikationsprobe war **blind** | alle drei Negativbeispiele ohne Klammer — der Ausdruck wurde nie befragt |
| 7 | Der DoD-Wächter war eine **Stichwortsuche** | ein zweiter Parser blieb grün, `re.compile` im **Kommentar** machte ihn rot |
| 8 | Die Zeitregel wurde zur **Kopie** — im selben Bau, der eine andere Doppelung auflöste | und der Wächter kannte nur die ältere |
| 9 | Die Zusicherung hing an der **Uhr des Läufers** | unter `TZ=UTC` rot, ohne dass etwas kaputt ist |
| 16 | **Fünf** Zusicherungen blieben bei kaputtem Code grün | `assertGreaterEqual` statt Gleichheit; eine Schranke, die strukturell nie greifen kann |
| 17 | Der zurückgegebene **WERT** wanderte | die volle ISO-Zeit ging **unformatiert** in die Briefansicht |

> **⚠⚠ Befund 8 ist der bitterste: derselbe Bau, der eine Doppelung auflöst wie verlangt,
> legt zwanzig Zeilen tiefer eine neue an. Und ihr Wächter kannte nur die ältere Kopie —
> die unbewachte Hälfte ist immer die jüngere.**

**Vier falsche Zahlen korrigiert statt geglättet:** „48 von 74 (65 %)" → gemessen
**46 (62 %)** · „9 von 9 ollama-Einträgen" → **alle 11 `fehler`-Einträge**, 9 ollama und
2 copilot (die Grundmenge war zu klein **und** der Defekt zu eng zugeschnitten) ·
„138 Abbrüche seit 22:05" → **110** · „0 Ticks mit `status: ok`" gilt **seit dem 20.08.**
und nicht überhaupt (Bestand: 4 von 16).

---

### ⚠ Ein eigener Fehler, den das GATE gefunden hat und nicht der Autor

Die Katalogzeile für `SWR-212` wurde **ohne Zeilenumbruch an die Zeile von `SWR-211`
angehängt**. Der Trace-Matrix-Lauf meldete daraufhin *„1 Lücke"* und `SWR-212` als
*„in Tests referenziert, aber nicht im Anforderungsdokument"*.

> **Eine Anforderung, die physisch in der Zeile ihrer Vorgängerin steht, ist vorhanden und
> für jedes Werkzeug unsichtbar. Gefunden hat es das Lücken-Gate — nicht der Autor, der
> die Zeile geschrieben hat, und auch nicht das Gegenlesen.**

Getrennt; danach **213 SWRs / 0 Lücken**.

---

### Verschoben — mit Grund und neuem Termin

`platform/T-0055` (+`T-0064`), `pm/T-0080`, `pm/T-0082`, `team-dashboard/T-0004`,
`T-0006`, `team-mail/T-0006`, `T-0007`, `team-termine/T-0001` → **Sprint 36**.

⚠⚠ **Der Grund ist benennbar und er ist derselbe wie in Sprint 33 und 34 — und genau das
ist das Beunruhigende:**

> **Vier Sprints in Folge hat das Reparieren eigener, bereits fertig gemeldeter Arbeit den
> Lauf gefüllt. 7, dann 7, jetzt 17 Befunde. Das ist keine Pechsträhne mehr, sondern eine
> Eigenschaft unseres Bauens — und sie gehört als solche behandelt, nicht als Ausrede.**

⚠⚠ **`platform/T-0055`, `pm/T-0080`, `pm/T-0082`, `team-dashboard/T-0004` und
`team-mail/T-0006` stehen in Sprint 36 bei ihrer VIERTEN Terminierung.** Nach `pl.md`
Regel 2 bekommen sie dort **keinen Termin, sondern eine Entscheidung** — bauen,
umschneiden oder verwerfen. Das steht hier, damit es nicht wieder erst im Abschluss
auffällt (`L-2026-08-21dk`).

---

## Verifikation (Sprint 35)

| Größe | Wert |
|---|---|
| Anforderungen / Lücken | **213** SWRs (v1.99) / **0** |
| Tests / Testdateien | **1551** / **109** |
| JS-Teststrecke | **116** grün (`js_tests.py`, 114 → 116) |
| Briefkasten | **0 offen** — am **Ende** gemessen |
| Post im Lauf | **0** Erstbriefe / **0** Beiträge / 9 unbestimmbar (`SWR-213`) |
| Offene Tickets | **34** |
| Auf den Menschen wartend | **0** |
| Workflows / unabgedeckte Takte | **8** / **0** |
| Work Products / undeklariert | **56** / **0** |
| `board.py --check` | grün (platform 67, pm 85, team-termine 12) |
| `preflight --nur-locks` | **STARTKLAR** |
| Parkplatz `verwaiste-locks` | **12351** Dateien (Stand 14:46) — nur auf dem Host löschbar |

⚠⚠ **DIE TESTSTRECKE IST NICHT VOLLSTÄNDIG GELAUFEN, UND DAS IST EINE AUSSAGE UND KEINE
FUSSNOTE.** Block 1 (Module 1–27) lief: **415 Tests**, davon **414 grün** und **1 rot** —
`test_berichtskennzahlen` meldet die veraltete Kennzahlenzeile im Plan (erwartetes
Verhalten, sie ist oben fortgeschrieben). **Ab Block 2 ist die Sandbox-Shell
ausgefallen** (`ENOSPC` auf dem Socket-Verzeichnis) und **nicht wiedergekommen**.

> **Die Zahl 1551 stammt aus `unittest.discover`, also aus der SAMMLUNG. Sie sagt, wie
> viele Zusicherungen es GIBT — nicht, dass sie grün sind. 1136 davon sind in diesem Lauf
> nicht ausgeführt worden.**

**Direkt nachgewiesen sind:** die vier neuen/geänderten Module (`test_post_im_lauf` 13,
`test_fehler_nennt_seinen_provider` 9, `test_brief_discovery` 13, plus `test_gateway`,
`test_backend`, `test_kommunikation` u. a. in Block 1), die **116** JS-Zusicherungen und
**alle sechs Mutationsproben**. Nicht nachgewiesen: die Module 28–109 seit der letzten
Änderung an `briefkasten.py`, `kennzahlen.py`, `core.py` und `regeln.js`.

⚠⚠ **Ollama-Offload: nichts delegiert, Token-Ersparnis 0 — gemessen, nicht geschätzt.**
`pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt (0 in allen drei
Run-Registries). **Neu gemessen und damit die Diagnose aus Sprint 34 ersetzt:** der
fehlende Nachweis ist weder ein Modellproblem noch fehlende Erreichbarkeit, sondern
**138 Abbrüche an unseren eigenen Preflight-Befunden**. Alles selbst erledigt.

---

## ⚠⚠ Nachtrag Folgelauf 2026-08-21 (VIERTER Lauf ohne Shell — und der erste, der etwas geschlossen hat)

Vier identische Startfehler, kein `git`, kein `board.py`, kein `preflight`, keine Tests,
kein Ollama-Tick, kein Register — **wie in den drei Läufen davor.** Anders ist, was dieser
Lauf daraus gemacht hat.

> **⚠⚠ Drei Läufe haben „keine Shell → keine Zahl" berichtet, während auf demselben
> Rechner, im selben Ordner, der Host die volle Teststrecke fuhr und ihr Ergebnis in
> `abschluss-logs/` ablegte. Die Zahlen lagen die ganze Zeit da. Es hat nur niemand
> nachgesehen — dieselbe Bewegung wie beim Ollama-Protokoll in Sprint 35, eine Ebene höher.**

### Befund 1 — die Teststrecke ist zum ersten Mal seit vier Sprints vollständig gelaufen, und sie ist ROT

| Größe | Wert | Quelle |
|---|---|---|
| Tests gelaufen | **1551** in 210,4 s | `abschluss-logs/abschluss-20260821-211400.log:10102` |
| **Rot** | **6** | ebd. `:10104` |
| Preflight (Abschlusslauf, alle Repos inkl. p1/Produkte) | **4 Befunde** | `review-20260821-211400.md` |
| Abschlussläufe des Hosts am 21.08. | **8 und wachsend** (20:44 – 22:25) | `abschluss-logs/` |

⚠⚠ **Sprint 35 hat „1551 Tests" als Verifikation berichtet und dazugeschrieben, dass 1136
davon nicht gelaufen sind.** Der erste vollständige Lauf sagt: **sechs sind rot, und keine
davon ist neu.** Die Zahl war nie eine Aussage über Grün — das stand im Bericht, und die
Zahl ist trotzdem als Verifikationszeile geführt worden.

Die sechs, nach Ursache sortiert und terminiert:

| Ursache | Rot 21:14 | Rot 21:55 | Ticket |
|---|---|---|---|
| `goldset` prüft mit `os.path.isabs` — auf dem Host ist `/etc/passwd` **kein** absoluter Pfad | 1 | 1 | **`platform/T-0068`** (dev, hoch) |
| `git_schreibweg`-Nachräumung hängt an `git_prozess_aktiv()`, also an der Prozessliste des Rechners | 2 | **0** | **`platform/T-0069`** (prob, mittel) |
| acht Lehren `L-2026-08-21dj…dq` ohne Vertreter | 3 | 3 | **`platform/T-0070`** (coach, hoch) |
| **Kennzahlenblock veraltet — von DIESEM Lauf verursacht** | 0 | **1** | Befund 4 unten |
| **Summe** | **6** | **5** | |

⚠⚠ **Die zwei `git_schreibweg`-Zusicherungen sind zwischen 21:14 und 21:55 grün geworden,
ohne dass eine Codezeile geändert wurde.** Das ist kein Nebensatz, sondern der Beweis für
`T-0069`: eine Zusicherung, die in 41 Minuten ohne Änderung die Farbe wechselt, misst
nicht ihren Gegenstand.

### Befund 2 — acht Lehren ohne Vertreter, und die Herkunft ist NICHT die, die dieser Bericht zuerst behauptet hat

`test_keine_NEUE_lehre_ohne_vertreter` nennt acht Namen: `L-2026-08-21dj`…`dq`.

⚠⚠ **Die Erstfassung dieses Abschnitts schrieb „alle acht aus den Läufen ohne Shell". Das
unabhängige Gegenlesen hat es nachgezählt und widerlegt — im selben Lauf, vor dem
Abschluss:**

| Lehre | Anlass laut Lehrbuch | Shell? |
|---|---|---|
| `dj` `dk` `dl` `dm` `dn` `do` | **Sprint 35** | **ja** — Sprint 35 hat gebaut (`SWR-213`) |
| `dp` `dq` | Folgelauf, „Shell ausgefallen" | nein |

> **⚠⚠ Sechs von acht, nicht acht von acht. Damit fällt die bequeme Erzählung und die
> unbequeme bleibt: die drei Zusicherungen waren am Ende von Sprint 35 BEREITS ROT — von
> demselben Sprint, der „1551 Tests" als Verifikation führte und dazuschrieb, dass 1136
> davon nicht gelaufen sind.**

Die zwei Läufe ohne Shell haben den Befund um zwei Namen **vergrößert**, nicht erzeugt —
und konnten es nicht merken. Das ist weniger, als hier zuerst stand, und es ist das, was
belegbar ist. **Fünfter Lauf in Folge, in dem das Gegenlesen findet, was der Autor nicht
sah** — diesmal an einem Bericht über genau dieses Muster.

`L-2026-08-21dq` — *„Ohne `git` ist die Ticketdatei tabu, der Rest des Hauses frei"* — ist
**einer der acht.** Beide Hälften sind widerlegt:

* **„Ticketdatei tabu"**: `abschluss.cmd` hat seit dem 21.08. Schritt **[0/6]
  Nachverbuchung** — `git add -A` + Commit in jedem Repo, **vor** dem Preflight, alle
  15 Minuten. Nachgemessen: **0 von 18** Repos unverbucht (21:15), CM-Review-Prüfpunkt
  „Nachverbuchung: **OK**".
  ⚠⚠ Diese Zeile steht in `NOTBETRIEB-OHNE-SHELL.md` **neun Zeilen unter** dem Verbot,
  dem sie den Grund nimmt. Ein Lauf, eine Datei, ein Autor.
* **„der Rest frei"**: Befund 2 selbst.

Die Lehre ist **samt Nachtrag stehen geblieben** und nicht umgeschrieben; das Merkblatt
`NOTBETRIEB-OHNE-SHELL.md` ist berichtigt.

### ⚠⚠ Befund 3 — der Ollama-Takt läuft, ist STARTKLAR, und hat trotzdem nichts zu tun. Das ist die FÜNFTE Antwort auf dieselbe Frage.

| Größe (Stand 21:16) | Wert | Vorlauf (14:46) |
|---|---|---|
| Schnelltakt-Läufe | **114** | 87 |
| Tick-Abbrüche | **177** | 138 |
| Erfolge | **0** | 0 |
| Preflight ab 20:00 | **überwiegend STARTKLAR** (20:00, 20:15, 20:45, 21:00, 21:15) | durchgehend Befunde |

⚠ **„Seit 20:00 STARTKLAR" stand hier zuerst und war zu glatt** (Gegenlesen): der Lauf um
**20:30** meldete `1 Befund` und brach ab. Fünf von sechs, nicht sechs von sechs.

In den STARTKLAR-Läufen bricht der Tick **nicht mehr** ab. Er endet mit einem anderen Satz:

> *„Kein bearbeitbares Ticket (Besetzung): 5 offene(s) Ticket(s) geprüft, keines trägt eine
> Rolle mit motor 'ollama' in Einheit 'platform' — Rollen im Bestand: CM, COACH, DEV, PL;
> mit motor 'ollama' besetzt: PROB@platform. **Der Bestand hat für diese Besetzung nichts —
> ein weiterer Lauf ändert das nicht.**"*

Für `team-mail` dasselbe: Rollen im Bestand **DEV**, ollama-besetzt **MAIL-RED**.

Die vier bisherigen Antworten auf „warum läuft Ollama nie?" lauteten: *Modell fehlt* (404)
· *aus der Sandbox unerreichbar* · *unsere eigenen Preflight-Befunde* · *Git-Sperren des
eigenen Takts*. Die fünfte ist banaler und lag hinter allen vieren:

> **⚠⚠ Genau zwei Besetzungen des Hauses tragen `motor: ollama` — `PROB@platform` und
> `MAIL-RED@team-mail` —, und seit ihrer Einrichtung hat kein einziges offenes Ticket eine
> dieser beiden Rollen getragen. Vier Sprints Diagnose an einer Maschine, der nie jemand
> Arbeit hingelegt hat.**

**Behandelt statt berichtet:** `platform/T-0069` ist mit `rolle: prob` und
`aufgaben_typ: problem-klassifikation` angelegt — Kette `[ollama, session, claude]`,
`tier: standard`, **nicht gate-relevant**. Damit trägt zum ersten Mal ein offenes Ticket
die Rolle, für die diese Besetzung existiert.

⚠⚠ **Das ist ein gelegter Nachweis, kein geführter — und dieser Lauf hat den Takt, dem er
Arbeit hinlegen wollte, DREI Takte lang blockiert.** Gemessen im `ollama-schnelltakt.log`:

| Lauf | Befund | Tick |
|---|---|---|
| 21:55 | `UNVERBUCHT tickets/T-0068.md · T-0069.md · T-0070.md` | **abgebrochen** |
| 22:10 | `UNVERBUCHT tickets/T-0070.md`, `T-0086.md` | **abgebrochen** |
| 22:25 | `UNVERBUCHT tickets/T-0069.md`, `T-0070.md`, `T-0086.md` | **abgebrochen** |

⚠⚠ **Die erste Fassung dieses Absatzes nannte den Lauf um „21:40" und schrieb, der Host
habe es „eine Minute später geheilt". Beides war falsch** (das zweite Gegenlesen hat es
gefunden): der 21:40-Lauf wurde abgebrochen, bevor der Preflight lief, und die Heilung
ist keine — **jede Korrektur an einem Ticket erzeugt eine neue unverbuchte Fassung, und
der Verbucher läuft im 15-Minuten-Takt hinterher.**

> **⚠⚠ Der Lauf, der den Ollama-Nachweis legen wollte, hat den Ollama-Takt mit genau den
> Ticketdateien blockiert, die den Nachweis tragen sollen. Der Verbucher heilt das Fenster
> nicht — er jagt ihm hinterher.**

`pm/T-0071` hat weiterhin **null** Ticks mit `status: ok` + Artefakt; Token-Ersparnis
dieses Laufs **0**. Ob der Nachweis je geführt wird, steht im `ollama-schnelltakt.log`
und **nicht hier**.

⚠ **Was der Betrieb nebenbei bestätigt hat:** die Läufe um 22:10 und 22:25 melden für
alle 18 Repos `sauber` und `board-check: OK` mit den neuen Tickets im Bestand, und
`[org] 1 Ticket(s) warten auf den Menschen: pm/T-0086`. **Die vier Tickets sind formal
gültig und die Entscheidungsanfrage ist im Betrieb angekommen** — das ist die einzige
Verifikation, die dieser Lauf ohne Shell führen konnte, und sie ist geführt.

### ⚠⚠ Befund 4 — dieser Lauf hat selbst eine Zusicherung rot gemacht, und der Host hat es 14 Minuten später gemessen

`abschluss-20260821-215500.log` (nach der Nachverbuchung der vier neuen Tickets):

```
FAIL: test_berichtskennzahlen.SprintplanTest.test_die_zahlen_im_bericht_stimmen_mit_der_messung
AssertionError: [('tickets_offen', 34, 38), ('wartet_auf_mensch', 0, 1)] != []
Ran 1551 tests — FAILED (failures=5)
```

**Der Kennzahlenblock ist unangetastet geblieben — und genau deshalb ist er jetzt falsch.**
Die Schutzregel aus `L-2026-08-21dq` (*„Plantabelle und Kennzahlenblock in Ruhe lassen"*)
schützt vor der falschen Gefahr: der Block veraltet durch das **Ticket**, nicht durch das
Bearbeiten dieser Datei. Dieser Lauf hat die neuen Zahlen oben selbst ausgerechnet und den
Block danebenstehen lassen.

> **⚠ Nicht geglättet:** Der Block wird **nicht** von Hand nachgezogen. `kennzahlen.miss()`
> ist die Quelle, `kennzahlen.py --schreibe` der Weg, und beides braucht eine Shell. Eine
> von Hand eingetragene Zahl wäre eine Behauptung an der Stelle, an der eine Messung steht.
> **Erster Schritt des nächsten Laufs mit Shell:**
> `python platform/scripts/kennzahlen.py --repos . --schreibe`.

⚠ **Zugleich sind zwei rote Zusicherungen von allein grün geworden** — die beiden
`git_schreibweg`-Nachräumungen, **ohne dass eine Codezeile geändert wurde** (6 rot um
21:14, 5 rot um 21:55, davon eine neue). Das ist die Bestätigung der These von
`platform/T-0069`, und sie ist stärker als die Herleitung im Ticket: eine Zusicherung, die
zwischen zwei Läufen ohne Codeänderung die Farbe wechselt, misst nicht ihren Gegenstand.

### Zahlen dieses Laufs — gemessen, mit Quelle

| Größe | Wert | Wie gemessen |
|---|---|---|
| Briefkasten offen | **0** | 69 Briefdateien, beide Ebenen, kein `status: offen` |
| Offene Aufgaben vor dem Lauf | **34** = 18 `open` + 15 `blocked` + 1 `in_review` | Zeilenmuster über `*/tickets/T-*.md`, Fließtext-Treffer `pm/T-0049` von Hand entfernt |
| Offene Aufgaben nach dem Lauf | **38** | + `platform/T-0068`, `T-0069`, `T-0070`, `pm/T-0086` |
| Auf den Menschen wartend | **0 → 1** | `pm/T-0086` (Klasse A, Frist 2026-08-28, Default C) |
| Repos mit unverbuchter Arbeitskopie | **0 von 18** | `ollama-schnelltakt.log` 21:15 |
| Sprintregister | **Sprint 35 beendet 20:21**, kein Sprint läuft (Pause 55 Min) | ebd. |
| Plandrift / Statusdrift / Tickets ohne Sprint / unverbuchte DRs | **0 / 0 / 0 / 0** | ebd. |
| Parkplatz `verwaiste-locks` | **12461** (von 12351) | ebd. |
| Ollama-Offload | **0** delegiert, Ersparnis **0** | `pm/T-0071` unverändert ohne Tick `status: ok` + Artefakt |

⚠ **Zwei Zahlen widersprechen sich, und das bleibt so stehen:** der Abschlusslauf um 21:14
meldet **4 Preflight-Befunde**, der Schnelltakt um 21:15 **STARTKLAR**. Sie messen nicht
dasselbe — `abschluss.cmd` fährt alle Repos **inklusive `p1`/Produkte**, der Schnelltakt
eine Teilmenge. **Welche der beiden die Organisation meint, ist ungeklärt und gehört
geklärt** (keine eigene Karteileiche: es ist Vorabfrage 3 in `platform/T-0069`).

### Was dieser Lauf NICHT getan hat

* **Kein Sprint 36 eröffnet** — ohne Shell kein `sprint_register.py`. Sprint 35 ist seit
  20:21 sauber beendet; `--beginne` ist der erste Schritt des nächsten Laufs mit Shell.
* **Keine Zeile Plattformcode geändert.** Drei Defekte sind diagnostiziert und terminiert,
  keiner gebaut: ohne Teststrecke wäre jede Reparatur eine Behauptung. ⚠ `T-0068` wäre
  eine Zeile gewesen — genau die bequeme Handlung, gegen die dieses Haus seine teuerste
  Lehre trägt.
* **Keine neue Lehre geschrieben.** Das ist die Anwendung von Befund 2 auf den eigenen
  Lauf: Der Nachtrag steht **in** `L-2026-08-21dq`, wo er hingehört, und legt keine
  neunte Lehre ohne Vertreter an.
* **Den Kennzahlenblock NICHT von Hand nachgezogen** (Befund 4) — er ist die Stelle, an
  der eine Messung steht, und eine Shell fehlt.
* **Kein Commit, kein Push.** Es gibt keinen; der Host verbucht (Schritt `[0/6]`).

### Was das Gegenlesen an DIESEM Bericht gefunden hat — vor dem Abschluss, nicht danach

Sechs Befunde, alle im Lauf korrigiert statt geglättet:

| # | Befund | Behandlung |
|---|---|---|
| 1 | *„alle acht Lehren aus Läufen ohne Shell"* — es sind **sechs aus Sprint 35** und zwei | überall richtiggestellt; die unbequemere Aussage steht jetzt da |
| 2 | *„drei Zusicherungen rot gemacht"* — sie waren nach Sprint 35 **schon** rot | „vergrößert, nicht erzeugt" |
| 3 | *„seit 20:00 STARTKLAR"* — 20:30 meldete 1 Befund und brach ab | „fünf von sechs" |
| 4 | *„der Grund war weg"* (Ticketdatei ohne Shell) — der Tick ist genau daran abgebrochen | Befund 3 oben; die Regel in `dq` nennt jetzt den Preis |
| 5 | `pm/T-0086`: *„114 Läufe … am 21.08."* — 114 ist der Stand **seit 20.08. 17:15** | im Ticket berichtigt |
| 6 | **Neu und von diesem Lauf verursacht:** `test_berichtskennzahlen` rot | Befund 4, benannt statt nachgetragen |

**Ein ZWEITES Gegenlesen der Korrekturen fand vier weitere — darunter einen in der
Korrektur selbst:**

| # | Behauptung der Korrektur | Gemessen |
|---|---|---|
| 7 | *„der Tick um **21:40** brach ab"* + *„eine Minute später geheilt"* | **Falscher Lauf und falsche Entwarnung:** 21:40 brach vor dem Preflight ab; die Abbrüche stehen bei **21:55, 22:10 und 22:25** — drei in Folge, weil jede Korrektur eine neue unverbuchte Fassung erzeugt |
| 8 | „an **vier Stellen** richtiggestellt" | mindestens **sieben** — und an einer achten (`PUSH-ANFORDERUNG.txt`) zuerst gar nicht |
| 9 | „**5** Abschlussläufe am 21.08." gegen „6" in `pm/T-0086` | im Verzeichnis liegen **8**; die Zahl wächst während des Laufs und taugt nicht als Kennzahl |
| 10 | drei Kurzfassungen trugen die widerlegte Zuschreibung weiter | nachgezogen |

> **⚠⚠ Fünfter Lauf in Folge, in dem das unabhängige Gegenlesen mehr findet als der Bau —
> und dieses Mal zweimal hintereinander am selben Bericht. Der Autor hat über das
> Nichtzählen geschrieben, dabei nicht gezählt, und beim Berichtigen des Nichtzählens
> wieder nicht gezählt.**

---

<details><summary>Archiv: Sprint 34</summary>

## Sprint-Plan (Sprint 34) — Planung VOR der Arbeit

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren Grund
**im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet: **alle** Tickets **aller** Repos
über **beide** Ebenen. Offen beim Start: **21**. Briefkasten beim Start: **0 offen** —
⚠ und das ist nach `L-2026-08-21cs` ausdrücklich KEINE Zusicherung für den Abschluss; die
Nachmessung am Ende ist Pflichtteil dieses Plans.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (beide Ebenen) | pl | Sprint 34 | **erfüllt** | 0 offen beim Start — **1 Beitrag um 12:26 während des Laufs**, beantwortet und umgesetzt. |
| **platform/T-0062** | dev | Sprint 34 | **geschlossen** | Sieben rote Zusicherungen seit Sprint 32; zuerst zählen (DoD 1), dann bauen. |
| **platform/T-0061** | coach | Sprint 34 | **geschlossen** | Zuerst zählen (DoD 1: echte Lehre gegen Zitat), dann entscheiden. |
| **pm/T-0083** | pl | Sprint 34 | **geschlossen** | Projektgründung `team-termine` (`pm/D016` = B) — in Sprint 32 zugesagt, in 33 verschoben. |
| **platform/T-0056** | cm | Sprint 34 | **geschlossen** | Ursache **messen**, bevor gebaut wird. |
| **team-dashboard/T-0005** | dev | Sprint 34 | **geschlossen (Teil 1)** | Entsperrt durch die Antwort des Auftraggebers um 12:26; Teil 2 abgetrennt als `T-0006`. |
| **platform/T-0063** | cm | Sprint 34 | **geschlossen** | ⚠ **Nicht geplant** — beim Ausführen von `pm/T-0083` gefunden. |
| **platform/T-0055** | dev | Sprint 34 | **verschoben → 35** | Grund im Ticket; Gegenstand ist durch `T-0064` gewachsen. |
| **platform/T-0060** | dev | Sprint 34 | **verschoben → 35** | ⚠ Nicht Kapazität: Ollama ist aus der Sandbox **gemessen unerreichbar**, der Nachweis braucht den Team-Node. |
| **pm/T-0080**, **pm/T-0082** | dev/pl | Sprint 34 | **verschoben → 35** | Grund je im Ticket. |
| **team-dashboard/T-0004**, **team-mail/T-0006** | dev | Sprint 34 | **verschoben → 35** | Grund je im Ticket; `team-mail/T-0006` ist **entsperrt** (`pm/D015` = B). |
| pm/T-0071, pm/T-0079, promt-team/T-0003, promt-team/T-0012 | pl/dev/prompt-opt | — | **blocked** | ⚠ Alle vier zeigen auf **`platform/T-0060`**, das **offen** ist und ein echtes, benanntes Hindernis trägt — `SWR-204` erfüllt. |
| pm/T-0001–T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | geplant | Takt-Dauerläufer. |
| team-termine/T-0001 (+11 blockiert) | pl | Sprint 35 | **neu** | Reihenfolge des Projektmodells: Planung zuerst. |

**Unterminiert: nichts.**

⚠⚠ **Ollama-Offload, vor der Arbeit gemessen (nicht geschätzt):** `pm/T-0071` hat
unverändert **keinen** Tick mit `status: ok` + Artefakt. **Neu gemessen und damit die
Diagnose aus Sprint 33 präzisiert:** Der Grund ist nicht mehr das Modell, sondern die
**Erreichbarkeit** — aus dieser Sandbox ist `localhost:11434` tot und
`host.docker.internal` von der Netz-Allowlist gesperrt. **Token-Ersparnis 0**, alles selbst
erledigt, der fehlende Nachweis ist im Fazit benannt.

---

## Sprint-Abschluss (Sprint 34, 2026-08-21)

**Geschlossen: sechs** — `platform/T-0062` (**SWR-207**), `platform/T-0063` (**SWR-208**),
`platform/T-0061` (**SWR-209**), `team-dashboard/T-0005` (**SWR-210**),
`platform/T-0056` (**SWR-211**), `pm/T-0083` (Projektgründung).
**Verschoben: sechs** — Grund je im Ticket.

**Neu angelegt: sechs** — `platform/T-0063`, `T-0064`, `T-0065`, `pm/T-0085`,
`team-dashboard/T-0006`, `team-mail/T-0007`.

**Neu gegründet:** **P16 `team-termine`** — erstes Projekt oberhalb von `projects/`, mit
`.kein-remote`, 12 Tickets, 2 Workflows.

---

### ⚠⚠ Der teuerste Fund des Laufs: 91 Lehren waren gelöscht, und der Wächter meldete Fortschritt

`platform/T-0061` sollte klären, warum „84 von 119 Lehren in keinem Lehrbuch stehen". Die
Zählung hat die Frage **um 180 Grad gedreht**.

| Stand | `## L-`-Köpfe in `process/knowledge/*/lessons.md` |
|---|---|
| `386627d` (Sprint 32, Abschluss) | **120** |
| `a82f207` (Sprint 32, **nächster Commit**) | **31** |

`a82f207` trägt den Betreff *„Sprint 32: … **Lehren cq-cv verankert** …"*. Sein Diff:
**91 Lehr-Abschnitte gelöscht, 2 hinzugefügt** — `cm/lessons.md` von 1931 auf 26 Zeilen,
`pl/lessons.md` von 831 auf 26. Die Dateien wurden **geschrieben** statt **angehängt**.
**90 der 91 hatten heute nirgends im Haus mehr einen Kopf.**

> **⚠⚠ Ein Commit, der „verankert" im Betreff trägt, hat 91 Lehren entfernt. Und die
> Prüfung, die das hätte finden müssen, meldete es als FORTSCHRITT: „Diese Lehre(n) haben
> einen Vertreter bekommen — bitte die Basis nachziehen."**

⚠ Die Folgerung von Sprint 33 war **ebenfalls falsch**: das Ticket schloss, die Lehren
hätten *„nie in einem Lehrbuch gelebt"*. Zwei Sprints hintereinander trug dieselbe Lücke
eine falsche Erklärung — weil beide Male der **Bestand** gezählt wurde und nie die
**Geschichte der Datei**.

**Der Nachweis der Wiederherstellung ist eine Zahl, die niemand gewählt hat:**
`ohne_vertreter()` liefert wieder **exakt 91** — namentlich dieselbe Menge wie
`OHNE_VERTRETER_BASIS` aus Sprint 31, in **beide** Richtungen leer.

> **Die Basis hatte die ganze Zeit recht. Und die Zurückhaltung von Sprint 33 — „die Basis
> nachzuziehen hätte die Zusicherung in einer Minute grün gemacht und den Befund
> gelöscht" — hat 90 Lehren gerettet.**

---

### ⚠⚠ Das Gegenlesen hat SIEBEN Befunde gefunden. Keinen davon der Autor.

Der dritte Sprint in Folge, in dem das unabhängige Gegenlesen mehr wert ist als der Bau.
Alle sieben sind im selben Lauf behoben.

| # | Befund | Kern |
|---|---|---|
| 1 | `SWR-208`: „jeder Gründungsweg schreibt `status: aktiv`" hatte **keine Zusicherung** | Halbsatz aus **beiden** Wegen entfernt → **139 Tests, keiner rot** — und genau dieser Halbsatz hatte `p13` sein Core Team gekostet |
| 2 | `SWR-208` hat die B033-Falle, die es **benennt**, wieder aufgestellt | `KLASSEN_OHNE_REMOTE` als **Kopie** (2 Werte gegen 4 in `pool`) mit einem Kommentar, der die Gleichheit *behauptet* |
| 3 | `SWR-211`: die Ausnahmeliste konnte **nie feuern** | und ihre „Verfallsprüfung" maß etwas anderes als das, was sie verfallen ließe |
| 4 | `SWR-211`: die Auflage „nie auf HEAD" stand nur im **Fehlertext** | eine Bitte, keine Schranke |
| 5 | `SWR-210`: „JS 107 → 114" war eine **Behauptung** | gemessen 113 → 114; der Läufer zählt die **Datei**, die Datei trägt 7 Zusicherungen |
| 6 | `SWR-209`: „831" stand als **871** da | die Datei hatte nie 871 Zeilen; Gegenmessung 99 statt 95 |
| 7 | `SWR-210`: der Vertragssprung auf **v2.8** wurde zweimal nicht nachgezogen | kein Altbestand, ein **Rückfall** — beide Dateien waren bei v2.7 mitgezogen worden |

> **⚠⚠ Befund 2 ist der bitterste: derselbe Bau, der die Doppelung BENENNT, legt eine neue
> an — mit einem Kommentar, der die Gleichheit behauptet, statt sie herzustellen. Ein
> Kommentar behauptet; `assertIs` stellt her.**

---

### ⚠ Zwei eigene Fehler dieses Laufs, benannt statt geglättet

**Erstens: derselbe Schreib-statt-Anhängen-Fehler, keine Stunde nach seiner Lehre.**
`team-dashboard/tickets/T-0005.md` wurde beim Fortschreiben überschrieben; der Kopf mit
Frontmatter war weg. Wiederhergestellt aus Git.

⚠⚠ **Und die erste Erklärung dafür war falsch — sie stand schon im Ticket, bevor sie
nachgemessen wurde.** Sie lautete: *„`board.py` sieht ein Ticket ohne Frontmatter gar
nicht."* Gemessen an einer Kopie: `Probleme: ['T-0005.md: kein Frontmatter']`.

> **Das Werkzeug hat den Fehler gefunden und den Dateinamen genannt. Der Aufruf lief mit
> `>/dev/null 2>&1`. Eine Prüfung, deren Ausgabe man wegwirft, ist teurer als keine — sie
> erzeugt den Eindruck, geprüft zu haben.**

**Zweitens: die eigene Kennzahl hat den Brief dieses Laufs nicht gesehen.**
`briefe_im_lauf` meldet **0**; nachgemessen ist es **1** (12:26). Die Größe liest nur das
Frontmatter `zeit` — den Zeitpunkt, zu dem ein Brief **angelegt** wurde, nicht den eines
neuen **Beitrags**. Aufgeschrieben als `platform/T-0065`, **nicht** im Bericht
stillschweigend korrigiert.

---

### Verschoben: sechs — mit Grund, neuem Termin und ohne Floskel

`platform/T-0055`, `platform/T-0060`, `pm/T-0080`, `pm/T-0082`,
`team-dashboard/T-0004`, `team-mail/T-0006` → **Sprint 35**, Grund **im jeweiligen
Ticket**. Alle sind **zweite** Verschiebungen; die Regel der vierten Berührung ist nicht
berührt.

⚠ **`platform/T-0060` ist der Sonderfall und steht als solcher da:** der Nachweis braucht
einen **fremden Rechner**. Gemessen: `localhost:11434` antwortet nicht,
`host.docker.internal` ist von der Netz-Allowlist gesperrt. Bei der vierten Berührung wird
**entschieden** (Lauf auf dem Team-Node oder Ollama-Weg schneiden), nicht terminiert.

---

## Verifikation (Sprint 34)

| Größe | Wert |
|---|---|
| Anforderungen / Lücken | **211** SWRs (v1.97) / **0** |
| Tests / Testdateien | **1529** / **107** |
| JS-Teststrecke | **114** grün (Läufer-Zählung; die neue Datei trägt 7 eigene Zusicherungen) |
| Briefkasten | **0 offen** — am **Ende** gemessen |
| `briefe_im_lauf` | **0** — ⚠⚠ **falsch**, nachgemessen **1** (`platform/T-0065`) |
| Offene Tickets | **33** (davon **12** aus dem neuen Projekt `team-termine`) |
| Auf den Menschen wartend | **0** |
| Workflows / unabgedeckte Takte | **8** / **0** |
| Work Products / undeklariert | **56** / **0** |
| Lehren / ohne Vertreter | **132** / **91** — ⚠ und **91 = 91** gegen die Basis aus Sprint 31, in beide Richtungen leer |
| Verschwundene Lehren | **0** (vor der Wiederherstellung: **99**) |
| Baselines: abgenommen / getaggt | **13** / **13** — `p12-v1.0` nach vier Tagen nachgetragen |
| Organigramm | grün (**21** Dateien) |
| `board.py --check` | grün über **19** Einheiten |

⚠ **Die Teststrecke ist in BLÖCKEN gefahren, und die Restmenge ist benannt (`SWR-189`).**
Die volle Sammlung (107 Module) überschreitet in dieser Sandbox das Zeitlimit von 178 s
und lief **nicht am Stück**. Gefahren und grün:

| Block | Tests |
|---|---|
| Module 1–27 | **415** |
| Module 28–42 | **211** |
| `kommunikation`, `konsole`, `liegengeblieben`, `mail_autopilot` | **33** |
| `lehrbuch_verliert_nichts` … `organigramm` (9 Module) | **126** |
| `organisation` … Modul 75 | **274** |
| Module 76–92 | **274** |
| `tote_sperre`, `trace_matrix`, `typ_literale` | **41** |
| `uebergang_sammelrepo` … `workproducts` (11 Module) | **122** |
| **Summe** | **1496 von 1529, alle grün** |

⚠⚠ **Zwei Module sind NICHT gelaufen und das ist eine Aussage, keine Fußnote:**
`test_js_teststrecke` und `test_uebergang_historie` überschreiten einzeln das Zeitlimit.
Ihr **Gegenstand** ist ersatzweise direkt nachgewiesen — die JS-Strecke über
`js_tests.py` (**114** grün) und die Übergangsregel über `board.py --check` in allen 19
Einheiten —, aber **die Module selbst sind ungeprüft**. „Nicht betroffen" wäre eine
Behauptung und kein Messergebnis.

⚠ `preflight.py` überschreitet in dieser Sandbox ebenfalls das Zeitlimit und ist **nicht
durchgelaufen** (unverändert gegenüber Sprint 33); die Lock-Räumung (`--nur-locks`) lief
mehrfach und meldete **STARTKLAR**.

⚠⚠ **Ollama-Offload: nichts delegiert, Token-Ersparnis 0 — gemessen, nicht geschätzt.**
`pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt. Neu gemessen: der
fehlende Nachweis ist **kein Modellproblem** (das war die Diagnose von Sprint 33) und auch
kein fehlender Versuch, sondern **fehlende Erreichbarkeit** aus dieser Sandbox.

---

</details>

<details><summary>Archiv: Sprint 33</summary>



## Sprint-Plan (Sprint 33) — Planung VOR der Arbeit

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren Grund
**im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet: **alle** Tickets **aller** Repos
über **beide** Ebenen (`*/tickets/` **und** `projects/*/tickets/`) — das ist die Korrektur
aus `L-2026-08-21cs`, an der Sprint 32 eine Projekt-Freigabe verloren hat. Offen: **20**
(`kennzahlen.py` 10:21, einstimmig nach `SWR-202`). Briefkasten beim Start: **0 offen**,
über beide Ebenen gemessen — ⚠ **und das ist nach `L-2026-08-21cs` ausdrücklich KEINE
Zusicherung für den Abschluss; die Nachmessung am Ende ist Pflichtteil dieses Plans.***

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (beide Ebenen) | pl | Sprint 33 | **geplant** | 0 offen beim Start. **Nachmessung am Sprint-Ende ist eigener Planpunkt**, nicht Nebenprodukt der Kennzahlen. |
| **platform/T-0058** | dev | Sprint 33 | **geplant** | ⚠⚠ **Erste Terminierung**, prio **hoch**. Zuerst zählen (DoD 1–2: Menge heute, Vorgeschichte in den Logs), dann entscheiden „vierter Zustand" gegen „Einzelfälle". ⚠ Berührt möglicherweise Klasse A → dann Inbox-DR statt Eigenentscheid. |
| **platform/T-0057** | dev | Sprint 33 | **geplant** | ⚠⚠ **Erste Terminierung**, prio **hoch**. Zuerst zählen (DoD 1: wie oft kommt ein Brief WÄHREND eines Laufs), dann **eine** Discovery mit Zusicherung. |
| **platform/T-0054** | cm | Sprint 33 | **geplant** | Erste Terminierung, prio niedrig. Restmenge der Endzustands-Literale nach `SWR-202`. |
| **pm/T-0083** | pl | Sprint 33 | **geplant** | ⚠ **NEU und in Sprint 32 ZUGESAGT, aber nie angelegt** — `pm/T-0078` nennt es wörtlich als nächsten Schritt. Projektgründung `team-termine` nach `pm/D016` = **B**. |
| **pm/T-0082** | pl | Sprint 33 | **geplant** | Erste Terminierung. Sprint-0-Planung p13 (Projektauftrag freigegeben, `p13/D000` = G0a). |
| **team-mail/T-0006** | dev | Sprint 33 | **geplant** | ⚠ Steht auf `blocked_by: [pm/T-0081]` — und `T-0081` ist mit `pm/D015` = **B** **entschieden**. Die Sperre ist beantwortet und **auflösend** (anders als bei `T-0077`); zu entsperren und zu terminieren. |
| **platform/T-0055** | dev | Sprint 33 | **geplant** | Erste Terminierung, prio hoch (Brief `N-0008`). Wächter über die regelmäßigen Skripte. |
| **platform/T-0056** | cm | Sprint 33 | **geplant** | Erste Terminierung, prio mittel (Brief `N-0009`). Ursache der ausbleibenden Baselines **messen**, bevor gebaut wird. |
| **pm/T-0080** | dev | Sprint 33 | **geplant** | Erste Terminierung, prio hoch (Brief `N-0046`), in Sprint 32 bereits **zerlegt** — nur Schritt 1. |
| **team-dashboard/T-0004**, **T-0005** | dev | Sprint 33 | **geplant** | Erste Terminierung, prio mittel (Briefe `N-0003`, `N-0004`). |
| pm/T-0071, pm/T-0079, promt-team/T-0003, promt-team/T-0012 | pl/dev/prompt-opt | — | **blocked** | ⚠⚠ Alle vier zeigen auf **`pm/T-0077`, das `done` ist** — genau der Gegenstand von `platform/T-0058`. **Keine Terminierung, bis T-0058 den zulässigen Zustand geklärt hat**; sie stillschweigend zu terminieren wäre die bequeme Handlung aus `SWR-166`. |
| pm/T-0001, pm/T-0002, pm/T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | geplant | Takt-Dauerläufer: Agenda + Intake + Lessons + Werkzeugpflege + Widget-Vertrag + Digest. |

**Unterminiert: nichts.** ⚠ **Reihenfolge ist Absicht:** `T-0058` und `T-0057` zuerst,
weil beide mit einer **Zählung** beginnen und die Zählung den Bau verändern kann — die
vierfache Bestätigung dieses Musters steht in den Sprints 29–32.

⚠⚠ **Ollama-Offload, vor der Arbeit gemessen (nicht geschätzt):** `pm/T-0071` hat
**keinen** Tick mit `status: ok` + Artefakt. Über alle drei Run-Registries gezählt:
**11 × `fehler`**, **4 × `ok`** — und die vier `ok` tragen **`provider: copilot`**, nicht
`ollama`. **Kein einziger Ollama-Lauf ist je erfolgreich gewesen.** Damit gilt die
Auffangregel: **alles selbst erledigen, Token-Ersparnis 0**, und der fehlende Nachweis
wird im Fazit benannt. Mit `pm/D014` = A ist entschieden, dass sich daran nichts ändert.

---

## Sprint-Abschluss (Sprint 33, 2026-08-21)

**Geschlossen:** `platform/T-0058` (**SWR-204**), `platform/T-0054` (**SWR-205**),
`platform/T-0057` (**SWR-206**). **Verschoben:** sieben — Grund unten, jeder im Ticket.

**Neue Anforderungen:** **SWR-204** (eine Sperre muss auf ein nicht geschlossenes Ticket
zeigen; Ausnahmen namentlich **und** mit Verfallsprüfung), **SWR-205** (der Endzustand hat
EINEN Namen, `board.STATUS_FINAL`; drei Fundstellen beurteilt und bewusst nicht
angeschlossen), **SWR-206** (EINE Brief-Discovery und EINE Auslegung von „offen"; die
Kennzahl `briefe_im_lauf` als Aussage über das **Fenster**).

**Neu angelegt:** `platform/T-0060` (Ollama: ein echter Lauf, aus `pm/D029`),
`platform/T-0061` (84 von 119 Lehren stehen in keinem Lehrbuch), `platform/T-0062` (SWR-203 nimmt seine Wurzel aus dem eigenen Dateipfad), `pm/T-0083`
(Projektgründung `team-termine` — **war in Sprint 32 zugesagt und nie angelegt**),
`pm/T-0084` (Inbox-DR, im Lauf beantwortet).

---

### ⚠⚠ Der Ertrag dieses Sprints ist wieder das REVIEW — und diesmal hat es eine ANFORDERUNG umgedreht

Drei Tickets waren gebaut, zugesichert und auf `in_review` gesetzt. Das unabhängige
Gegenlesen hat darin **drei ernste Fehler** gefunden. Keinen davon hat der Autor gefunden,
keinen eine der eigenen Zusicherungen.

**1. Der teuerste: ein Zeitzonenfehler, der eine Anforderung mit einer falschen Aussage gefüllt hat.**
`briefe_im_lauf` verglich den Brief-Zeitstempel (**UTC**, `+00:00`) mit dem Sprintstart
(**Wanduhrzeit**, CEST) und warf den Offset mit `.replace(tzinfo=None)` weg statt
umzurechnen.

> **⚠⚠ Zwei Stunden Versatz — länger als ein ganzer Sprint. Die Kennzahl hätte bei
> Sprintlängen von ein bis zwei Stunden IMMER 0 gemeldet: eine Größe, die den Satz
> „keiner eingegangen" verhindern sollte, hätte ihn maschinell erzeugt.**

Und sie hatte bereits Schaden angerichtet, bevor jemand sie prüfte: der Bau hatte damit
das **Ursprungsticket „korrigiert"** — die sieben Briefe seien während Sprint 31 gekommen —
und diese Behauptung stand in **`SWR-206`**, im Ticket und in einer **eingefrorenen
Regressionsschranke**. Richtig ist: die Briefe tragen **08:32–09:03 Ortszeit** und kamen
während **Sprint 32** (08:13–10:03). `platform/T-0057` hatte die ganze Zeit recht.

> **Eine Zeitzone ist keine Formatfrage, sondern eine Maßeinheit. Und eine falsche
> Messung, die eine KORREKTUR behauptet, ist teurer als gar keine — sie überschreibt die
> richtige Aussage und begründet das auch noch.**

⚠ Nachgemessen in Ortszeit: **17 von 21** Briefen seit Registerbeginn (**81 %**) kamen,
während ein Sprint lief. Die Kernaussage von `SWR-206` wird dadurch **stärker**, nicht
schwächer — nur ihr Beleg saß im falschen Sprint.

**2. Ein fünfter Name, den die eigene Zusicherung strukturell nicht sehen konnte.**
`SWR-205` zählte vier Namen für den Endzustand. Es sind **fünf** — `board.GESCHLOSSEN`
stand im selben Modul, in dem die Menge wohnt.

> **⚠⚠ Die Zusicherung nahm `board.py` PAUSCHAL aus. Eine Ausnahme für eine ganze Datei
> ist keine Ausnahme, sondern ein blinder Fleck — und er saß an der teuersten Stelle.**
> Jetzt ist genau **eine Zuweisungszeile** ausgenommen.

**3. Eine Ausnahmeliste ohne Verfallsprüfung — und sie ist noch im selben Lauf abgelaufen.**
`TOTE_SPERREN_BESTAND` nahm vier Verweise namentlich aus, bis der Auftraggeber `pm/T-0084`
beantwortet. Er hat **vier Stunden später** geantwortet (`pm/D029` = C) — und **nichts**
hätte gemeldet, dass die Ausnahme ihren Grund verloren hat.

> **Eine Ausnahme ohne Verfallsprüfung ist ein Dauerbefund mit umgekehrtem Vorzeichen:
> sie meldet nicht zu viel, sondern für immer zu wenig.**

⚠ Dazu drei kleinere, ebenfalls vom Review: eine Zusicherung war **durch ihren eigenen
Docstring** erfüllt (Anwesenheit statt Verwendung), eine war **vakuum-grün** (`[] == []`,
mit `except Exception` als Schlucker), und `SWR-206` hatte die **Discovery** vereinheitlicht
und die **Auslegung** von „offen" doppelt gelassen — dieselbe Fehlerfamilie, eine Ebene
tiefer, im selben Sprint, der sie schloss.

---

### ⚠⚠ Die Zählungen haben BEIDE Tickets umgestellt — schon wieder

| Ticket | nahm an | gemessen |
|---|---|---|
| `T-0058` | 3 Tickets in der Lage, „brauchen wir einen vierten Zustand?" | **8** Verweise in **5** Tickets — und **kein einziger** `blocked_by` des Hauses zeigte auf ein **offenes** Ticket, obwohl `SWR-193` genau das verlangt |
| `T-0054` | 3 Namen, 6 Literale, „kein Schaden" | **5** Namen, **7** Literale — und ein echter Schaden (`offene_blocker` mit `!= "done"`) |

> **⚠⚠ Der Befund von `T-0058` war nicht „uns fehlt ein Zustand", sondern „eine Sperre
> wird nie zurückgenommen, weil nichts danach fragt". Vier der acht Verweise waren
> Altpapier.**

Der vierte Ticket-Zustand ist deshalb **verworfen** — gemessener Preis: 9 Quelldateien,
153 Zustands-Literale, für eine Lage, die in 386 Tickets **einmal** vorkam. Gebaut ist die
fehlende **Prüfung**: Preis null neue Wörter, Wirkung 4 Befunde → 0.

> **Und die Entscheidung ist nachträglich gemessen: die Ausnahmeliste war nach vier
> Stunden leer. Ein vierter Zustand wäre für immer geblieben.**

---

### ⚠ Zwei Dinge, die dieser Sprint gefunden und NICHT repariert hat (Kap. 16)

**`platform/T-0061` — 84 von 119 Lehren stehen in keinem Lehrbuch.** Eine rote Zusicherung
meldete „71 gewonnene Vertreter". Nachgemessen ist es das Gegenteil: die 71 sind nie in der
Grundmenge gewesen. Die Kennzahl „Lehren: 121" zählt **Zitate im ganzen Haus**, die Prüfung
„ohne Vertreter" zählt **Köpfe im Lehrbuch** — zwei Zahlen unter einem Namen.

> **Eine Lehre, die nur im Abschlussbericht steht, ist eine Erinnerung an einen Sprint.
> Erst im Lehrbuch ist sie eine Regel für den nächsten.**

⚠ `OHNE_VERTRETER_BASIS` auf den heutigen Stand zu setzen hätte die Zusicherung in einer
Minute grün gemacht — **und den Befund gelöscht**. Sie bleibt rot.

**`platform/T-0060` — unsere Ollama-Diagnose war fünf Sprints alt.** Plan und Bericht
zitierten *„11 × Fehler, `model 'llama3.1:8b' not found`"* als **aktuellen** Zustand.
Gemessen liegen **alle 11** vor der Reparatur vom 20.08. 20:45, seither gab es **keinen
einzigen Versuch**, und der eine erfolgreiche Ollama-Lauf des Hauses (06.08.) trug
**`gemma3:27b`** — genau das, was der Auftraggeber in `pm/D029` geschrieben hat.

> **Eine Fehlerliste ohne Zeitachse ist keine Diagnose, sondern ein Archiv, das sich wie
> ein Befund liest.**

---

### Verschoben: sieben — mit Grund, neuem Termin und ohne Floskel

`platform/T-0055`, `platform/T-0056`, `pm/T-0080`, `pm/T-0082`, `pm/T-0083`,
`team-dashboard/T-0004`, `team-dashboard/T-0005`, `team-mail/T-0006` → **Sprint 34**,
Grund **im jeweiligen Ticket**: die Reparatur der drei eigenen Fehler und die zwei daraus
entstandenen Befunde haben den Rest des Laufs gekostet.

> **Eigene Fehler zu reparieren geht vor neuer Arbeit. Ein Sprint, der beides gleichzeitig
> versucht, liefert zwei halbe Sachen und einen Bericht, der beide für ganz erklärt.**

⚠ Alle sind **erste** Verschiebungen — die Regel der vierten Berührung ist nicht berührt.

---

### ⚠⚠ NACHTRAG: die Pflicht-Nachmessung am Ende hat einen Fehler in der Kennzahl gefunden, die sie ermöglicht

Die Briefkasten-Nachmessung am Sprint-Ende (`L-2026-08-21cs`) hat **0 offene Briefe** und
**0 während des Laufs eingegangene** bestätigt — und dabei einen Fehler in `briefe_im_lauf`
selbst aufgedeckt: **sobald der Sprint beendet war, meldete die Größe 14 statt 0.**

`_sprint_start` nahm den höchstnummerierten Sprint **ohne** `ende`. **15 von 33** Sprints
haben nie eine Endezeile bekommen — abgebrochene Läufe. Solange Sprint 33 lief, war die
Antwort richtig; danach fiel sie auf ein altes, offen gebliebenes Fenster zurück.

> **⚠⚠ „Kein Ende" heißt abgebrochen und nicht aktiv. Eine Funktion, die nur solange
> richtig antwortet, wie der Normalfall gilt, ist im Ausnahmefall nicht ungenau — sie ist
> beliebig. Und der Ausnahmefall war hier die Mehrheit.**

⚠ `sprint_register` führt für genau diese Lage ein eigenes Merkmal (`abgebrochen`), und der
neue Leser hat es nicht übernommen — dieselbe Familie wie `SWR-198`. Repariert, mit
Zusicherung; `L-2026-08-21da`.

**Damit sind es vier eigene Fehler in diesem Lauf, gefunden von drei verschiedenen
Stellen** — drei vom unabhängigen Gegenlesen, einer von der Pflicht-Nachmessung am Ende.
**Keinen hat der Autor beim Bauen gefunden.**

---

## Verifikation (Sprint 33)

| Größe | Wert |
|---|---|
| Anforderungen / Lücken | **206** SWRs (v1.91) / **0** |
| Tests / Testdateien | **1480** / **101** |
| Briefkasten | **0 offen** — am **Ende** gemessen |
| `briefe_im_lauf` | **0** (neu; über beide Ebenen, in Ortszeit gerechnet) |
| Offene Tickets | **19** |
| Auf den Menschen wartend | **0** — ⚠ `pm/T-0084` wurde **im Lauf** beantwortet |
| Tote Sperren (`SWR-204`) | **0**, Ausnahmeliste **leer** |
| Lehren / ohne Vertreter | **35** / **20** — ⚠ und diese Zahl ist Gegenstand von `T-0061` |

⚠ **Rot und benannt statt repariert (Kap. 16):**

* `test_lehren_vertreter::test_ein_gewonnener_vertreter_wird_gebucht_und_nicht_nebenbei_getan`
  → **`platform/T-0061`** (84 von 119 Lehren stehen in keinem Lehrbuch).
* **sieben** Zusicherungen in `test_backend` → **`platform/T-0062`**. Gemessen ist die
  Ursache eine **Zeile**: `inbox._naechste_d_id` leitet seine Wurzel aus dem **Dateipfad
  des eigenen Moduls** ab statt vom Aufrufer.
  > **⚠⚠ Eine Funktion, die „die ganze Organisation" liest, bestimmt damit selbst, welche
  > Organisation gemeint ist — und die Antwort ist immer: die, in der der Quelltext
  > zufällig liegt. Der ausdrücklich vorgesehene Rückfall („bei unbekannter Wurzel das
  > einzelne Log", `SWR-193`-Auflage) kann nie greifen: die Wurzel ist nie unbekannt,
  > sie wird erfunden.**
  ⚠ Sie sind seit **Sprint 32** rot, und dessen Abschluss meldete *„alle 98 übrigen
  Testmodule sind einzeln gelaufen"*. Diese Aussage war zu großzügig.

⚠ **Nicht vollständig gefahren, und das ist eine Aussage über die Menge, die NICHT geprüft
wurde (`SWR-189`):** `preflight.py` überschreitet in dieser Sandbox das Zeitlimit (178 s)
und ist **nicht durchgelaufen**. Einzeln nachgewiesen sind stattdessen: `board.py --check`
über **alle 18** Einheiten grün, `trace_matrix` 206/0, `organigramm.py --check` grün (20
Dateien), und **413 Tests** in 26 gezielt ausgewählten Modulen. Die übrigen Module sind
**nicht** gelaufen — „nicht betroffen" wäre eine Behauptung und kein Messergebnis.

⚠⚠ **Ollama-Offload: nichts delegiert, Token-Ersparnis 0 — gemessen, nicht geschätzt.**
`pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt. **Neu gemessen und
gegen den Plan dieses Laufs korrigiert:** die Fehlschläge liegen alle **vor** der Reparatur
vom 20.08., seither gab es keinen Versuch — der fehlende Nachweis ist also **kein**
Modellproblem mehr, sondern ein fehlender Lauf (`platform/T-0060`, Sprint 34, braucht den
Team-Node).

---

<details><summary>Archiv: Sprint 32</summary>

## Sprint-Plan (Sprint 32) — Planung VOR der Arbeit

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`). Gesichtet: **alle** Tickets **aller**
17 entdeckten Repos; nicht geschlossen sind **12** (`SWR-113`-Zählweise) bzw. **9**
(`kennzahlen.py`-Zählweise) — die Differenz sind die 3 gesperrten, siehe `T-0053`.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 32 | **erfüllt** | ⚠⚠ **0 offen beim Start — und 7 offen beim Abschluss.** Alle sieben kamen **während** des Laufs (06:32–07:03), alle vom Auftraggeber. Alle sieben **in diesem Sprint beantwortet und qualifiziert**; 2 davon als Klasse-A-Entscheidungsanfrage. |
| **platform/T-0052** | dev | Sprint 32 | **erledigt** | ⚠⚠ **Erste Terminierung**, prio **hoch**. Aus Sprint 31 als nullte Terminierung angelegt, hier **wie angekündigt** eingeplant. Vorabmessung zuerst (DoD-Punkt 1: Fensterlänge über ≥ 2 Sprints). |
| **platform/T-0053** | cm | Sprint 32 | **erledigt** | ⚠ **Erste Terminierung**. Vorabzählung zuerst (DoD: Leser von `tickets_offen` zählen, nicht schätzen). |
| promt-team/T-0003 | dev | — | **blocked** | ⚠ `blocked_by: [pm/T-0077]`, unverändert. Keine Terminierung — seit `SWR-198` erzeugt das keinen Befund mehr. |
| promt-team/T-0012 | prompt-opt | — | **blocked** | ⚠ dito (`blocked_by: [T-0001, T-0002, pm/T-0077]`). |
| pm/T-0071 | pl | — | **blocked** | ⚠ `blocked_by: [T-0077]`. Der Ollama-Offload-Nachweis fehlt weiterhin (Ticks nur `status: fehler`) — siehe Abschluss. |
| **pm/T-0077** | mensch | — | **erledigt** | ✅⚠⚠ **WÄHREND des Laufs entschieden: `D014` = A**, um 08:27 — **sieben Minuten** nach dem vorigen Brief, bei einer Frist von sieben Tagen. Verbucht. |
| **p13/T-0001** | mensch | — | **erledigt** | ⚠⚠ **In der Planung ÜBERSEHEN** (Handlauf sichtete nur `*/tickets/`) und ebenfalls während des Laufs entschieden: `D000` = **G0a**, Projektauftrag p13 freigegeben. Verbucht; Sprint-0-Planung als `pm/T-0082`. |
| pm/T-0001, pm/T-0002, pm/T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | geplant | Takt-Dauerläufer: Agenda + Intake + Lessons + Werkzeugpflege + Widget-Vertrag + Digest. |

**Verschoben: nichts.** Die 3 gesperrten Tickets sind **nicht verschoben**, sondern
`blocked` mit `blocked_by` — der Unterschied ist seit `SWR-193` ausdrückbar.

---

## ⚠⚠ NACHTRAG: sieben Briefe kamen WÄHREND des Laufs — und der Briefkasten stand schon auf „erfüllt"

Beim Start dieses Sprints waren **0** Briefe offen; das ist gemessen und war richtig. Beim
Zusammenstellen der Abschlusszahlen meldete `kennzahlen.py` **7**. Alle sieben tragen
Eingangszeiten zwischen **06:32 und 07:03** — sie sind **nach** dem Briefkasten-Durchgang
eingegangen.

> **⚠⚠ „Briefkasten zuerst" ist eine Reihenfolge und keine Zusicherung. Ein Durchgang am
> Anfang beantwortet die Briefe, die am Anfang da sind — und sagt nichts über die, die
> während der Arbeit ankommen. Der Haken hinter „erfüllt" war zum Zeitpunkt des Setzens
> wahr und zwei Stunden später falsch.**

Das ist derselbe Vorgang, den die Historie schon zweimal notiert hat (*„zum zweiten Mal in
vier Tagen wird etwas, das nach dem Bericht eintrifft, zum Altbestand des nächsten
Laufs"*) — hier zum **dritten** Mal, und diesmal mit sieben Briefen auf einmal.

⚠ **Gefunden hat es nicht der Briefkasten-Schritt, sondern der Kennzahlenlauf am Ende.**
Und er hat es nur gefunden, weil `zaehle_briefkasten` **weiter greift** als der Blick
dieses Laufs: es liest zusätzlich `*/*/management/briefkasten/` (die verschachtelten
Repos). Der erste Durchgang dieses Laufs hat nur die oberste Ebene abgesucht.

> **Zwei Discovery-Wege mit verschieden weiten Grundmengen — dieselbe Familie wie der
> Nebenbefund aus `SWR-198`. Dort lieferten beide zufällig dieselben 17 Einheiten; hier
> war der engere Weg der, den ein Mensch von Hand gegangen ist.**

**Alle sieben sind in diesem Sprint beantwortet, qualifiziert und committet.** Verschoben
ist die **Umsetzung**, nicht die Antwort — Grund: Ankunft nach dem Arbeitsdurchgang, nicht
Kapazität. Aufgeschrieben als `L-2026-08-21cs`; der Vertreter dafür ist `platform/T-0057`.

| Brief | Qualifiziert als | Termin |
|---|---|---|
| `platform/N-0008` Skript-Wächter | `platform/T-0055` (problem, hoch) | Sprint 33 |
| `platform/N-0009` Baselines | `platform/T-0056` (problem, mittel) | Sprint 33 |
| `pm/N-0044` Projekt `team-termine` | **`pm/T-0078` (decision-request)** — Klasse A: Gründung **und** Schreibrecht auf fremdes Konto | Frist 28.08. |
| `pm/N-0045` Core-Rollen gleich besetzen | `pm/T-0079` (problem, **blocked** by `T-0077`) | kein Termin |
| `pm/N-0046` Arbeitsverlauf je Aufgabe | `pm/T-0080` (cr, hoch) — **zerlegt**, nur Schritt 1 terminiert | Sprint 33 |
| `team-dashboard/N-0003` Gesamt-Widget | `team-dashboard/T-0004` (cr, mittel) | Sprint 33 |
| `team-mail/N-0005` Digest-Versand | **`pm/T-0081` (decision-request)** + `team-mail/T-0006` (**blocked**) | Frist 28.08. |

---


## ⚠⚠ NACHTRAG 2: der Auftraggeber hat WÄHREND des Laufs BEIDE offenen Entscheidungen beantwortet

Beim Start dieses Sprints stand `pm/T-0077` als einzige Sache beim Menschen, Frist 28.08.
Beim Abschluss meldete das Werkzeug **zwei entschiedene, unverbuchte** Entscheidungsanfragen:

| DR | Entscheidung | Zeit | Bedeutung |
|---|---|---|---|
| `pm/T-0077` | **`D014` = A** | 08:27 | „alles bleibt" — **kein** Arbeitsvorrat für den Ollama-Takt |
| `p13/T-0001` | **`D000` = G0a** | 08:56 | Projektauftrag p13 „Produkt-Architekturbilder" **freigegeben** |

> **⚠⚠ `T-0077` stand VIER SPRINTS lang in einer Empfehlungsliste und wurde nicht
> beantwortet. Als es zum ersten Mal als Frage mit Optionen, Frist und Voreinstellung
> dastand, war es in SIEBEN MINUTEN entschieden — bei sieben Tagen Frist.**
> Das ist die dritte Messung derselben Sorte in diesem Haus. **Fragen ist billiger als
> Ausweichen, und der Preis des Ausweichens wird nicht vom Fragenden bezahlt.**

**Beide sind in diesem Lauf verbucht.** ⚠ `p13/T-0001` war der Planung dieses Sprints
**entgangen** — derselbe zu enge Handlauf wie beim Briefkasten (`*/tickets/` statt
zusätzlich `projects/*/tickets/`), **im selben Lauf ein zweites Mal**. Auch das gehört zu
`L-2026-08-21cs`.

### ⚠⚠ Und Option A hat eine Lage erzeugt, die das Ticket nicht vorhergesehen hat

`blocked_by: [T-0077]` zeigt an **drei** Tickets jetzt auf ein **geschlossenes** Ticket.

> **Eine Sperre, die auf eine getroffene Entscheidung verweist, ist keine Sperre mehr —
> aber der Zustand, der sie begründet hat, besteht unverändert fort. Option A hat den
> Grund nicht beseitigt, sondern BESTÄTIGT.**

Für diese Lage gibt es **keinen zulässigen Zustand**: `blocked` verlangt einen offenen
Verweis, ein Termin wäre eine Zusage ohne Arbeitsvorrat, und `done` wäre **Option C** —
die der Auftraggeber gerade **nicht** gewählt hat. **Zum dritten Mal in drei Sprints liegt
der Fehler zwischen zwei richtigen Regeln** (`SWR-198`, `SWR-201`, jetzt hier).
Aufgeschrieben als `platform/T-0058`, prio hoch — **nicht** mit einem bequemen Statuswort
geglättet.

---

## Sprint-Abschluss (Sprint 32, 2026-08-21)

**Geschlossen:** `platform/T-0052` (**SWR-201**), `platform/T-0053` (**SWR-202**).
**Nichts aus dem Plan verschoben.**

**Neue Anforderungen:** **SWR-201** (der Plannachlauf des laufenden Sprints ist ein
benannter Nicht-Befund, gebunden an Richtung + `done` + Zugehörigkeit der Planzeile),
**SWR-202** („offenes Ticket" hat eine Zählweise über alle Erzeuger, und `SWR-113` hat
endlich einen Vertreter).

**Neu angelegt:** `platform/T-0054` (Endzustände 6× als Literal, 3 Namen),
`platform/T-0055`, `platform/T-0056`, `platform/T-0057`, `pm/T-0078`–`T-0081`,
`team-dashboard/T-0004`, `team-mail/T-0006` — **neun davon aus den sieben Briefen**,
eines aus einer Messung beim Bau.

### ⚠⚠ Vier eigene Fehler, alle vom unabhängigen Review gefunden — Schwere *hoch*

**Das Review ist der Ertrag dieses Sprints, nicht der Bau.** `SWR-201` war in der ersten
Fassung **kaputt**, und zwar auf eine Art, die alle sechs eigenen Zusicherungen grün
gelassen hat:

1. **Die Ausnahme war an „ein Sprint läuft" gebunden, nicht an „diese Planzeile gehört zu
   ihm".** Während gearbeitet wird, läuft aber **immer** einer — eine Planzeile aus
   Sprint 7 wäre mit unterdrückt worden.
   > **Eine Bedingung, die während der gesamten Arbeitszeit wahr ist, ist keine Bedingung
   > — sie ist ein offenes Tor mit einer Aufschrift.**
   ⚠ Damit war der DoD-Punkt „Wirkung für vergangene Sprints unverändert" **verletzt**,
   während die Anforderung ihn wörtlich behauptete.
2. **Ein Schlupfloch über `rejected`:** `TICKET_GESCHLOSSEN` enthält `done` **und**
   `rejected`. Eine Session hätte einen unbequemen Befund loswerden können, indem sie das
   Ticket **verwirft**.
3. **Die Verdrahtung war von keiner Zusicherung gedeckt.** Das Review hat Aufruf und
   Payload-Schlüssel **entfernt** — alle sechs Zusicherungen blieben grün, der Preflight
   meldete still „0", weil ein Vorgabewert den fehlenden Schlüssel in eine leere Liste
   verwandelte.
   > **Ein Vorgabewert verwandelt eine fehlende Antwort in eine beruhigende.**
4. **Beide Anforderungen standen auf `reviewed`, bevor das Review lief** — vom Autor
   gesetzt.

### ⚠ Zwei Prüfer, die den Fehler hatten, den sie prüfen

* Die Zitat-Zusicherung von `SWR-202` prüfte **Anwesenheit** statt Verwendung und blieb
  grün, während `aggregation.uebersicht` drei Zeilen darüber das Literal benutzte.
* Zwei Prüfungen schlugen gegen ihre **eigene Erklärung** an: die eine fand die schlechte
  Schreibweise im Docstring, wo sie als abschreckendes Beispiel zitiert steht; die andere
  las den Funktionsrumpf bis zum nächsten `def` und verschluckte die Konstante dahinter.
  > **Eine Zerlegung, die über ihren Gegenstand hinausläuft, misst den Nachbarn mit.**

### ⚠ Und ein Fehler in eigener Sache, den niemand gemeldet hat

Die beiden Tickets standen bis kurz vor dem Schließen auf `open` und sind erst **nach**
der Arbeit auf `in_progress` gesetzt worden. Das ist wörtlich der Vorgang, den `SWR-155`
gemessen hat (Median-Lebensdauer 22 Sekunden) und den die Rollenkarte PL als **Lehre 1**
führt. **Die Prüfung war grün, weil sie die Reihenfolge nicht kennt — nur das Vorkommen.**

## ⚠⚠ NACHTRAG 3: zwei weitere eigene Fehler, beide von fremden Zusicherungen gefunden

### 1. Wir haben `D014`–`D016` doppelt vergeben — und `SWR-197` war genau dagegen gebaut

Als der Auftraggeber seine drei Entscheidungen traf, vergab `inbox._naechste_d_id`
`D014`, `D015`, `D016` in `pm` — IDs, die `p0` seit dem **06.08.** trägt. Die mehrdeutige
Menge wuchs **an einem Tag von 14 auf 17**.

> **⚠⚠ `SWR-197` (Sprint 30) hat gemessen, dass alle mehrdeutigen Zitate aus `D000`–`D013`
> stammen, und geschrieben, die Sperrklinke sei „an der Vergabe" gebaut. Sie war es nicht:
> `_naechste_d_id` bildete `max + 1` über EIN Log. Die ersten drei Vergaben nach der
> Sperrklinke haben sie gebrochen.**
>
> **Eine Prüfung, die neben der Vergabe steht und sie nicht anfasst, ist kein Riegel,
> sondern ein Zeuge.**

**`SWR-203`**: die Vergabe liest ab jetzt **alle** Entscheidungslogs der Organisation.
⚠ Der Altbestand ist ehrlich auf **17** fortgeschrieben — **aber ausdrücklich nur
zusammen mit der Reparatur**. Ihn allein zu erweitern wäre die bequeme Handlung gewesen.
`platform/T-0059`, `L-2026-08-21cu`.

### 2. Wir haben viermal `open -> done` committet — im selben Lauf, in dem wir darüber schrieben

`test_uebergang_historie` (Sprint 23) meldete **vier** unzulässige Übergänge:
`platform/T-0052`, `T-0053`, `pm/T-0077`, `p13/T-0001`. Wir hatten `in_progress` gesetzt —
aber erst am Ende, und zusammen mit `done` committet. **Die Prüfung liest Commits, nicht
Arbeitsspeicher.**

> **⚠⚠ Der Abschluss dieses Laufs BESCHREIBT den Fehler zwei Absätze weiter oben („die
> Tickets standen bis kurz vor dem Schließen auf `open`") — und hat ihn im selben Atemzug
> BEGANGEN. Ein Fehler, den man aufschreibt, ist damit nicht behoben; er ist nur belegt.**

⚠ Nicht repariert (Kap. 16): die vier stehen ab jetzt **namentlich** in der Liste der
fortgeschriebenen Übergänge, die damit von **4 auf 8** wächst — **die Hälfte davon gehört
diesem Lauf.** Rollenkarte PL Lehre 1 ist um das Wort **committet** ergänzt; sie stand
dort bereits und hat nicht getragen. `L-2026-08-21cv`.

### ⚠ Und ein achter Brief kam nach dem Preflight

`team-dashboard/N-0004` (08:07, Post-Widget nach Design-Vorlage) — **beantwortet und als
`team-dashboard/T-0005` qualifiziert.** Die Vorlage
(`projects/p11/design/widget_design_mail.png`) ist gelesen und ihre **Lesart als Tabelle
im Ticket festgehalten**: ein Bild ist keine Zusicherung.

**Damit sind es acht Briefe in einem Lauf**, alle beantwortet — und `L-2026-08-21cs` hat
seinen dritten Beleg am selben Tag.

## Verifikation (Sprint 32, gemessen 10:03)

| Größe | Wert |
|---|---|
| `PREFLIGHT` | **STARTKLAR** (8 fortgeschrieben) |
| Anforderungen / Lücken | **202** SWRs (v1.88) / **0** |
| Tests / Testdateien | **1452** / **99** |
| Organigramm | grün, **20** Dateien |
| Briefkasten | **0 offen** — ⚠ am **Ende** gemessen (8 im Lauf eingegangen und beantwortet) |
| Workflows / unabgedeckte Takte | **6** / **0** |
| Work Products / Lücken | **56** / **0** |
| Lehren / ohne Vertreter | **121** / **91** (unverändert — alle **sechs** neuen haben einen) |
| Offene Tickets | **19**, einstimmig über alle drei Erzeuger (`SWR-202`) |
| Auf den Menschen wartend | **0** — ⚠ **alle drei DRs wurden im Lauf beantwortet** |
| Parkplatz | **11714** (Stand 10:07 — die Zahl trägt ihren Zeitpunkt, `SWR-174`) |

⚠ **Nicht gefahren, und das ist eine Aussage über die Menge, die wir NICHT geprüft haben
(`SWR-189`):** `test_js_teststrecke` überschreitet in dieser Sandbox das Zeitlimit. **Es
ist in diesem Lauf kein JavaScript geändert worden**, aber „nicht betroffen" ist eine
Behauptung und kein Messergebnis. Alle **98** übrigen Testmodule sind einzeln gelaufen.

⚠ **Ollama-Offload: nichts delegiert, Token-Ersparnis 0 — gemessen, nicht geschätzt.**
`pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt; die Run-Registry
zeigt ausschließlich `status: fehler` (`model 'llama3.1:8b' not found`). Mit `pm/D014` = A
ist entschieden, dass sich daran nichts ändert.

---

</details>

<details><summary>Archiv: Sprint 31</summary>

## Das Wichtigste (Sprint 31, 2026-08-21)

1. **✅ DREI TICKETS GESCHLOSSEN, NICHTS VERSCHOBEN — DARUNTER BEIDE NULLTEN
   TERMINIERUNGEN AUS SPRINT 30 UND DIE VIERTE BERÜHRUNG.**
   `platform/T-0051` (**SWR-198**), `platform/T-0050` (**SWR-199**), `platform/T-0049`
   (**SWR-200**, gebaut **und** geschnitten). Ein neues Ticket: `T-0052` — aus einer
   **Messung am laufenden Betrieb** entstanden, nicht aus einem Vorrat.
2. **⚠⚠ DER FEHLER LAG NICHT IN EINER PRÜFUNG, SONDERN ZWISCHEN ZWEIEN — UND DAS IST DER
   ROTE FADEN DIESES LAUFS.** Für ein **gesperrtes** Ticket gab es keinen zulässigen
   Terminwert: alter Sprint → Befund, leer → Befund, Zukunft → still, aber eine Zusage
   über fremdes Handeln.
   > **Eine Lage, in der die bequeme Handlung die einzige ist, die grün macht, ist genau
   > die Bauart, gegen die `SWR-166` gebaut wurde.**
   Die Ausnahme **gab es schon** — an einem **Typ** (`decision-request`) statt an einem
   **Zustand**, weil `blocked` erst seit `SWR-193` existiert, **einen Sprint alt**.
   > **⚠⚠ Ein Stellvertreter, der lange mit der Sache zusammenfiel, wird zum Loch in dem
   > Moment, in dem die Sache einen eigenen Namen bekommt.**
   `SWR-198`. **Am echten Bestand gemessen: `unterminierte_tickets` 3 → 0**, und der
   Schnelltakt des Auftraggebers meldet seitdem `[org] 0 Tickets ohne Sprint`.
3. **⚠⚠ ZUM VIERTEN MAL „ERST ZÄHLEN, DANN BAUEN" — UND ZUM VIERTEN MAL HAT DIE ZAHL DIE
   FRAGE VERÄNDERT.** `SWR-194` nannte seine Grundmenge die *„ehrliche Untermenge"*.
   Gemessen: **24 %** der 38 „Erkannten" haben einen Vertreter, **15 %** der 73
   „Übersehenen" — nahezu dasselbe.
   > **Die 34er-Menge war nie eine Auswahl von Lehren, die einen Vertreter BRAUCHEN. Sie
   > war eine Auswahl von Lehren, die jemand mit Doppelpunkt geschrieben hat.**
   ⚠ Und die zweite Messung hat die **Bauform** bestimmt: zwischen „Muster erweitern"
   (111 von 112) und „Filter weglassen" (112) liegen **null** Lehren — beide ergeben 91.
   **Von zwei gleichwertigen Bauformen ist die mit einem Begriff weniger die richtige.**
   `SWR-199`; der Ausstieg heißt jetzt `**Beobachtung:**` und ist eine **Handlung** statt
   eines Nebeneffekts der Zeichensetzung.
4. **⚠⚠ DIE VIERTE BERÜHRUNG HAT IHRE EIGENE VERMUTUNG WIDERLEGT.** Drei Sprints lang
   galt: *„es gibt einen zweiten SCHREIBWEG ins Entscheidungslog, und er hat keine
   Nummernvergabe."* Gemessen über 17 Logs und 158 Zeilen: **es gibt keine zweite
   Funktion.**
   > **Der zweite Schreibweg ist die HAND — und er ist nicht die Ausnahme, sondern die
   > MEHRHEIT: 103 von 158 Zeilen (65 %).**
   ⚠ Geschnitten ist die Nummernvergabe, und der Grund ist gemessen: der Schaden ist seit
   `SWR-195` (Sprint 29) und `SWR-197` (Sprint 30) bereits gefangen — von Tickets, die
   **nach** dieser Frage entstanden sind. **Die Frage hat ihre eigene Antwort überlebt.**
5. **⚠⚠ EINE ZUSICHERUNG AUS SPRINT 30 HAT DIESE SESSION AUFGEHALTEN — UND GENAU DAFÜR
   WAR SIE GEBAUT.** `test_termin_zange_blocked.py` sicherte den **Mangel** und trug den
   Auftrag *„wird mit T-0051 UMGEDREHT und nicht gelöscht"* in ihrem eigenen Docstring.
   Nach dem Bau von `SWR-198` wurde sie rot.
   > **Eine Zusicherung, die einen Mangel BENENNT statt ihn zu verschweigen, meldet seine
   > Behebung von allein. Wäre der Mangel nur in Prosa vermerkt gewesen, hätte die Datei
   > nach dem Fix schweigend weiter den alten Zustand beschrieben.**
   ⚠ **Und sie hat dabei einen zweiten, echten Fehler gefunden**, den keine neue
   Zusicherung dieses Laufs gesehen hätte: ihre Vorrichtung baut `blocked_by` als **echte
   Liste**, und `board.parse_liste` brach daran mit `AttributeError` — es kannte nur Text
   aus dem Frontmatter. **Eine Zerlegefunktion, die an ihrem eigenen Ergebnis scheitert,
   ist nicht idempotent.** `L-2026-08-21cp`.
6. **⚠⚠ DER SCHNELLTAKT LÄUFT — UND DIESE SESSION HAT IHN SELBST BLOCKIERT.** Um **06:15**
   meldete der Preflight zweimal `STARTKLAR`. Ab **06:30** bis **07:01**: dreimal
   `1 Befund`, **6 Ticks abgebrochen** — und der Befund war jedes Mal die Statusdrift, die
   **diese Session** erzeugt hat, indem sie ihre drei Tickets schloss.
   > **⚠⚠ Der Plan wird laut `pm/D006` am Sprint-ABSCHLUSS fortgeschrieben. Also ist der
   > Bestand während JEDES Sprints widersprüchlich — per Konstruktion —, und genau in
   > diesem Fenster kann der Schnelltakt nie laufen. Das Fenster ist kein Ausrutscher, es
   > ist die Dauer eines Sprints.**
   ⚠ Das stellt eine Aussage der Agenda richtig: `pm/T-0077` ist **nicht** die einzige
   Sperre vor dem Ollama-Offload. `platform/T-0052`, prio hoch. **Beide bisherigen
   Diagnosen waren für ihren Messzeitpunkt richtig** — gemessen wurde jeweils am *Ende*
   einer Session, wenn der Plan schon stand. **Eine Ursache, die nur am Ende eines Laufs
   gemessen wird, kann einen Zustand nicht sehen, der nur WÄHREND des Laufs besteht.**
7. **⚠ DER OLLAMA-OFFLOAD IST WEITERHIN NICHT DELEGIERT — mit einem dritten Grund.**
   `pm/T-0071` hat unverändert **keinen** Tick mit `status: ok` + Artefakt; der Nachweis
   fehlt und wird hier benannt statt übergangen. Neu ist, dass der Grund messbar **nicht
   allein** der leere Arbeitsvorrat ist (siehe 6).
   **Kein Ticket delegiert; Token-Ersparnis 0 — gemessen, nicht geschätzt.**
8. **1429 Python-Tests** über **95** Testdateien, Matrix **200 SWRs / 0 Lücken**,
   Briefkasten **0 offen / 0 eingegangen**, auf den Menschen wartend **1**
   (`pm/T-0077`, Frist 28.08.), Workflows **6 / 0 unabgedeckte Takte**,
   Work-Product-Lücken **0** (56 WPs), Lehren **115 / 91 ohne Vertreter** (= die benannte
   Basis), Parkplatz **11480** (Stand 07:10 — die Zahl trägt ihren Zeitpunkt, `SWR-174`).
   > ⚠ **Zwei unabhängige Messungen, deckungsgleich:** die Summe der Einzelläufe je
   > Testmodul ergibt **1429**; `kennzahlen.py` zählt **1429** über **95** Dateien.
   > Sprint 30 stand bei 1404/93; dieser Lauf hat **zwei** Dateien mit 15 + 5 = 20 und
   > eine bestehende um 5 ergänzt — 1404 + 25 = **1429**. Deckungsgleich.
   >
   > ⚠⚠ **Offene Tickets stehen hier mit ZWEI Zahlen und ihren Definitionen, weil die
   > Werkzeuge zwei geben:** **11** nach `SWR-113` (Status weder `done` noch `rejected`,
   > Takt-Dauerläufer eingeschlossen — die in Sprint 7 getroffene Festlegung) und **8**
   > nach `kennzahlen.py` (`status == "open"`). Die Differenz sind die **3 gesperrten**
   > Tickets. Eine der beiden still zu wählen wäre genau der Zustand, gegen den `SWR-113`
   > gebaut wurde. `platform/T-0053`.

## Sprint-Plan (Sprint 31)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 31 | **erfüllt** | ✅ **0 offen**, beim Start und beim Abschluss gemessen. Kein Brief eingegangen. |
| **platform/T-0051** | dev | Sprint 31 | **erledigt** | ✅ **SWR-198.** Nullte Terminierung aus Sprint 30, im Folgelauf gebaut wie angekündigt. Befunde **1 → 0** am echten Bestand gemessen. |
| **platform/T-0050** | coach | Sprint 31 | **erledigt** | ✅ **SWR-199.** Nullte Terminierung aus Sprint 30. Die Messung hat die Bauform bestimmt: Filter fällt, statt erweitert zu werden. |
| **platform/T-0049** | cm | Sprint 31 | **erledigt** | ✅ **SWR-200.** **Vierte Berührung — entschieden**, nicht terminiert: gebaut (Zusicherung über die Code-Wege) **und** geschnitten (keine Nummernvergabe für die Hand). |
| **platform/T-0052** | dev | Sprint 32 | offen | ⚠⚠ **Nullte Terminierung, prio hoch.** Am laufenden Schnelltakt gemessen: 6 abgebrochene Ticks in 46 Minuten, Ursache ist die Statusdrift **dieses** Sprints. Zwei richtige Regeln, dazwischen ein garantierter Zustand — dieselbe Familie wie `T-0051`. |
| **platform/T-0053** | cm | Sprint 32 | offen | ⚠ **Nullte Terminierung.** Beim Abgleich der Abschlusszahlen gefunden: zwei Werkzeuge zählen „offene Tickets" verschieden (**9** gegen **12**) — und `SWR-113` hat genau das vor **vier** Sprints entschieden. Die Festlegung stand in einem Docstring und in keiner Zusicherung. |
| promt-team/T-0003 | dev | — | **blocked** | ⚠ `blocked_by: [pm/T-0077]`, unverändert. Keine Terminierung — und ab `SWR-198` erzeugt das keinen Befund mehr. |
| promt-team/T-0012 | prompt-opt | — | **blocked** | ⚠ dito. |
| pm/T-0071 | pl | — | **blocked** | ⚠ `blocked_by: [T-0077]`. ⚠⚠ Der **Grund** ist um einen dritten ergänzt: nicht nur leerer Arbeitsvorrat, sondern auch das Drift-Fenster (`T-0052`). Die Sperre bleibt dieselbe. |
| **pm/T-0077** | mensch | Frist 28.08. | **wartet** | ⚠ Unverändert offen, Frist **nicht** erreicht (heute 21.08.). Default **A**, Schweigen genügt. |
| pm/T-0001, pm/T-0002, pm/T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**vier**, alle mit Vertreter) + Chronik in **vier** Einheiten + Verifikation. Workflow-Abdeckung **6/6, 0 Lücken**, WP-Lücken **0** — kein neues Takt-Ticket, also keine neue Workflow-Pflicht. |

## Sprint-Abschluss (Sprint 31, 2026-08-21)

**Geschlossen:** `platform/T-0051` (**SWR-198**), `platform/T-0050` (**SWR-199**),
`platform/T-0049` (**SWR-200**). **Nichts verschoben.**

**Neue Anforderungen:** **SWR-198** (Ausnahme am Zustand statt am Typ, gebunden an den
Verweis), **SWR-199** (Grundmenge der Lehren-Prüfung gemessen statt gesetzt), **SWR-200**
(benannte Menge der Code-Schreibwege ins Entscheidungslog, über den Syntaxbaum).

**Neu angelegt:** `platform/T-0052` (das Drift-Fenster des laufenden Sprints),
`platform/T-0053` (zwei Zählweisen für „offene Tickets").

### ⚠⚠ Drei eigene Fehler, alle von Werkzeugen oder Vorsprint-Zusicherungen gefunden

1. **Eine Zahl war falsch formuliert** — der erste Entwurf des `SWR-199`-Docstrings
   behauptete, der Regel-Filter entferne *„in jeder Schreibweise genau null"* Lehren.
   Richtig: das **Erweitern** entfernt nichts mehr, die **enge** Schreibweise entfernt 62.
   Aufgefallen, weil die eigene Zusicherung die Behauptung nicht hergab. **Korrigiert
   statt stehengelassen** (`L-2026-08-21cb`).
2. **Die Zusicherung zu `SWR-200` hat sich im ersten Entwurf selbst widerlegt** — sie fand
   `inbox.py` **nicht**, weil sie den Schreibmodus in *derselben Zeile* wie den Dateinamen
   suchte; `entscheide` legt den Pfad in `log_pfad` ab und öffnet drei Zeilen später.
   **Eine Textsuche über eine Zeile findet nur den Schreiber, der seinen Pfad nicht
   zwischenspeichert** — sie hätte genau den Hauptweg übersehen. Auf den Syntaxbaum
   umgestellt, **bevor** sie geglaubt wurde.
3. **⚠⚠ Zwei Werkzeuge zählen „offene Tickets" verschieden — und es war schon
   entschieden.** `sprint.kennzahlen` sagt **12** (Status weder `done` noch `rejected`,
   `SWR-113`), `kennzahlen.py` sagt **9** (`status == "open"`). Die Differenz sind die
   **3 gesperrten** Tickets. `SWR-113` ist in Sprint 7 **genau zu dieser Frage** gebaut
   worden — *„eine unwiderlegbare Kennzahl ist keine"* —, und das zwanzig Sprints später
   entstandene `kennzahlen.py` hat die Festlegung nicht übernommen.
   > **Die Festlegung stand in einem Docstring und in keiner Zusicherung. Das ist wörtlich
   > `SWR-125`: eine Entscheidung, die keine Prüfung mitgeändert hat, ist eine
   > Absichtserklärung.**
   ⚠ Beide Zahlen stehen **mit ihrer Definition** in Punkt 8 — keine wird stillschweigend
   gewählt. `platform/T-0053`.
4. **Eine neue Lehre stand kurzzeitig ohne Vertreter da** (`ohne_vertreter` 92 statt 91),
   und die Prüfung nannte sie beim Namen: ihr Vertreter lag in `test_lehren_vertreter.py`
   — der Datei, die aus dem Vertreter-Korpus **ausgeschlossen** ist.
   > **Eine Lehre, die BEI der Vertreter-Prüfung gelernt wird, kann ihren Vertreter nicht
   > IN ihr haben. Sie braucht eine zweite Stelle, an der dieselbe Regel wirklich trägt —
   > und wenn es keine gibt, ist die Regel noch keine.**

### ⚠ Ein fünfter Fund, beim Aufräumen der Arbeitskopien

Im Repo `projects` trug der **Git-Index** das **Löschen** einer Historienzeile
(`p11/docs/historie.md`, Sprint 28) — Arbeitsbaum und `HEAD` waren identisch und korrekt,
nur der Zwischenspeicher hielt eine Entfernung fest, die nie jemand committen wollte.

> **Ein gestagter Löschvorgang an einer Chronik ist Kap. 16 im Wartezustand: er wird zur
> umgeschriebenen Historie, sobald irgendjemand in diesem Repo ein `git commit -a` oder
> ein weites `git add` absetzt — und bis dahin meldet kein Werkzeug ihn als Befund.**

⚠ Dieselbe Familie wie `SWR-191` aus Sprint 29 (*die Prüfung las den Index und sprach über
den Baum*), nur andersherum: hier ist der **Baum** in Ordnung und der **Index** trägt den
Schaden. Zurückgenommen mit `git restore --staged`; Inhalt unangetastet, `HEAD`-Diff leer.
**Kein eigenes Ticket:** die Ursache (eine fremde/frühere Session, die stagte und nicht
committete) ist nicht mehr feststellbar, und ein Ticket ohne prüfbare Frage wäre ein
Vorrat. Der Fund steht hier, damit er beim nächsten Auftreten wiedererkannt wird.

**Auf `blocked` geblieben statt terminiert:** `promt-team/T-0003`, `promt-team/T-0012`,
`pm/T-0071` — alle `blocked_by: [pm/T-0077]`, Frist läuft. ⚠ Ab `SWR-198` ist das zum
ersten Mal **befundfrei** und nicht mehr die Wahl zwischen zwei Befunden.

**Lessons (vier, alle sofort verankert UND mit Vertreter):** `L-2026-08-21cm`
(Stellvertreter wird zum Loch, sobald die Sache einen Namen bekommt), `cn` (Verhältnis
gemeint, Ungleichung geschrieben), `co` (die Frage hat ihre Antwort überlebt), `cp`
(Zerlegefunktion nicht idempotent). **Verbleib:** `process/knowledge/dev/lessons.md`
(cm, cp), `.../coach/lessons.md` (cn), `.../cm/lessons.md` (co), Historie `platform`,
Vertreter in `test_gesperrt_terminzange.py`, `test_termin_zange_blocked.py`,
`test_entscheidungslog_schreibwege.py`.

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

* **Ob ein Ollama-Tick inhaltlich etwas Sinnvolles tut.** Unverändert: es ist nie einer
  gelaufen. Der Nachweis für `pm/T-0071` (`status: ok` + Artefakt) **fehlt** und wird hier
  benannt, damit er nicht später als erledigt gilt, weil ihm niemand widersprochen hat.
* **Die Länge des Drift-Fensters über mehrere Sprints.** Gemessen ist **ein** Sprint
  (46 Minuten, 6 abgebrochene Ticks). Ob das die Regel ist, ist die Frage von `T-0052` —
  und sie ist offen.
* **Ob die 91 Lehren ohne Vertreter einen brauchen.** `SWR-199` hat die Grundmenge
  gewechselt und den Bestand **benannt**; ob er schrumpfen soll, ist damit nicht
  entschieden.
* **Die volle Testsuite in EINEM Lauf.** Unverändert: ein Gesamtlauf läuft in ein
  Werkzeug-Zeitlimit. Gefahren modulweise; die Summe steht oben mit ihrer Herkunft und
  ist durch `kennzahlen.py` unabhängig bestätigt.
* **Ob `gemma3:27b` auf dem Rechner des Auftraggebers installiert ist.** Von hier aus
  nicht messbar (`L-2026-08-20ce`).

---

</details>

<details><summary>Archiv: Sprint 30</summary>

## Das Wichtigste (Sprint 30, 2026-08-21)

1. **✅ ZWEI TICKETS GESCHLOSSEN, NICHTS VERSCHOBEN — UND BEIDE WAREN NULLTE
   TERMINIERUNGEN AUS SPRINT 29, IM FOLGELAUF GEBAUT WIE ANGEKÜNDIGT.**
   `platform/T-0047` (**SWR-197**) und `platform/T-0048` (**SWR-196**). Drei neue Tickets
   angelegt: `T-0049`, `T-0050` — beide aus **Messungen** entstanden, nicht aus Vorräten.
2. **⚠⚠ DIE VORHERSAGE AUS SPRINT 29 IST EINGETRETEN UND IST JETZT EINE MESSUNG: DER
   SCHNELLTAKT BRICHT NICHT MEHR AB.** Um **04:15** — dem ersten Lauf nach dem Commit von
   `SWR-191` um 04:10 — steht im Log `PREFLIGHT: STARTKLAR` statt `Preflight hat Befunde`.
   Davor: **65** Abbrüche.
   > **⚠⚠ UND DAHINTER STAND EIN ZWEITER BLOCKER, DEN DER ERSTE VERDECKT HAT.** 2 von 2
   > Ticks endeten trotzdem ohne Ergebnis: `waehle_ticket` gab `kandidaten[0]` zurück und
   > prüfte die Besetzung erst **danach**.
   > **Eine Prüfung nach der Auswahl ist kein Filter, sondern ein Veto gegen genau einen
   > Kandidaten — die Zweitplatzierten werden nie angesehen.**
   `SWR-196`. Wirkung am echten Bestand gemessen (`--dry-run`), nicht versprochen.
3. **⚠⚠ UND DIE ALTE MELDUNG WAR WAHR UND ZU ENG — GENAU DAS IST TEUER.** *„Rolle CM hat
   … keine Besetzung … T-0001 bleibt unangetastet"* liest sich wie ein **Zufall**.
   Gemessen ist ein **Zustand**: **0 von 8** offenen Tickets der Organisation tragen eine
   ollama-besetzte Rolle (cm 2, pl 4, coach 1, dev 1; besetzt: `PROB@platform`,
   `MAIL-RED@team-mail`).
   > **Die enge Aussage lädt zum Wiederkommen in 15 Minuten ein — und der Takt hat das
   > 90-mal getan. Zwilling von `L-2026-08-21ce`: dasselbe Wegsehen mit besserem
   > Gewissen.**
   ⚠ Der Zustand war seit dem 20.08. gemessen — die Zahl stand im **Docstring einer
   Funktion**, nicht in der Meldung, die der Betrieb 90-mal gedruckt hat.
4. **✅ ZUM DRITTEN MAL „ERST ZÄHLEN, DANN BAUEN" — UND ZUM DRITTEN MAL HAT DIE ZAHL DIE
   FRAGE VERÄNDERT.** `T-0047`, Vorabfrage 1 ausgeführt: von **1023** praefixlosen
   Entscheidungs-Zitaten stehen **743 (73 %)** im besitzenden Repo, **65 (6 %)** nennen
   eine nur einmal vergebene ID, **214 (21 %)** sind echt mehrdeutig.
   > **⚠⚠ Und alle 214 nennen eine von VIERZEHN IDs — `D000` bis `D013`. Ab `D014` ist
   > jede ID organisationsweit einmal vergeben. Der Mangel ist ein PRÄFIX DES
   > NUMMERNRAUMS und keine Eigenschaft des Korpus.**
   Deshalb ist die Sperrklinke an der **Vergabe** gebaut und nicht an 1023 Zitatstellen.
5. **⚠⚠ DAS ARGUMENT GEGEN DEN GEPLANTEN ZUSCHNITT IST AN DIESER SESSION SELBST
   GEMESSEN.** Während des Baus stiegen die Zahlen von 1023/214 auf **1030/216** — allein
   dadurch, dass Ticket und Anforderung **über** das Problem schreiben und dabei IDs
   nennen.
   > **Eine Prüfung auf die Zitatzahl hätte jeden Bericht bestraft, der den Befund
   > erklärt: ein Dauerbefund, den das Erklären selbst füttert.**
6. **⚠⚠ DER UNANGENEHMSTE BEFUND DIESES LAUFS BETRIFFT DIE EIGENE PRÜFUNG AUS SPRINT 29.**
   `SWR-194` hätte **drei** Lehren dieses Laufs übersehen — sie standen als `**Regel.**`
   statt `**Regel:**`, und die Zählung blieb bei 34/29, als gäbe es sie nicht.
   > **Der Fehler ist nicht, dass drei durchgerutscht sind. Der Fehler ist, dass die
   > Prüfung dabei GRÜN geblieben ist. Eine Sperrklinke, die man mit einem anders
   > gesetzten Doppelpunkt umgeht, ist keine.**
   Gemessen: **34** von **111** Lehren tragen `**Regel:**`, **110** tragen irgendeine
   Regel-Schreibweise — **76 übersehen**. ⚠ Die *„gefundene, nicht erfundene"* Konvention
   unterscheidet **nichts**; die 34 sind eine Schreibweise. `platform/T-0050`.
   ⚠ Die drei Lehren sind nachgezogen und haben Vertreter bekommen — `ohne_vertreter`
   steht wieder bei **29**. Die Lücke bleibt und ist terminiert, nicht geschlossen.
7. **⚠ DER OLLAMA-OFFLOAD IST WEITERHIN NICHT DELEGIERT — ABER DER GRUND IST EIN NEUER.**
   `pm/T-0071` hat unverändert keinen Tick mit `status: ok` + Artefakt. Neu ist, **woran
   es liegt**: nicht mehr am Preflight, sondern am leeren Arbeitsvorrat.
   **Kein Ticket delegiert; Token-Ersparnis 0 — gemessen, nicht geschätzt.**
8. **1404 Python-Tests** über **93** Testdateien (**gemessen**, `kennzahlen.py` 05:06),
   Matrix **197 SWRs / 0 Lücken**,
   Briefkasten **0 offen / 0 eingegangen**, offene Tickets **10**, auf den Menschen
   wartend **1** (`pm/T-0077`, Frist 28.08.), Workflows **6 / 0 unabgedeckte Takte**,
   Work-Product-Lücken **0**, Parkplatz **11325** (Stand 05:06 — die Zahl trägt ihren
   Zeitpunkt, `SWR-174`).
   > ⚠ **Die Summe ist durch zwei unabhängige Messungen belegt:** `kennzahlen.py` zählt
   > **1404**; Sprint 29 stand bei **1367** über 90 Dateien, dieser Lauf hat **drei**
   > Dateien mit **11 + 21 + 5 = 37** Zusicherungen ergänzt — 1367 + 37 = **1404**.
   > **Deckungsgleich.**

## Sprint-Plan (Sprint 30)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 30 | **erfüllt** | ✅ **0 offen**, beim Start und beim Abschluss gemessen. Kein Brief eingegangen. |
| **platform/T-0048** | dev | Sprint 30 | **erledigt** | ✅ **SWR-196.** Aus der Messung des ersten startklaren Schnelltakt-Laufs entstanden und im selben Lauf geschlossen. |
| **platform/T-0047** | cm | Sprint 30 | **erledigt** | ✅ **SWR-197.** Nullte Terminierung aus Sprint 29, im Folgelauf gebaut wie angekündigt. |
| **platform/T-0049** | cm | Sprint 31 | offen | ⚠ **Dritte Berührung**, Zählung fortgeführt. Der zweite Schreibweg ins Entscheidungslog — er wäre mit `T-0047` untergegangen und bekommt deshalb einen eigenen Termin. **Bei der vierten wird entschieden, nicht terminiert.** |
| **platform/T-0050** | coach | Sprint 31 | offen | ⚠⚠ **Nullte Terminierung.** Die Lücke in `SWR-194`. Nicht in diesem Lauf gebaut, und der Grund steht im Ticket: die naheliegende Reparatur erzeugte ~100 Dauerbefunde und wäre `SWR-166` ein viertes Mal. **Erst messen, dann bauen.** |
| **platform/T-0051** | dev | Sprint 31 | offen | ⚠⚠ **Nullte Terminierung, prio hoch.** Beim Abschluss gefunden: für ein **gesperrtes** Ticket gibt es **keinen zulässigen Terminwert** — `sprint_vergangen` meldet den alten, `unterminierte_tickets` (`SWR-125`) den leeren, und still ist nur eine Zusage, die das Team nicht halten kann. |
| promt-team/T-0003 | dev | — | **blocked** | ⚠ `blocked_by: [pm/T-0077]`, unverändert. Keine Terminierung. |
| promt-team/T-0012 | prompt-opt | — | **blocked** | ⚠ dito. |
| pm/T-0071 | pl | — | **blocked** | ⚠ `blocked_by: [T-0077]`. ⚠⚠ Der **Grund** hat sich geändert: nicht mehr Preflight, sondern leerer Arbeitsvorrat (`SWR-196`). Die Sperre bleibt dieselbe. |
| **pm/T-0077** | mensch | Frist 28.08. | **wartet** | ⚠ Unverändert offen, Frist **nicht** erreicht (heute 21.08.). Default **A**, Schweigen genügt. |
| pm/T-0001, pm/T-0002, pm/T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**drei**, alle mit Vertreter) + Chronik in **vier** Einheiten + Verifikation. Workflow-Abdeckung **6/6, 0 Lücken**, WP-Lücken **0** — kein neues Takt-Ticket, also keine neue Workflow-Pflicht. |

## Sprint-Abschluss (Sprint 30, 2026-08-21)

**Geschlossen:** `platform/T-0047` (**SWR-197**), `platform/T-0048` (**SWR-196**).
**Nichts verschoben.**

**Neue Anforderungen:** **SWR-196** (Besetzung als Kandidatenfilter), **SWR-197**
(Sperrklinke am Nummernraum der Entscheidungs-IDs).

**Neu angelegt:** `platform/T-0049` (zweiter Schreibweg, dritte Berührung),
`platform/T-0050` (Schreibweise statt Konvention in `SWR-194`), `platform/T-0051` (die
Termin-Zange am gesperrten Ticket).

### ⚠⚠ Ein vierter Befund, gefunden beim Aufräumen — und die erste Diagnose war zu freundlich

Der Preflight meldete drei gesperrte Tickets als *„offen auf vergangenem Sprint"*. Der
Termin wurde geleert — **und der Befund war nicht weg, sondern umgezogen**: jetzt meldet
`unterminierte_tickets` *„Ticket ohne Sprint"*.

> **Für ein gesperrtes Ticket gibt es KEINEN zulässigen Terminwert. Der einzige Wert, der
> beide Prüfungen still hält, ist eine Terminzusage über fremdes Handeln — also die
> falsche Handlung.**

⚠ Beide Prüfungen sind einzeln richtig; der Fehler liegt **zwischen** ihnen. Die Ausnahme
steht an einem **Typ** (`decision-request`), wo sie einen **Zustand** meint — weil
`blocked` mit `blocked_by` erst seit `SWR-193` existiert, **einen Sprint alt**.
**Ein Stellvertreter, der lange mit der Sache zusammenfiel, wird zum Loch in dem Moment,
in dem die Sache einen eigenen Namen bekommt.**

⚠ **Das stellt Sprint 29 richtig:** der Termin ist dort nicht liegengeblieben — es gab
nichts Besseres. Zwilling von `L-2026-08-21cc`: dort fiel eine Begründung mit der einzigen
möglichen Handlung zusammen, **hier gibt es überhaupt keine.**

**Gewählt** ist der leere Termin: gleicher Preis (je ein Befund), aber die **wahre**
Aussage. `platform/T-0051`, prio hoch.

### ⚠ Ein fünfter Fund, beim Aufräumen der Arbeitskopien

Im Repo `projects` trug der **Git-Index** das **Löschen** einer Historienzeile
(`p11/docs/historie.md`, Sprint 28) — Arbeitsbaum und `HEAD` waren identisch und korrekt,
nur der Zwischenspeicher hielt eine Entfernung fest, die nie jemand committen wollte.

> **Ein gestagter Löschvorgang an einer Chronik ist Kap. 16 im Wartezustand: er wird zur
> umgeschriebenen Historie, sobald irgendjemand in diesem Repo ein `git commit -a` oder
> ein weites `git add` absetzt — und bis dahin meldet kein Werkzeug ihn als Befund.**

⚠ Dieselbe Familie wie `SWR-191` aus Sprint 29 (*die Prüfung las den Index und sprach über
den Baum*), nur andersherum: hier ist der **Baum** in Ordnung und der **Index** trägt den
Schaden. Zurückgenommen mit `git restore --staged`; Inhalt unangetastet, `HEAD`-Diff leer.
**Kein eigenes Ticket:** die Ursache (eine fremde/frühere Session, die stagte und nicht
committete) ist nicht mehr feststellbar, und ein Ticket ohne prüfbare Frage wäre ein
Vorrat. Der Fund steht hier, damit er beim nächsten Auftreten wiedererkannt wird.

**Auf `blocked` geblieben statt terminiert:** `promt-team/T-0003`, `promt-team/T-0012`,
`pm/T-0071` — alle `blocked_by: [pm/T-0077]`, Frist läuft.

**Lessons (drei, alle sofort verankert UND mit Vertreter):** `L-2026-08-21cj` (Prüfung
nach der Auswahl = Veto), `ck` (Präfix des Nummernraums), `cl` (wahre, aber zu enge
Meldung). **Verbleib:** `process/knowledge/dev/lessons.md`, `.../cm/lessons.md`, Historie
`platform` Lehren 18–21, Vertreter in `test_tick_besetzungsfilter.py` und
`test_entscheidungs_ids.py`.

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

* **Ob ein Ollama-Tick inhaltlich etwas Sinnvolles tut.** Unverändert: es ist nie einer
  gelaufen. Der Grund hat sich verschoben (Preflight → leerer Arbeitsvorrat), die Aussage
  nicht. Sie steht hier, damit sie nicht später als erledigt gilt, weil ihr niemand
  widersprochen hat.
* **Ob die 76 von `SWR-194` übersehenen Lehren einen Vertreter BRAUCHEN.** Gemessen ist,
  dass die Prüfung sie nicht sieht. Ob das schadet, ist die Frage von `T-0050` — und sie
  ist offen. ⚠ Die naheliegende Antwort („Muster erweitern") ist **nicht** gewählt worden,
  weil sie ~100 Dauerbefunde erzeugt hätte.
* **Die volle Testsuite in EINEM Lauf.** Unverändert: ein Gesamtlauf läuft in ein
  Werkzeug-Zeitlimit. Gefahren in Blöcken; die Summe steht unten mit ihrer Herkunft.
* **Ob `gemma3:27b` auf dem Rechner des Auftraggebers installiert ist.** Von hier aus
  nicht messbar (`L-2026-08-20ce`).

</details>

---

<details><summary>Archiv: Sprint 29</summary>

## Das Wichtigste (Sprint 29, 2026-08-21)

1. **✅ FÜNF TICKETS GESCHLOSSEN, DARUNTER BEIDE NULLTEN TERMINIERUNGEN AUS SPRINT 28 UND
   EINE VIERTE BERÜHRUNG — UND KEINES IST VERSCHOBEN WORDEN.** `T-0046`, `T-0030`,
   `T-0045`, `T-0034`, `T-0036`. Fünf neue Anforderungen: **SWR-191 bis SWR-195**.
   > **⚠ Von den offenen Tickets sind **15 → 8** geworden. Drei davon sind nicht
   > geschlossen, sondern **ehrlich gesperrt** — siehe 3.**
2. **⚠⚠ DER PREFLIGHT HAT ZWEI BEFUNDE ÜBER ARBEIT GEMELDET, DIE COMMITTET WAR — UND DER
   FEHLER WAR NICHT DIE ZÄHLUNG, SONDERN DIE GRÖSSE.** Die Prüfung las den **Index**
   (einen Zwischenspeicher) und nannte das Ergebnis *„nicht committet"* (eine Aussage
   über den **Baum**).
   > **Ein falscher Befund ist TEURER als kein Befund: er hat dieselbe Wirkung wie ein
   > echter — er bricht jeden Tick ab — und kennt keine Handlung, die ihn abstellt. Genau
   > das trainiert das Wegsehen, gegen das `SWR-166` gebaut wurde (83 abgebrochene
   > Pushes).**
   `SWR-191`. Am echten Bestand nachgemessen: `pm` **1 → 0**, `platform` meldet nur noch
   die Arbeit **dieses** Laufs. Preis **gemessen statt geschätzt**: `read-tree` je Repo
   kostet über 17 Repos **+7,6 s** (14,4 s statt 6,8 s) — und die Zahl steht in der
   Anforderung, nicht in einer Fußnote.
3. **⚠⚠ NACH VIER TERMINIERUNGEN STEHEN DREI TICKETS ZUM ERSTEN MAL EHRLICH AUF
   `blocked` — UND DER VERGLEICH DER DREI IST DER EIGENTLICHE BEFUND.**
   `SWR-193` macht `blocked_by: [pm/T-0077]` ausdrückbar; `promt-team/T-0003` und
   `T-0012` sind gebucht.
   > **⚠⚠ Und dann fiel `pm/T-0071` auf: es wartet auf `pm/T-0077` im **selben Repo**.
   > Dort war `blocked` die ganze Zeit möglich. Es hat nur nie jemand versucht. Bei
   > `promt-team/T-0003` hat das Werkzeug abgelehnt — hier gab es keine Werkzeuglücke,
   > die die vier Terminierungen erklärt.**
4. **✅ DIE VIERTE BERÜHRUNG VON `platform/T-0030` IST GEBAUT — UND DIE MESSUNG HAT DEN
   ZUSCHNITT BESTIMMT STATT UMGEKEHRT.** Vor der ersten Zeile gezählt: **sieben von neun**
   DoD-Punkten waren **Struktur und keine Arbeit** (das PIN-Gate steht einmal am Kopf von
   `do_POST`, Schreibweg/Fingerabdruck/Zeitquelle lagen bereit).
   > **Die einzige echte Hürde war die Archivsperre — und genau dort stand die Antwort
   > schon im Ticket: *die Sperre gilt dem Formular, nicht dem Gespräch.* Deshalb ist
   > `kommentiere()` ein eigener Pfad NEBEN `aktualisiere` und kein Schalter darin. Ein
   > Schalter an einer Sperre ist keine Sperre.**
   `SWR-192`. Kommentare stehen im **Ticket-Rumpf**, auch an **erledigten** Aufgaben.
5. **⚠⚠ DREIMAL HAT IN DIESEM LAUF EIN WERKZEUG EINEN FEHLER GEFUNDEN, DEN DIE SESSION
   SELBST GEMACHT HAT — UND ZWEIMAL WAR ES DERSELBE.**
   * `uebergang_historie` hat einen **unzulässigen Statussprung** `open → done` gemeldet.
     Ursache: ein `git commit`, dessen Fehlschlag in einer Ausgabeumleitung verschluckt
     wurde; der nächste Statuswechsel machte daraus den Sprung. **Zweimal passiert.**
     Repariert nach dem Muster aus Sprint 27 (lokal, ungepusht → zurückgenommen und über
     `open → in_progress → in_review → done` neu gebucht). Seitdem prüft jeder Schritt,
     **ob der Commit wirklich gelandet ist**.
   * `test_renderweg_zaehlung` wurde rot: der Kommentartext ist der **fünfte**
     Rohtext-Aufrufer, wo vier gezählt waren.
   > **Beide Prüfungen haben genau das getan, wofür sie dastehen. Ein Commit, dessen
   > Erfolg nicht geprüft ist, ist kein Commit — und ein Zähler ohne Namen kann einen
   > Tausch nicht von Stillstand unterscheiden.**
6. **⚠⚠ UND EINE NEUE PRÜFUNG WAR IM ERSTEN ENTWURF TAUTOLOGISCH — GEMESSEN, NICHT
   VERMUTET.** `lehren.py` nannte eine **existierende** Lehr-ID als Beispiel in einem
   Kommentar und hat ihr damit einen Vertreter verschafft: **die Zählung fiel von 29 auf
   28, ohne dass sich an der Sache etwas geändert hatte.**
   > **Eine Prüfung, die ihre eigene Frage beantworten kann, prüft nicht mehr.**
   Behoben zweifach (Muster neutralisiert **und** Prüfer aus dem eigenen Korpus genommen);
   die Gegenprobe dazu ist gebaut: die Testdatei nennt alle 29 IDs im Klartext, also wäre
   die Menge ohne den Ausschluss **leer** — und die Prüfung für immer grün.
7. **✅ ZWEIMAL „ERST ZÄHLEN, DANN BAUEN" AUSGEFÜHRT — UND BEIDE MALE HAT DIE ZAHL DIE
   FRAGE VERÄNDERT.**
   * `T-0034`: **108** Lehren, **34** mit ausformulierter Regel, **5** mit Vertreter,
     **29** ohne. Die Vermutung *„Grundmenge groß, Trefferquote klein"* ist **halb
     widerlegt**: die Quote ist klein (15 %), die Grundmenge ist es **nicht** (34 von
     108) — und genau das beantwortet die Frage nach der „ehrlichen Untermenge" von
     allein. Die Konvention war **gefunden und nicht erfunden**.
   * `T-0036`: **1003** Zitatstellen ohne Repo-Präfix gegen **319** mit (Vermutung
     bestätigt, 76 %) — **aber** die zwei größten Posten sind die Entscheidungslogs
     **selbst**, wo die Angabe nicht mehrdeutig ist. **Die 1003 sind nicht 1003
     Probleme.** Deshalb gebaut **und** geschnitten (`platform/T-0047`).
8. **⚠ DER OLLAMA-OFFLOAD IST WEITERHIN NICHT DELEGIERT, UND DER GRUND IST UNVERÄNDERT
   ZWEIFACH.** `pm/T-0071` hat noch immer keinen Tick mit `status: ok` + Artefakt — und
   Sprint 28 hat gemessen, dass eine Cowork-Session den Provider **gar nicht erreichen**
   kann (`localhost:11434` refused, `host.docker.internal:11434` 403). **Kein Ticket an
   Ollama delegiert; Token-Ersparnis daher 0, und das ist gemessen und nicht geschätzt.**
9. **1367 Python-Tests** über **90** Testdateien (**gemessen**, `kennzahlen.py` — +56 über
   +5 Dateien), Matrix **195 SWRs / 0 Lücken**, **113** JS-Tests grün (+6),
   `organigramm --check` grün (19 Dateien), Briefkasten **0 offen / 0 eingegangen**,
   offene Tickets **8**, auf den Menschen wartend **1** (`pm/T-0077`, Frist 28.08.),
   Workflows **6 / 0 unabgedeckte Takte**, Work-Product-Lücken **0**, Parkplatz **11138**
   (Stand 03:36 — die Zahl trägt ihren Zeitpunkt, `SWR-174`).

## Sprint-Plan (Sprint 29)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 29 | **erfüllt** | ✅ **0 offen**, beim Start und beim Abschluss gemessen. Kein Brief ist während des Laufs eingegangen. |
| **platform/T-0046** | dev | Sprint 29 | **erledigt** | ✅ **SWR-191.** Nullte Terminierung aus Sprint 28, im Folgelauf gebaut wie angekündigt. Drei Vorabfragen **vor** dem Bau beantwortet und gemessen. |
| **platform/T-0030** | dev | Sprint 29 | **erledigt** | ✅ **VIERTE BERÜHRUNG: GEBAUT.** `SWR-192`. Der Brief `platform/N-0007` ist beantwortet. |
| **platform/T-0045** | dev | Sprint 29 | **erledigt** | ✅ **SWR-193.** Nullte Terminierung aus Sprint 28. Wirkung **gemessen**: drei Tickets stehen ehrlich auf `blocked`. |
| **platform/T-0034** | coach | Sprint 29 | **erledigt** | ✅ **SWR-194.** Erste Verschiebung beendet. Sperrklinke statt Anklagezettel. |
| **platform/T-0036** | cm | Sprint 29 | **erledigt** | ✅ **SWR-195, gebaut UND geschnitten.** Der schwerere Befund ist gebaut, die Zitierfrage geht mit ihrer Zahl nach `T-0047`. |
| promt-team/T-0003 | dev | — | **blocked** | ⚠⚠ `blocked_by: [pm/T-0077]`. **Keine fünfte Terminierung.** Erstmals ausdrückbar (`SWR-193`). |
| promt-team/T-0012 | prompt-opt | — | **blocked** | ⚠⚠ dito. |
| pm/T-0071 | pl | — | **blocked** | ⚠⚠ `blocked_by: [T-0077]` — **im selben Repo, war die ganze Zeit möglich.** Siehe Punkt 3. |
| **pm/T-0077** | mensch | Frist 28.08. | **wartet** | ⚠ Unverändert offen, Frist **nicht** erreicht (heute 21.08.). Default **A**, Schweigen genügt. |
| **platform/T-0047** | cm | Sprint 30 | offen | ⚠ **Neu, nullte Terminierung.** Schnitt aus `T-0036`, mit der Messung im Rumpf. Erbt die Berührungszählung von `T-0036` **nicht** — der gebaute Teil ist gebaut. |
| pm/T-0001, pm/T-0002, pm/T-0003, platform/T-0001, team-dashboard/T-0001, team-mail/T-0001 | pl/coach/cm/dev | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**neun**) + Chronik in **drei** Einheiten + Verifikation. Workflow-Abdeckung **6/6, 0 Lücken**, WP-Lücken **0** — kein neues Takt-Ticket, also keine neue Workflow-Pflicht. |

## Sprint-Abschluss (Sprint 29, 2026-08-21)

**Geschlossen:** `platform/T-0046`, `T-0030` (vierte Berührung, **gebaut**), `T-0045`,
`T-0034`, `T-0036` (**gebaut und geschnitten**). **Nichts verschoben.**

**Neue Anforderungen:** **SWR-191** (Baum statt Index), **SWR-192** (Kommentare am
Ticket), **SWR-193** (repo-übergreifende Sperre), **SWR-194** (Lehre ohne Vertreter),
**SWR-195** (keine neue Dublette im Entscheidungslog).

**Neu angelegt:** `platform/T-0047` (Schnitt aus `T-0036`, mit 1003/319 im Rumpf).

**Auf `blocked` gebucht statt terminiert:** `promt-team/T-0003`, `promt-team/T-0012`,
`pm/T-0071`.

**Lessons (neun, alle sofort verankert):** `L-2026-08-21ce` (ein falscher Befund ist
teurer als kein Befund), `cf` (ein Schalter an einer Sperre ist keine Sperre), `cg` (ein
Aufwärtsgang braucht ein Abbruchkriterium aus dem Gegenstand), `ch` (eine Prüfung, die
sich selbst liest, beantwortet ihre eigene Frage), `ci` (B033 mit einem Schreibweg als
vergessener Kopie), dazu Historie-Lehren 9–17 in `platform`.
**Verbleib: Historie `platform` Lehren 9–17, Rollenkarten DEV/TEST/QM/CM/PL, Runbook
Kap. 16/17.**

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

* **Die volle Testsuite in EINEM Lauf.** Gefahren wurden **alle** Module in **acht
  Blöcken**; ein Gesamtlauf läuft unverändert in ein Werkzeug-Zeitlimit (`test_u*` allein
  **154 s**, `test_js_teststrecke` + Nachbarn **159 s**). ⚠ **Die Summe ist trotzdem
  belegt, und zwar durch zwei UNABHÄNGIGE Messungen:**
  436 + 111 + 28 + 350 + 209 + 108 + 56 + 69 = **1367** — und `kennzahlen.py` zählt
  **1367** in der Sammlung. **Deckungsgleich.**
  > **⚠ Ein erster Zwischenstand ergab 1342 und damit eine Lücke von 25. Die Ursache war
  > nicht die Suite, sondern die Messung: die Blöcke waren zu verschiedenen Zeitpunkten
  > gefahren worden, und fünf der Testdateien dieses Laufs existierten beim frühen Block
  > noch nicht. Nachgemessen statt berichtet — eine Summe aus Teilmessungen zu
  > verschiedenen Ständen ist keine Summe.**
* **Ob `git status` auf diesem Mount die Sperren SELBST erzeugt.** Vermutet nach den
  `unable to unlink`-Warnungen, an einem synthetischen Repo **nicht reproduzierbar** —
  die Gegenprobe ist damit **ergebnislos** und nicht bestätigend. `SWR-191` beansprucht
  diesen Nebeneffekt deshalb **nicht**; strukturell ist nur, dass `GIT_INDEX_FILE` die
  Sperre in `/tmp` legt statt in `.git/`.
* **Ob `gemma3:27b` auf dem Rechner des Auftraggebers installiert ist.** Unverändert von
  hier aus nicht messbar (`L-2026-08-20ce`).
* **Ob die 29 Lehren ohne Vertreter ihn BRAUCHEN.** Gemessen ist, dass sie keinen haben.
  Ob jede einzelne einen verdient, ist eine inhaltliche Frage, die diese Prüfung
  ausdrücklich **nicht** beantwortet.


---

## Das Wichtigste (Sprint 27, 2026-08-20)

1. **⚠⚠ EINE ANFORDERUNG WAR GRÜN UND IHRE WIRKUNG WAR NULL — UND GEFUNDEN HAT DAS KEINE
   PRÜFUNG, SONDERN EIN ZUFALL.** `SWR-169` holt das Ollama-Modell aus dem
   Besetzungsregister und ist in **vier** Gegenproben belegt. Im Betrieb hat es nie
   gegriffen: **alle vier prüften die Auflösungsfunktion, keine ihren Aufrufer.**
   > **Ohne den ungeplanten Lauf um 21:30 hätte Sprint 26 „SWR-169 gebaut" berichtet und
   > wäre damit durchgekommen.**

   `platform/T-0033` (kritisch), `SWR-171`/`SWR-172`. `L-2026-08-20cn` (cm, Regel 5).
2. **⚠⚠ UND DER BEFUND IST GRÖSSER ALS DER MODELLNAME: DER TICK HAT ARBEIT AN EINE
   INSTANZ GEGEBEN, DIE NIEMAND BESETZT.** Gezogen wurden `CM@platform` und
   `DEV@team-mail`. `CM@platform` steht im Register mit `motor: cowork` — **`DEV@team-mail`
   steht dort überhaupt nicht.**
   > **Der leere Modellname war die FOLGE und nicht die Ursache. Eine Prüfung auf den
   > Modellnamen wäre still geworden, sobald irgendjemand irgendein Modell einträgt.**

   `SWR-171` prüft deshalb die **Besetzung**, vor Gateway-Aufruf, Branch und Statuswechsel.
3. **⚠ ERST GEZÄHLT, DANN GEBAUT — und die Zahl hat die Bauart entschieden: 0 von 14.**
   Kein einziges der 14 offenen Tickets trägt eine Rolle mit ollama-Besetzung. Damit ist
   die wörtliche Umsetzung von `pm/D010` **keine Lösung, sondern eine Abschaltung**.
   > **Der Schalter (`--rolle`, `SWR-172`) ist deshalb GEBAUT und NICHT UMGELEGT; eine
   > Zusicherung wacht darüber, dass „gebaut, nicht umgelegt" nicht stillschweigend zu
   > „umgelegt" wird.** Die Frage liegt als `platform/T-0035` beim Auftraggeber
   (A/B/C, Frist 27.08., Default A) — es ist seine Automatik.
4. **✅ DER NACHWEIS KAM AUS SEINEM BETRIEB, NICHT AUS UNSEREM TEST.** Um **22:00** hat
   der Schnelltakt erneut gefeuert, mitten in diesem Lauf. Im Log steht
   `Tick OHNE ERGEBNIS (Besetzung): …`; nachgemessen: **kein** neuer Registry-Eintrag,
   beide Repos sauber auf `main`, `T-0001` unverändert `open`.
   > **⚠⚠ Und derselbe Lauf hat unsere MUTATION ausgeführt.** Zum Zeitpunkt 22:00 stand
   > die absichtlich verfälschte Fassung aus der Gegenprobe auf der Platte — im Log des
   > Auftraggebers steht wörtlich `IMMER ABBRUCH`. Folgenlos (der Abbruch tut nichts), und
   > **es steht hier, weil es sonst niemand erfahren würde.** Eine Gegenprobe an Code, den
   > alle 15 Minuten eine fremde Automatik startet, ist ein Eingriff in den Betrieb.
5. **⚠⚠ DIE GEGENPROBE ZUR GEGENPROBE HAT SICH SELBST GETÄUSCHT.** Der erste
   Mutationsdurchgang meldete **grün** für eine **ausgeschaltete** Prüfung — die Mutation
   stand zum Testzeitpunkt noch nicht auf der Platte, ein alter `__pycache__` lag daneben.
   Erst der verifizierte zweite Durchgang zeigte 2 rote Zusicherungen.
   > **Grün ist zweideutig: „die Prüfung greift nicht" oder „die Mutation ist nicht
   > angekommen". Es hätte als „Gegenprobe bestanden" in genau dem Bericht gestanden, der
   > aus einer Gegenprobe entstanden ist, die die falsche Hälfte gemessen hat.**
   `L-2026-08-20cm`.
6. **✅ `platform/T-0027` BEI DER VIERTEN BERÜHRUNG: GEBAUT *UND* GESCHNITTEN.**
   `SWR-173` (die Kennzahlen entstehen aus ihren Quellen: `platform/scripts/kennzahlen.py`)
   und `SWR-174` (eine Zusicherung hält den Bericht dagegen, **vor** dem Push). Erwartungswert
   **vor** dem Bauen aufgeschrieben: 0 Abweichungen. Gemessen: 0.
   ⚠ Der Parkplatz ist **mit Begründung im Test** von der Gleichheit ausgenommen und muss
   stattdessen einen **Zeitpunkt** tragen — *eine gemessene Zahl ohne den Zeitpunkt ihrer
   Messung altert genauso lautlos wie eine geschätzte.*
   ⚠ Geschnitten: die Rubrik **„gelernt ohne Vertreter"** ist `platform/T-0034` geworden —
   der eigene Text von `T-0027` hatte das als erste Frage des nächsten Anlaufs vorgegeben.
   `L-2026-08-20cp` (coach), Runbook **Kap. 15**.
7. **⚠⚠ EINE BEDINGUNG, DIE GEGEN FEHLSCHLÄGE GESCHÄRFT WURDE, WAR DURCH EINEN ERFOLG VON
   VOR VIERZEHN TAGEN SCHON ERFÜLLT.** `promt-team/T-0008` verlangte seit Sprint 26 *„ein
   Tick mit `status: ok` und Artefakt"* und schrieb dazu **„Stand: 0 von 3"**. In
   `p0/.../run-registry.jsonl` steht seit dem **2026-08-06**:
   `cm | ok | provider: ollama | artefakte: ['process/']`.
   > **Die Bedingung liest über den BESTAND und ist an einem EREIGNIS gemessen worden.
   > Zweimal hintereinander war die Grundmenge das, worauf niemand gesehen hat — `SWR-128`
   > zum dritten Mal.** Neue Bedingung mit benannter Grundmenge **und Stichtag**.
8. **⚠ UND DER EIGENE FEHLER DIESES LAUFS, DER NICHT DURCHGEHT.** Der Abschluss von
   `T-0033` schrieb `status: done` direkt auf `open`. `board.py` hat das abgelehnt —
   **neben** dem Commit statt davor (`;` statt `&&`), der unzulässige Übergang stand in
   der Historie. Repariert über den richtigen Weg (`open → in_progress → in_review → done`,
   je ein Commit); der Fehlcommit war lokal und ungepusht und ist zurückgenommen.
   > **Eine Prüfung, die neben dem Schreibvorgang läuft statt vor ihm, ist eine Meinung.**
   `L-2026-08-20cn`/`co`, Runbook **Kap. 16 und 17**.

## Sprint-Plan (Sprint 27)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 27 | **erfüllt** | ✅ **0 offen** über 61 Briefe in 11 Repos, beim Start und beim Abschluss gemessen. Kein Brief ist während dieses Laufs eingegangen. |
| platform/T-0033 | dev | Sprint 27 | **erledigt** | ✅ **Erster Punkt des Sprints wie geplant** (`prio: kritisch`). **SWR-171/172.** Frage 3 zuerst beantwortet (**0 von 14**), Frage 2 verworfen, Frage 1 als DR vorgelegt statt selbst entschieden. |
| platform/T-0027 | cm | Sprint 27 | **erledigt** | ✅ **Vierte Berührung: gebaut UND geschnitten.** **SWR-173/174** + Abtrennung nach `T-0034`. Erwartungswert 0 Abweichungen vor dem Bau notiert und getroffen. |
| platform/T-0035 | mensch | Sprint 27 | **erledigt** | ✅ **Neu gestellt (22:18) und nach DREI MINUTEN mit A entschieden** (`platform/D000`, 22:21). Verbucht, geschlossen, **keine Folgearbeit** — A ist der Ist-Zustand. Kein Nachfolgeticket. |
| platform/T-0036 | cm | Sprint 28 | offen | ⚠ **Neu, nullte Terminierung** — Nebenbefund der Verbuchung: `D000` gibt es 17-mal, `pm/D005` dreimal in einer Datei. **Benannt, nicht gebaut.** |
| platform/T-0034 | coach | Sprint 28 | offen | ⚠ **Neu, nullte Terminierung** (abgetrennt, nicht verschoben). „Gelernt ohne Vertreter". Sofort-Wirkung als Runbook Kap. 15 **noch in diesem Lauf** — ausdrücklich als Provisorium markiert. |
| pm/T-0071 | pl | Sprint 28 | offen | ⚠ **Schritt 2 ist ZU ENDE beantwortet, und die Antwort ist nein:** der Takt hat nie an dem gearbeitet, wofür er entschieden wurde. Schritt 3 wartet auf einen Arbeitsvorrat für PROB/MAIL-RED, nicht auf Betriebszeit. Kein `blocked`. |
| promt-team/T-0008 | test | Sprint 28 | offen | ⚠ **3. Verschiebung der neuen Fassung** — und diesmal mit einem Befund über die Bedingung selbst (erfüllt seit dem 06.08.). Neue Bedingung mit Grundmenge **und Stichtag**. |
| promt-team/T-0003 | dev | Sprint 28 | offen | ⚠ **3. Terminierung mit dem richtigen Grund.** Ein Eintrag vom 6. August ist keine Baseline für den heutigen Prompt; der Weg zu einem frischen ist gemessen versperrt. |
| platform/T-0030 | dev | Sprint 28 | offen | ⚠ **2. Verschiebung.** Neu dazu: der Schnelltakt hat **während** dieses Laufs in dieselben Repos gegriffen — DoD 8 (Konflikterkennung) ist damit kein Papierpunkt mehr. |
| projects/p11/T-0016 | dev | Sprint 28 | offen | ⚠ **3. Verschiebung**, Kapazität. Umfang unverändert **gezählt** (4 Bausteine, 11 von 111 JS-Zusicherungen), drei Vorabfragen bewusst unbeantwortet. |
| p9/T-0008 | mensch | Sprint 27 | **erledigt** | ✅ **Nach SIEBEN Minuten mit A entschieden** (`p9/D003`, 22:25) — **plus** der Anweisung *„Nennen P9 in Org-Cockpit um"*. Verbucht **und ausgeführt**: **SWR-175**, Anzeigename im Steckbrief. Der Ordner bleibt `p9`. |
| team-mail/T-0001 | dev | jeder Sprint | offen (Takt) | ⚠ Vom 22:00-Tick gezogen und **korrekt unangetastet gelassen** (SWR-171). Unverändert offen: `N-0003` (Zugangsdaten) — der Brief ist beantwortet, die Daten fehlen. |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**vier**: `cm` `cn` `co` cm · `cp` coach) + drei Runbook-Kapitel (15/16/17) + Verifikation. |

## Sprint-Abschluss (Sprint 27, 2026-08-20)

**Geschlossen:** `platform/T-0033` (kritisch, erster Punkt des Sprints) und
`platform/T-0027` (vierte Berührung, gebaut **und** geschnitten).

**Entscheidungen des Auftraggebers, im Lauf verbucht:** `platform/D000` (T-0035 = **A**, 3 Min Antwortzeit, keine Folgearbeit) und `p9/D003` (T-0008 = **A** plus Umbenennung, 7 Min, ausgeführt als **SWR-175**).

**Neue Anforderungen:** **SWR-171** (die Besetzung wird vor dem Gateway-Aufruf geprüft),
**SWR-172** (`--rolle` — gebaut und nicht umgelegt), **SWR-173** (die Kennzahlen entstehen
aus ihren Quellen), **SWR-174** (eine Zusicherung hält den Bericht dagegen; der Parkplatz
ist mit Begründung ausgenommen), **SWR-175** (Anzeigename für Einheiten ohne Team), **SWR-176** (die qualifizierte
Planzeile gewinnt gegen die nackte ID).

**Neu angelegt:** `platform/T-0034` (abgetrennt von `T-0027`, Sprint 28), `platform/T-0035`
(DR — gestellt und im selben Lauf entschieden), `platform/T-0036` (Nebenbefund der
Verbuchung, Sprint 28).

**Verschoben:** `pm/T-0071`, `promt-team/T-0008` (3. der neuen Fassung),
`promt-team/T-0003` (3.), `platform/T-0030` (2.), `projects/p11/T-0016` (3.) — jede mit
Grund **im Ticket**.

**Lessons:** `L-2026-08-20cm` (Mutationsprobe ohne Wirkungsnachweis), `L-2026-08-20cn`
(Statuswechsel an der Übergangsmatrix vorbei), `L-2026-08-20co` (Git über den einen
Schreibweg), `L-2026-08-20cp` (gelernt ohne Vertreter). **Runbook Kap. 15, 16, 17.**

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

1. Ob ein Tick jemals ein brauchbares Artefakt liefert. Dazu bräuchte es ein offenes
   Ticket für `PROB@platform` oder `MAIL-RED@team-mail`, und davon gibt es **null**.
   Der Satz steht hier aus demselben Grund wie in Sprint 25 und 26: damit er nicht später
   als erledigt gilt, weil ihm niemand widersprochen hat.
2. Ob `gemma3:27b` auf dem Rechner des Auftraggebers installiert ist — von hier aus nicht
   messbar (`L-2026-08-20ce`) und deshalb nicht behauptet.
3. Ob `SWR-173/174` künftig falsche Zahlen verhindern. Sie decken **sieben**
   wiederkehrende Kennzahlen ab. Der achte Beleg von `T-0027` — `9` statt `11` in einem
   Fließtext — wäre **nicht** gefunden worden, und das steht so im Abschluss des Tickets.
4. ⚠ `main` und `feature/t-0001-…` in `platform` sind weiterhin **repariert, nicht
   aufgelöst**. Unverändert seit Sprint 26.



---

## ⚠⚠ NACHTRAG: der Auftraggeber hat WÄHREND des Laufs BEIDE offenen Fragen beantwortet

| Frage | gestellt | beantwortet | Antwortzeit |
|---|---|---|---|
| `platform/T-0035` (Schnelltakt) | 22:18, **in diesem Lauf** | 22:21, **A** | **3 Minuten** |
| `p9/T-0008` (Wo leben die Anforderungen?) | Sprint 26, Frist 27.08. | 22:25, **A** + Anweisung | **7 Minuten** |

> **Zum zweiten Mal in zwei Sprints kostet das Fragen weniger als das Ausweichen. `T-0035`
> war die Frage, die diesen Sprint daran gehindert hat, die Automatik selbst umzustellen —
> sie war in drei Minuten beantwortet.**

**`platform/T-0035` = A:** alles bleibt. Der Takt läuft weiter und meldet ehrlich, dass es
für seine Besetzungen nichts zu tun gibt. **Keine Folgearbeit** — A ist der Zustand, den
dieser Lauf hergestellt hat. Kein Nachfolgeticket.

**`p9/T-0008` = A *plus* Anweisung:** *„Nennen P9 in Org-Cockpit um."* Der Antrag hatte A
und C als **Alternativen** angeboten; die Antwort nimmt A und den Kern von C.
> **Das ist keine Unentschlossenheit, sondern die genauere Auskunft: die Anforderungen
> bleiben liegen, wo sie liegen, und der Name sagt ab jetzt, was dort liegt. Identität und
> Beschriftung sind zwei Dinge — der Antrag hat sie als Alternativen behandelt.**

Ausgeführt als **`SWR-175`**: `steckbrief.yaml` trägt ein Feld `name`, Rangfolge
Team-Registry > Steckbrief > Ordnername. Im Organigramm steht **Org-Cockpit**; die
Discovery-Kennung, der Ordner und jeder Querverweis `p9/...` bleiben **`p9`**.

⚠ **Was damit NICHT erledigt ist:** *keine Prüfung dieses Hauses fragt, ob der Name über
einem Ordner noch stimmt.* Ein Anzeigename macht diesen einen Fall lesbar und lässt die
Prüfung fehlen (`platform/T-0034`).

### ⚠ Und das Verbuchen selbst hat einen Befund geliefert: `platform/T-0036`

Der Entscheidungsmarker lautet **`D000`** — und `D000` gibt es in diesem Haus **17-mal**.
Die IDs werden **je Repo** vergeben (`inbox._naechste_d_id` liest das Log des jeweiligen
Repos), zitiert werden sie in den Berichten **global**: „D004", „D005", „D000".
⚠ Härter: `pm/.../decision-log.md` führt **`D005` dreimal und `D006` zweimal** — eine
Kollision in **einer** Datei, die `max+1` nicht erzeugt haben kann. Es gibt einen zweiten,
handgeschriebenen Schreibweg ins Entscheidungslog, und der hat keine Nummernvergabe.
> **Das ist `L-2026-08-20ce` an neuer Stelle: eine Angabe, die ihren Ort verloren hat.**
**Benannt, nicht gebaut** — eine Umstellung von Entscheidungs-IDs berührt jede Zitatstelle
in jedem Bericht dieses Hauses.


### ⚠⚠ Nachtrag 2: der Preflight hat einen echten Drift gemeldet und das FALSCHE Paar genannt

Bei der Schlussverifikation stand `1 Befund`: *„Plan sagt Sprint 27, Ticket sagt Sprint 28"*
für `promt-team/T-0008`. Die Planzeile sagt **28**, das Ticket sagt **28**.

Die Zeile, die den Befund auslöste, war eine **andere**: `p9/T-0008`. Sie gehört einem
**geschlossenen** Ticket und steht deshalb nicht in der Menge der offenen; die Auflösung
fiel auf die nackte `T-0008` zurück, und die war unter den **offenen** Tickets eindeutig —
`promt-team/T-0008`, anderes Repo, anderer Sprint.

> **⚠⚠ Die Eindeutigkeit ist über die OFFENEN Tickets geprüft, die Zeile gehörte einem
> GESCHLOSSENEN. Eine ID wird nicht dadurch eindeutig, dass die Restmenge klein ist.**

⚠ Das Schwestermodul `statusdrift` löst über **alle** Tickets auf und ist nie in diese
Falle gelaufen — dieselbe Frage, zwei Grundmengen, eine davon falsch gewählt.

> **Damit ist es der DRITTE Befund dieses Sprints aus derselben Familie (`SWR-128`, *grün,
> weil niemand fragt, worüber*): die Gegenprobe ohne Aufrufer, die Bedingung, die den
> Bestand liest und an einem Ereignis gemessen wurde — und jetzt die Grundmenge einer
> Nachschlagetabelle.**

⚠ Und der Fund selbst ist kein Zufall: die Zeile entstand, **weil dieser Lauf `p9/T-0008`
geschlossen hat**. *Eine Prüfung kann dadurch falsch werden, dass ein Ticket erledigt
wird.*

Behoben als **`SWR-176`** — nennt eine Planzeile ein Repo, gilt nur die qualifizierte
Form. Vier Zusicherungen, darunter das Paar (die eigene Zeile wird weiterhin geprüft) und
der Notnagel (eine Zeile **ohne** Repo löst weiterhin über die nackte ID auf).

---

# Anhang: Sprint 26

## Das Wichtigste (Sprint 26, 2026-08-20)

1. **⚠⚠ DER ERSTE TICK, DER JEMALS DURCHGELAUFEN IST — UND ER HAT NICHTS GETAN.** `SWR-166`
   hat den Preflight entsperrt; seither sind **3 von 26** Versuchen durchgekommen (20:00
   `platform`, 20:15 `platform`, 20:15 `team-mail`). Alle drei: `status=fehler`,
   `artefakte=[]`.
   > **Sprint 25 hatte ausdrücklich aufgeschrieben, dass er das NICHT gemessen hat —
   > „damit es nicht später als erledigt gilt, weil ihm niemand widersprochen hat". Dies
   > ist die Messung, und die Antwort ist nein.**

   `platform/T-0031`, `platform/T-0032`, `SWR-167`–`SWR-170`.
2. **⚠⚠ DIE URSACHE STAND SEIT VIERZEHN TAGEN ALS LEHRE IM BESTAND — DREIMAL, MIT
   ERWARTUNGSWERT.** `404: model 'llama3.1:8b' not found`. **L-003** vom **2026-08-06**
   nennt den Guardrails-Default, nennt `gemma3:27b` als das installierte Modell und nennt
   die Gegenmaßnahme wörtlich: *„Modell-Defaults gegen das Geräteregister prüfen;
   Abweichungen als Registry-/Guardrails-CR nachziehen."* Abgelegt in `T-0036-prompt.md`,
   `p0/sprint-1/retro.md` und `p0/T-0016` — dort mit **„Erwartungswert: Wiederholungsquote
   in Sprint 2 = 0"**. Die Quote ist **3 von 3**.
   > **Es fehlte NICHT die Sorgfalt beim Aufschreiben. Die Lehre ist vorbildlich
   > formuliert, dreifach abgelegt und mit Erwartungswert versehen — und hat vierzehn Tage
   > lang exakt null Wirkung gehabt, weil der Satz, der ihren Vollzug trug, nie ein Ticket
   > geworden ist.**

   Das ist der **elfte** Beleg für `platform/T-0027` und der härteste; die neue Rubrik
   heißt **„gelernt ohne Vertreter"**. `L-2026-08-20ci`.
3. **⚠⚠ UND DER TICK HAT DEN SCHADEN SELBST VERLÄNGERT — DREI BEFUNDE IN EINER FUNKTION.**
   (a) `print("Tick abgeschlossen…")` stand **unbedingt** vor `return 0` — auch nach
   `fehler`. (b) Der Branchname ist bei **jedem** Tick derselbe; beim zweiten Tick von
   `T-0001` zog `checkout <branch>` HEAD **zwei Commits zurück**, `main` und Branch sind
   divergiert. (c) Die Rückkehr auf `main` stand mit `fehler_ok=True` da und ist
   stillschweigend misslungen.
   > **⚠⚠ Folge: `main` behielt `in_progress`, der Arbeitsbaum stand auf dem Branch mit
   > `open` — und der Preflight, der den ARBEITSBAUM liest, meldete „In Arbeit
   > liegengeblieben: 0". Eine Prüfung, die den Arbeitsbaum liest, prüft den Branch, auf
   > dem sie zufällig steht.**

   Repariert (Commit `e532681`), gebaut (`SWR-167/168`). `L-2026-08-20cj`.
4. **✅ DER AUFTRAGGEBER HAT GEANTWORTET — NACH FÜNF MINUTEN.** `p12/T-0012` (Rendern von
   Ticket-Bodys) ist am 20.08. um **20:34** mit **A** entschieden (`D004`), fünf Minuten
   nach Beginn dieses Sprints. Verbucht, geschlossen, **nichts gebaut und nichts
   zurückgebaut** — A ist der Ist-Zustand.
   > **Fünfmal als Aufgabe terminiert, einmal gefragt, fünf Minuten Antwortzeit. Der
   > Aufwand lag nie im Beantworten, sondern darin, die Frage als Frage zu erkennen.**

   ⚠ Bemerkt hat die Antwort **kein** Preflight (der lief vorher), sondern
   `test_dr_verbuchung` über den **echten Bestand**, mitten im Lauf. *Die rote Zeile war
   nicht die Störung des Laufs, sie war sein Ergebnis.*
5. **⚠ EINE BEDINGUNG, DIE EIN FEHLSCHLAG ERFÜLLT, IST KEINE BEDINGUNG.** `pm/T-0071`,
   `promt-team/T-0003` und `promt-team/T-0008` warteten alle auf *„mindestens einen
   durchgelaufenen Tick"*. Drei sind durchgelaufen — die Bedingung war **wörtlich erfüllt
   und inhaltlich nicht**. Nachgeschärft in allen dreien auf: **ein Tick mit `status: ok`
   und mindestens einem Artefakt** (Stand: **0 von 3**).
   ⚠ Nebenbefund aus `T-0008`: es gibt **drei** Run-Registries, nicht eine. Der Tick
   schreibt in die des Ziel-Repos, `T-0008` liest nur die von `p0` — **die Bedingung zeigt
   auf ein Register, in das die Ticks nicht schreiben.** Benannt, nicht gebaut.
6. **⚠⚠ Zum FÜNFTEN Lauf in Folge hat ein Werkzeug den frischen Entwurf verworfen — und
   diesmal DREIMAL in einem Lauf.** Zweimal war es ein Test gegen seinen eigenen Verfasser,
   einmal der Preflight gegen den Sprintplan: die Planzeile zu `p9/T-0008` sagte
   **„erledigt“**, weil der *Brief* beantwortet war — der *DR* ist es nicht.
   > **Ein beantworteter Brief ist keine getroffene Entscheidung. Die Zeile hätte den
   > Zähler „auf dich wartende Entscheidungen“ um eins zu niedrig gehalten, und zwar in
   > genau dem Bericht, der ihn nennt.**
   `test_kein_return_im_finally` suchte nach dem **Wort** „return" und wurde von dem
   Kommentar rot gemacht, der das Verbot erklärt. `test_am_echten_bestand…` erwartete
   `MAIL-RED@mail` — aus dem Team-Kürzel **gebildet** statt aus dem Register **gelesen**;
   die Instanz heißt `MAIL-RED@team-mail`. `L-2026-08-20ck`.
7. **Verifikation:** **1236 Python-Tests** in der Sammlung (**gemessen**, **76**
   Testdateien), Matrix **170 SWRs / 0 Lücken**, Briefkasten **0 offen beim Start, 2
   eingegangen und beantwortet**, entschiedene
   unverbuchte DRs **0** (nach der Verbuchung), Parkplatz **10043**.
   ✅ Neue Preflight-Zeile (`SWR-170`): *2 von 2 ollama-Besetzungen weichen ab* — erwartet
   waren 2. *Eine Prüfung, deren erwarteter Wert vor dem Bauen aufgeschrieben wird, prüft
   beim ersten Lauf sich selbst mit.*

## Sprint-Plan (Sprint 26)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| Briefkasten (alle Repos) | pl | Sprint 26 | **erfüllt** | ✅ Beim Sprintstart 0 offen (59 Briefe). ⚠ **Zwei kamen WÄHREND des Laufs** (20:36, 20:40) und sind beantwortet: `p9/N-0001`, `promt-team/N-0002`. |
| p9/N-0001 (Brief) | pl | Sprint 26 | **erledigt** | ✅ *„kann dieses Projekt geschlossen werden?"* — gemessen: 7/7 Tickets `done`, **78 Commits in 7 Tagen**, 81 SWRs, davon 9 der letzten 25 aus `platform`. Beantwortet und committet. |
| p9/T-0008 (DR) | mensch | Frist 27.08. | offen | ⚠ **Neu, Klasse C, drei Optionen, Default A = alles bleibt.** Liegt in der Inbox. ⚠ Der erste Entwurf der Planzeile schrieb **„erledigt“** — der Brief war beantwortet, der DR ist es nicht. **Der Preflight hat es als Plan-Drift gemeldet**, und er hatte recht: *ein beantworteter Brief ist keine getroffene Entscheidung.* |
| promt-team/N-0002 | pl | Sprint 26 | **erledigt** | ✅ *„beim prompt team bewegen sich die Aufgaben nicht mehr"* — gemessen: 8/10 `done`, die zwei offenen warten auf Läufe mit Ergebnis. Nebenbefund: drei Run-Registries. |
| Tick-Schaden `platform` | cm | Sprint 26 | **erledigt** | ✅ **Reparatur vor Bau.** `platform` zurück auf `main`, `T-0001` auf `open`, der nur auf dem Branch liegende Run-Registry-Eintrag nachgetragen (`logging.run_registry: required`). Commit `e532681`. |
| platform/T-0031 | dev | Sprint 26 | **erledigt** | ✅ **Neu und geschlossen im selben Lauf** (`prio: kritisch`). **SWR-167/168.** Vier Gegenproben gefahren (Mutation → rot, Rücknahme → 17/17 grün). |
| platform/T-0032 | dev | Sprint 26 | **erledigt** | ✅ **Neu und geschlossen im selben Lauf** (`prio: kritisch`). **SWR-169/170.** Am echten Bestand: erwartet 2 Abweichungen, gemessen 2. |
| projects/p12/T-0012 | pl | Sprint 26 | **erledigt** | ✅ **Entscheidung `D004` (A) verbucht.** Keine Folgearbeit: A ist der Ist-Zustand. Kein Nachfolgeticket — eines für „nichts tun" wäre ein Vorgang ohne Gegenstand. |
| pm/T-0071 | pl | Sprint 27 | offen | ⚠ **Schritt 2 IST beantwortet** (Ticks laufen, nur ollama-fähige Typen, Gate-relevantes unberührt) — und die Antwort ist halb: 0 Artefakte. Schritt 3 wartet auf **Betriebszeit mit Ergebnis**, nicht auf einen Menschen. Bedingung nachgeschärft. |
| promt-team/T-0003 | dev | Sprint 27 | offen | ⚠ **2. Terminierung mit dem richtigen Grund.** Baseline über drei Fehlläufe wäre eine Messung des Modellnamens, nicht des Prompts. |
| promt-team/T-0008 | test | Sprint 27 | offen | ⚠ **2. Verschiebung der neuen Fassung.** Grund gemessen (0 Läufe mit Ergebnis) **plus** neuer Befund: drei Run-Registries statt einer. |
| platform/T-0027 | cm | Sprint 27 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Elfter Beleg geliefert, Rubrik **„gelernt ohne Vertreter"** ergänzt. ⚠ **Beim vierten Mal: gebaut oder geschnitten.** |
| platform/T-0030 | dev | Sprint 27 | offen | ⚠ **1. Verschiebung.** Ein zweiter Schreibweg in eine Ticketdatei ist erst dann eine Verbesserung, wenn der erste nachweislich dort landet, wo er soll — das ist mit `SWR-168` gerade hergestellt worden. |
| projects/p11/T-0016 | dev | Sprint 27 | offen | ⚠ **2. Verschiebung**, Kapazität. Umfang unverändert **gezählt** (4 Bausteine, 11 von 111 JS-Zusicherungen), nicht neu geschätzt. |
| team-mail/T-0001 | dev | jeder Sprint | offen (Takt) | ⚠ Der Tick hat dieses Ticket gezogen und ist am Modellnamen gescheitert — **aber korrekt aufgeräumt** (zurück auf `main`, Status `open`, Fehler im Rumpf). Unverändert offen: `N-0003` (Zugangsdaten). |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**vier**: `ci` `cj` cm · `ck` test · `cl` pl) + Verifikation + Widget-Vertrag unverändert **v2.7**. |

### ⚠⚠ NACHTRAG: der Schnelltakt hat um 21:30 selbst die Gegenprobe gefahren

Während dieses Laufs ist der Takt erneut gefeuert — und damit ist die Wirkungsprüfung
passiert, die oben ausdrücklich als *„nicht messbar"* offengelassen war.

| | |
|---|---|
| `SWR-167` | ✅ Das Log sagt **„Tick OHNE ERGEBNIS (status=fehler, artefakte=0)"** statt „Tick abgeschlossen". |
| `SWR-168` | ✅ Beide Repos stehen nach dem Tick auf `main`, sauber. Kein Branch-Rückfall. |
| `SWR-170` | ✅ Die neue Zeile steht in der Preflight-Ausgabe des Ticks selbst. |
| `SWR-169` | ⚠⚠ **Greift nicht.** Der Tick fragt weiter nach `llama3.1:8b`. |

**Die Ursache:** `pm/D010` hat den Takt **je Besetzung** entschieden (*platform/PROB*),
`ollama-schnelltakt.cmd` übergibt aber nur die **Einheit**. `waehle_ticket` zieht daraufhin
das nächste Ticket **jeder** aktiven KI-Rolle — gezogen wurden `CM@platform` und
`DEV@team-mail`, und für die steht im Register kein Modell.

> **⚠⚠ `SWR-169` ist richtig gebaut und in vier Gegenproben belegt — es bekommt Rolle und
> Einheit zur Laufzeit nur nie. Die Anforderung ist grün, die Wirkung ist null. Ohne den
> zufälligen Lauf um 21:30 hätte dieser Sprint „SWR-169 gebaut" berichtet und wäre damit
> durchgekommen.**

⚠ Und das ist ein Befund über **diesen Lauf**: alle vier Gegenproben zu `T-0032` prüften
die **Auflösungsfunktion**, keine ihren **Aufrufer**. *Eine Gegenprobe, die die Funktion
prüft und nicht ihren Aufrufer, misst die Hälfte, die man selbst geschrieben hat.*

Aufgenommen als **`platform/T-0033`** (`prio: kritisch`), **erster Punkt von Sprint 27**.
⚠ Bewusst **nicht** mehr hier gebaut: die Änderung greift in die alle 15 Minuten laufende
Automatik des Auftraggebers ein und trägt eine Entscheidung in sich.

## Sprint-Abschluss (Sprint 26, 2026-08-20)

**Geschlossen:** `platform/T-0031` und `platform/T-0032` (beide neu und geschlossen im
selben Lauf), `projects/p12/T-0012` (Entscheidung des Auftraggebers verbucht), dazu die
Reparatur des Tick-Schadens im `platform`-Repo.

**Neue Anforderungen:** **SWR-167** (Ergebniswort folgt dem Gateway-Status), **SWR-168**
(Branch-Rückkehr wird nachgeprüft), **SWR-169** (Modell aus dem Besetzungsregister),
**SWR-170** (Abweichung Register/Guardrails wird gemeldet).

**Neu angelegt:** `platform/T-0031`, `platform/T-0032`, `platform/T-0033` (Nachtrag,
`prio: kritisch`), `p9/T-0008` (DR, Frist 27.08., Default A).

**Briefe:** `p9/N-0001` und `promt-team/N-0002` — beide **während** des Laufs eingegangen
und im selben Lauf beantwortet.

**Verschoben:** `platform/T-0027` (3.), `platform/T-0030` (1.), `projects/p11/T-0016` (2.),
`promt-team/T-0008` (2. der neuen Fassung), `promt-team/T-0003` (2. mit dem richtigen
Grund), `pm/T-0071` (Bedingung nachgeschärft statt Grund wiederholt) — jede mit Grund
**im Ticket**.

**Verifikation:** **1236 Python-Tests** in der Sammlung (gemessen, **76** Testdateien),
Matrix **170 SWRs / 0 Lücken**, Briefkasten 0 offen (2 eingegangen, 2 beantwortet),
entschiedene unverbuchte DRs 0,
Parkplatz **10043**.

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

Ob ein Tick **nach** `SWR-169` ein brauchbares Artefakt liefert. Dazu muss einer laufen,
und dazu muss `gemma3:27b` auf dem Rechner des Auftraggebers installiert sein — von hier
aus **nicht messbar** (`L-2026-08-20ce`). Der Satz steht hier aus demselben Grund, aus dem
er in Sprint 25 stand: damit er nicht später als erledigt gilt, weil ihm niemand
widersprochen hat.

⚠ Und ein zweiter: dass `main` und `feature/t-0001-…` in `platform` divergiert sind, ist
**repariert, nicht aufgelöst** — der Branch steht weiterhin da, als Beleg. Ihn zu löschen
wäre Glätten; ihn zu mergen hieße, einen Commit aus einem Fehllauf in die Historie zu
holen. `SWR-168` sorgt dafür, dass kein neuer dazukommt.

---

# Anhang: Sprint 25

## Das Wichtigste (Sprint 25, 2026-08-20)

1. **⚠⚠ DER AUTO-PUSH-WÄCHTER WAR SEIT DREI TAGEN TOT, UND ES STAND DIE GANZE ZEIT IN
   ZWEI LOGDATEIEN.** Letzter erfolgreicher Lauf: **17.08. 11:32:30**. Seither **83
   Läufe, 83 Abbrüche**, nichts auf GitHub. Der **Ollama-Schnelltakt**, den der
   Auftraggeber selbst eingerichtet hat, lief **6-mal** und brach **alle 12** Ticks ab.
   > **Beide brechen ab, weil `preflight` Exit 1 liefert, solange irgendein Befund
   > dasteht — und vier Befunde sind Statusübergänge aus ABGESCHLOSSENEN Sprints, die
   > niemand mehr reparieren kann. Ein Wächter, der auf eine Tatsache blockiert, die
   > niemand mehr ändern kann, ist kein Wächter mehr, sondern ein Schalter, den jemand
   > umgelegt und niemand bemerkt hat.**

   ⚠ Gefunden hat es **kein Startcheck**, sondern die dritte Nachfrage des Auftraggebers.
   `SWR-166`, `platform/T-0029`, `L-2026-08-20cg`.
2. **⚠⚠ DIE REGEL DAGEGEN STAND SEIT SPRINT 9 IM SELBEN MODUL UND WIRD DORT ZWEIMAL
   ANGEWANDT.** Für den Altbestand vor dem Stichtag: *„wird GEMELDET und blockiert NICHT
   — kein Dauerbefund, der das Wegsehen trainiert."* Für die Uhrenprobe: *„nicht
   reparierbar … das hieße das Wegsehen zu trainieren."* An der dritten Stelle nicht.
   > **Das ist B033 — nur ist die vergessene Kopie diesmal keine Codestelle, sondern eine
   > BEGRÜNDUNG.**

   ⚠ Der Stichtag ist **nicht** verschoben (`ALTBESTAND_ERWARTET` bleibt 56), es entsteht
   **kein** Register von Einzelfällen, und die vier Fälle stehen weiterhin **namentlich
   und mit Commit** in jeder Preflight-Ausgabe. Geändert hat sich nur, wen sie stoppen.
3. **⚠⚠ DER AUFTRAGGEBER HATTE RECHT, UND DER GEGENBEWEIS LAG IN UNSEREM EIGENEN COMMIT.**
   `team-mail/N-0004`: *„sowohl OLAMA wie IMAP ist eingerichtet und funktioniert."* Commit
   **`70d5aa1`** (16:01:05) trägt den Tages-Digest vom 20.08. (26 Mails, lokales Ollama),
   231 Zeilen IMAP-Rohdaten **und** den Absatz *„Gesetzte `MAIL_IMAP_*`-Variablen: 0 —
   erneut GEMESSEN, nicht angenommen"*. Eine Sekunde später ging derselbe Satz in den Plan.
   > **Die Zahl stimmte. Gemessen wurde in der Cowork-SANDBOX, wo sie nicht anders
   > ausfallen kann. Eine Umgebungsmessung gilt für die Maschine, auf der sie lief — und
   > in der Angabe stand nur die Zahl, nie der Ort.**

   `L-2026-08-20ce`. Drei Sprints lang hat das Wort „gemessen" genau das getan, wogegen es
   eingeführt wurde: die Prüfung beendet.
4. **✅ `p12/T-0011` BEI DER FÜNFTEN BERÜHRUNG GELIEFERT — und der Grund war nie
   Kapazität.** Fünfmal terminiert, fünfmal „keine Zeit", fünfmal wahr. Darin steckte eine
   **Entscheidung**, die niemandem vorgelegt worden ist. Fällig war etwas Kleineres:
   `RohtextAnsichtTest` maß, **wie viele** Rohtext-Ansichten es gibt, nicht **welche** —
   ein Tausch wäre grün geblieben. Gebaut (`ROHTEXT_STELLEN`, vier Ansichten einzeln
   benannt), Rest als `p12/T-0012` **gefragt** statt ein sechstes Mal terminiert.
   `L-2026-08-20ch`.
5. **⚠⚠ ZUM VIERTEN LAUF IN FOLGE HAT EIN WERKZEUG DEN FRISCHEN ENTWURF VERWORFEN — UND
   DIESMAL ZWEIMAL IN EINEM LAUF.** `board.py` wies `p12/T-0012` ab und widerlegte damit
   dessen eigenen Satz, es gehe *nicht* in die Inbox. `test_konsole` fand
   `scripts/organigramm.py` aus dem Orga-Rework als **Einstiegspunkt ohne
   `konsole.sichere_ausgabe()`**. Und der **Preflight** widerlegte denselben DR ein zweites
   Mal: ohne `frist` ist er ein unterminiertes Ticket — **dreimal in einem Lauf**.
   > **Beide Entwürfe waren plausibel, und kein Mensch hat sie beim Lesen bemerkt.**

   `L-2026-08-20cf`.
6. **✅ Die Arbeit der Vorsession war fertig und stand nicht in Git** — 60 Dateien aus dem
   Orga-Rework (`pm/T-0070/T-0072`, `platform/T-0028`). Erst gegen die Werkzeuge
   verifiziert (`organigramm --check` grün, 8/8), dann nachverbucht (B025). ⚠ Genau das
   hat den Wächter zusätzlich blockiert.
7. **1219 Python-Tests** (über die Sammlung **gemessen**, **74** Testdateien) + **42**
   `produkt-datakonv`, **111 JS-Tests grün**, Matrix **166 SWRs / 0 Lücken**, Briefkasten
   **0 offen**. ✅ **`PREFLIGHT: STARTKLAR (5 fortgeschrieben)`** — zum ersten Mal seit
   dem 17.08.
   ⚠ Die vier Statusübergänge sind **nicht verschwunden**: sie stehen namentlich in der
   Ausgabe und in der Schlusszeile. Dieser Lauf hat **keinen neuen** hinzugefügt.
8. **Parkplatz `verwaiste-locks`: 9754** (Sprint 24: 9506) — gemeldet, **kein Befund**,
   Momentaufnahme.

## Sprint-Plan (Sprint 25)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| team-mail/N-0004 · platform/N-0007 | pl | Sprint 25 | **erledigt** | ✅ Briefkasten zuerst: beide beantwortet und sofort committet. N-0004 → `platform/T-0029`, N-0007 → `platform/T-0030`. |
| platform/T-0029 | cm | Sprint 25 | **erledigt** | ✅ **Neu und geschlossen im selben Lauf** (`prio: kritisch`). **SWR-166**: blockierende vs. fortgeschriebene Befunde. Nachweis am echten System: STARTKLAR, die vier Übergänge weiterhin namentlich. |
| projects/p12/T-0011 | pl | Sprint 25 | **erledigt** | ✅ **FÜNFTE Berührung: geliefert.** Die Prüfung nennt jetzt **DIESE vier** Ansichten. Rest als DR `p12/T-0012` gestellt statt terminiert. |
| Orga-Rework-Nachverbuchung | cm | Sprint 25 | **erledigt** | ✅ 60 Dateien der Vorsession gegen die Werkzeuge verifiziert und in 16 Repos nachverbucht. |
| pm/T-0071 | pl | Sprint 26 | offen | ✅ Schritt 1 (Mensch) erledigt, Schritt 2 **gemessen**: 6 Läufe, 12 Ticks, **0 durchgelaufen**. Ursache gefunden und behoben. ⚠ Schritt 3 (Wirkung) beginnt erst mit dem ersten wirklich gelaufenen Tick — **kein `blocked`, kein „wartet auf dich“**, sondern Betriebszeit. |
| team-mail/T-0001 | dev | jeder Sprint | offen (Takt) | ⚠ **Wartegrund korrigiert, nicht der Zustand.** Der Digest vom 20.08. existiert (manueller Lauf des Auftraggebers). Kein „wartet auf Umgebung" mehr. |
| promt-team/T-0003 | dev | Sprint 26 | offen | ⚠ **Erste Terminierung mit dem RICHTIGEN Grund** — der alte („wartet auf Umgebung") ist widerlegt. Bedingung: ein durchgelaufener Tick. |
| promt-team/T-0008 | test | Sprint 26 | offen | ⚠ **1. Verschiebung der neuen Fassung.** Grund **gemessen**: 0 durchgelaufene Ticks über alle Rollen — die Prüfung wäre auf leerer Grundmenge grün (SWR-128). Kein `blocked`. |
| platform/T-0027 | cm | Sprint 26 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Dieser Lauf lieferte **zwei** weitere Belege: die Parkplatzzahl 9506→9754 (gemessen, aber ohne Zeitpunkt) und eine neue Rubrik — *gemessen ohne Angabe, WO*. ⚠ Beim vierten Mal gilt: gebaut oder geschnitten. |
| projects/p11/T-0016 | dev | Sprint 26 | offen | ⚠ **1. Verschiebung**, Grund: Kapazität. Umfang unverändert **gezählt** (4 Bausteine, 11 von 111 JS-Zusicherungen). |
| platform/T-0030 | dev | Sprint 26 | offen | ⚠ **0. Verschiebung.** Zuschnitt fertig, Bau nicht. Reihenfolge wie B039: erst der Weg nach außen, dann neue Fläche. |
| projects/p12/T-0012 | mensch | Frist 27.08. | offen | ⚠ **Neu, Klasse C, drei Optionen, Default A = heutiger Zustand.** Liegt in der Inbox. ⚠ Der fristlose Entwurf ist vom Preflight widerlegt worden — *eine Frage ohne Frist ist eine, deren Ausgang niemand aufgeschrieben hat*. Schweigen kostet trotzdem nichts: A ist der Ist-Zustand. |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**vier**: `ce` `cg` cm · `cf` test · `ch` pl) + Verifikation + Widget-Vertrag unverändert **v2.7**. |

## Sprint-Abschluss (Sprint 25, 2026-08-20)

**Geschlossen:** `platform/T-0029` (neu und geschlossen im selben Lauf), `projects/p12/T-0011`
(fünfte Berührung), dazu die Nachverbuchung des Orga-Reworks in 16 Repos und zwei Briefe.

**Neue Anforderung:** **SWR-166** — `reviewed` mit Nachweis und mit gefahrener Gegenprobe.

**Neu angelegt:** `platform/T-0029`, `platform/T-0030`, `projects/p12/T-0012` (DR).

**Verschoben:** `platform/T-0027` (2.), `projects/p11/T-0016` (1.), `promt-team/T-0008` (1.
der neuen Fassung), `promt-team/T-0003` (erste Terminierung mit dem richtigen Grund),
`platform/T-0030` (0.) — jede mit Grund **im Ticket**.

**Verifikation:** **1219 Python-Tests** (über die Sammlung gemessen, **74** Testdateien) +
**42** `produkt-datakonv`, **111 JS-Tests grün**, Matrix **166 SWRs / 0 Lücken**,
Briefkasten 0 offen, entschiedene unverbuchte DRs 0, Pflichtartefakte 0 fehlend,
Decision-Log gegen Ticketmarker 0, Plan-/Statusdrift 0, Parkplatz **9754** (kein Befund).

✅ **`PREFLIGHT: STARTKLAR (5 fortgeschrieben)`.** ⚠ Die 5 sind die vier Statusübergänge aus
abgeschlossenen Sprints und die Pause seit Sprint 24 — **gemeldet, namentlich, mit Commit**,
und ausdrücklich nicht geglättet.

### ⚠ Zwei Zusicherungen sind GESCHÄRFT worden, keine gelöscht

1. `test_seit_dem_stichtag_gibt_es_keinen_verstoss` stand **seit dem 17.08. rot** und
   musste es bleiben — ihr Gegenstand kann sich nicht mehr ändern. Sie fragt jetzt nach dem
   **laufenden** Sprint; was sie vorher zusicherte, sichert ihr Nachbar zu
   (`test_die_fortgeschriebenen_verschwinden_dabei_nicht`).
2. `test_der_ausfall_wird_ein_befund_mit_zahl_und_zeitraum` prüfte auf das Wort `BEFUND`.
   Der Gegenstand war *„mit Zahl und Zeitraum genannt"* — das prüft sie weiter, dazu die
   neue Marke, und ihr Nachbar prüft, dass die Pause im Fortgeschrieben-**Zähler** landet.

> **Ein Test, der rot ist und rot bleiben muss, sagt nichts mehr. Ihn zu löschen wäre
> Glätten, ihn stehenzulassen war drei Tage Stillstand. Verschoben wird sein Gegenstand,
> und der Nachbar hält fest, was er vorher hielt.**

### ⚠ Was dieser Lauf ausdrücklich NICHT gemessen hat

Ob ein Tick nach dem Entsperren inhaltlich etwas Sinnvolles tut. Es ist **nie einer
gelaufen**. Der Satz steht hier, damit er nicht später als erledigt gilt, weil ihm niemand
widersprochen hat.

---

# Anhang: Sprint 24

## Das Wichtigste (Sprint 24, 2026-08-20)

1. **✅ DREIMAL DIE REGEL DER VIERTEN BERÜHRUNG ANGEWANDT — UND DREIMAL GEBAUT.**
   `p11/T-0015` (Rückbau), `platform/T-0021` (Git-Sperre), `platform/T-0022` (Frage 1)
   standen alle bei der **vierten** Berührung. Keines ist ein viertes Mal verschoben
   worden.
   > **Drei Tickets, die zusammen zehn Verschiebungen trugen, in einem Lauf geschlossen.
   > Der Grund war jedes Mal derselbe und jedes Mal richtig: „Kapazität". Er wird nicht
   > falsch, wenn man ihn viermal aufschreibt — er hört nur auf, eine Aussage zu sein.**
2. **✅ DER RÜCKBAU IST DURCH, UND SEINE TEUERSTE STELLE WAR DIE, AN DER NICHTS ZU TUN
   WAR.** `p11/T-0015`: `/api/dashboard`, `aggregation.dashboard` und `KACHEL_FELDER` sind
   weg, **SWR-135 auf die Layout-Hälfte zurückgeschnitten** (v1.61). Der erste Entwurf des
   Wächters prüfte nur, was **fehlt**.
   > **⚠⚠ Eine Prüfung, die nur Abwesenheit misst, ist nach einem Kahlschlag ebenfalls
   > grün. `_zustand` und `zustaende_von` sehen aus wie Dashboard-Code und tragen seit
   > SWR-146 den `zustaende`-Block des COCKPITS.**

   Der Wächter ist deshalb ein **Paar**: neben jedes „das ist weg" gehört ein „und das ist
   noch da", mit echter Auswertung. `L-2026-08-20by`.
3. **⚠⚠ DIE MESSUNG ZU `platform/T-0021` HAT DEN TITEL DES TICKETS WIDERLEGT.** Die
   `tmp_obj`-Reste, nach denen es benannt ist, sind **Müll und keine Sperre** (ein Commit
   lief mit fünf `unlink`-Warnungen und **Exit 0** durch). Die Sperre, die tötet, ist
   `index.lock` — und sie wird vom **gelingenden** Aufruf hinterlassen.

   | Aufruf | Exit | Sperre bleibt liegen |
   |---|---|---|
   | `git status --porcelain` | **0** | **JA** |
   | `git add`, `git commit`, `git log`, `git diff` | 0 | nein |

   > **Git beendet einen SCHREIBENDEN Indexvorgang durch Umbenennen — das geht durch.
   > Einen bloß LESENDEN Refresh beendet es durch LÖSCHEN — und das ist hier verboten. Der
   > harmlose Lesevorgang hinterlässt die Sperre, an der der nächste Aufruf stirbt.**

   ⚠ Damit war **Frage 2 des Tickets falsch gestellt** („nach dem Commit räumen?" — nach
   dem Commit ist nichts zu räumen), und der Rückfall aus **SWR-134** sah drei Sprints lang
   wie die Lösung aus: er repariert den Aufruf, der **gescheitert** ist, und verlegt die
   Kosten auf den nächsten. **SWR-163**, `L-2026-08-20bx`.
4. **✅ Frage 3 desselben Tickets ist beantwortet und die Antwort ist ja — SWR-164.** Der
   Parkplatz `verwaiste-locks` wächst unbegrenzt, weil die erste Räumstufe (`os.remove`)
   auf diesem Mount **immer** scheitert: **1975** (Sprint 21) → **2099** (heute) allein in
   `pm`, **9506** über alle Repos (gemessen am Ende dieses Laufs). ⚠ Die Zahl ist eine
   **Momentaufnahme und keine Konstante**: sie wächst mit jedem Commit — allein dieser Lauf
   hat sie um rund 170 erhöht. Genau deshalb prüft die Zusicherung daneben eine
   **Größenordnung** und keine feste Zahl (der Fehler aus SWR-157).
   ⚠ Die Zeile ist ausdrücklich **kein Befund**: reparierbar ist das von hier aus nicht,
   was fehlte, war die **Messung**. Eine ungemessene Größe ist von einer, die nicht wächst,
   nicht zu unterscheiden.
5. **⚠⚠ DER GRÖSSTE BEFUND DIESES LAUFS IST WIEDER EINER ÜBER SICH SELBST — UND WIEDER HAT
   IHN EINE ALTE ZUSICHERUNG GEFUNDEN.** `SWR-165` verlangt wörtlich, der Rumpfmarker
   stehe an **einer** Stelle. Ihr erster Entwurf legte eine **zweite** Konstante an.
   > **Rot gemacht hat das nicht der Autor, sondern ein Zähltest aus Sprint 17, der nichts
   > tut, als zu zählen, in wie vielen Dateien ein Literal vorkommt. Zum ZWEITEN Lauf in
   > Folge hat eine ältere Zusicherung den eigenen Entwurf verworfen** (Sprint 23:
   > SWR-134 gegen die Uhrenprobe).

   `L-2026-08-20cd`. ⚠ Das ist das Argument dafür, Zähltests zu behalten, auch wenn sie
   pedantisch wirken.
6. **✅ `platform/T-0022` ist nach drei Verschiebungen GANZ geschlossen — SWR-165.** Die
   drei Schreibvorgänge von `inbox.entscheide` sind **gezählt**, und die Zählung hat die
   Frage umgestellt: nicht die Reihenfolge ist offen, sondern **welche Lücke die schlimmere
   ist**. Es ist die zwischen dem **ersten** und dem **zweiten** Schreibvorgang.
   > **Eine Entscheidung, die protokolliert ist und im Ticket unsichtbar bleibt, ist
   > schlimmer als eine, die gar nicht ankam: die eine merkt der Mensch, die andere nicht.**

   ⚠ Gebaut ist eine **Prüfung** und **kein Umbau** des Schreibwegs — ein Bau am Schreibpfad
   einer Klasse-A-Entscheidung verlangt eine Aussage über den Teilausfall, und die Frage ist
   niemandem gestellt worden. Gemessen: 93 Logzeilen, 46 von der Inbox, **0** ohne Marker.
7. **✅ Eine Entscheidung, die eine fünfte Terminierung ersetzt hat.** `promt-team/T-0010`
   → **Klasse C, PL**: (a) *je Sprint eine Rolle aufrufen* und (b) *Übungsläufe* sind
   verworfen, weil beide einen Lauf **um der Messung willen** erzeugen.
   > **Ein Goldset folgt dem Betrieb. Es geht nicht voran und es wird nicht nachgeholt.**

   `promt-team/T-0008` ist deshalb **umgeschnitten** statt geschnitten: nicht *„zehn Rollen
   vermessen"*, sondern *„bemerken, wenn eine Rolle vermessbar wird"* — mit Prüfung, weil
   eine Regel ohne Vertreter keine drei Sprints hält. `blocked_by` entfällt.
   `L-2026-08-20cb`.
8. **⚠ ACHTER geschätzter Wert — und er stand unter einer Überschrift, die „gezählt, nicht
   übersehen" heißt.** Der Abschluss von `p11/T-0015` nannte **9** betroffene
   JS-Zusicherungen; gemessen sind es **11**. ⚠ Und dieser Fall widerlegt einen
   naheliegenden Zuschnitt von `platform/T-0027`: die dort genannten fünf Rubriken hätten
   ihn **nicht** gefunden, und eine Schablone auch nicht — die Zahl stand in Fließtext.
   Gefunden hat sie ein **Skript**. `L-2026-08-20cc`.
9. **1201 Python-Tests** (über die Sammlung **gemessen**, **72** Testdateien), **111
   JS-Tests grün**, Matrix **165 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene
   unverbuchte DRs **0**, Pflichtartefakte **0** fehlend, Decision-Log gegen Ticketmarker
   **0**.
   ⚠ **Nicht startklar:** der Altbefund über vier Statusübergänge (drei aus den Sprints
   13/15, einer aus Sprint 23) steht **unverändert**. Dieser Lauf hat **keinen** neuen
   hinzugefügt.
10. **Sechs Tickets geschlossen** (`p11/T-0015`, `p11/T-0003`, `platform/T-0021`,
    `platform/T-0022`, `promt-team/T-0010` — und `promt-team/T-0008` **entsperrt und
    umgeschnitten**), **eines neu** (`p11/T-0016`), **drei Anforderungen** (SWR-163, 164,
    165), **eine Entscheidung** (Klasse C), **sieben Lessons**.
    ⚠ **Nichts liegt beim Menschen** — dieser Lauf hat nichts vorzulegen.

## Sprint-Plan (Sprint 24)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| projects/p11/T-0015 | dev | Sprint 24 | **erledigt** | ✅ **Vierte Berührung: gebaut.** Kachelhälfte zurückgebaut, SWR-135 auf die Layout-Hälfte (v1.61), Teststrecke **umgedreht** statt gelöscht. |
| projects/p11/T-0003 | pl | Sprint 24 | **erledigt** | ✅ Klammer geschlossen — letzter Teil (`T-0015`) gebaut. ⚠ Zum **dritten** Mal in Folge vom PM nachgezogen, nicht vom Preflight. |
| platform/T-0021 | cm | Sprint 24 | **erledigt** | ✅ **Vierte Berührung: gebaut.** **SWR-163** (der gelingende Aufruf räumt hinter sich her) + **SWR-164** (Parkplatz gemessen). Fragen 2 und 3 beantwortet, Frage 2 als **falsch gestellt** erkannt. |
| platform/T-0022 | dev | Sprint 24 | **erledigt** | ✅ **Vierte Berührung: gebaut.** Frage 1 gezählt → **SWR-165**. Alle drei Fragen des Tickets beantwortet (SWR-152 / SWR-161 / SWR-165). |
| promt-team/T-0010 | dev | Sprint 24 | **erledigt** | ✅ **Frage 1 entschieden** (Klasse C, PL). (a) und (b) verworfen, (c) als **Umkehrung** statt als Schnitt. |
| promt-team/T-0008 | test | Sprint 25 | offen | ✅ **Entsperrt und umgeschnitten** statt ein fünftes Mal terminiert. Neue DoD: Regel + **Prüfung**. `blocked_by` leer. **Nullte Terminierung der neuen Fassung.** |
| projects/p11/T-0016 | dev | Sprint 25 | offen | ⚠ **Neu, 0. Verschiebung.** Die Frontend-Hälfte des Rückbaus — **gezählt** (4 Bausteine, 11 von 111 JS-Zusicherungen) und bewusst **nicht** mitgenommen. |
| platform/T-0027 | cm | Sprint 25 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. ⚠ Dieser Lauf hat den **achten** Beleg geliefert **und zwei Argumente für den Zuschnitt**: die fünf genannten Rubriken hätten ihn nicht gefunden, und eine Schablone auch nicht. |
| projects/p12/T-0011 | pl | Sprint 25 | offen | ⚠⚠ **4. Verschiebung — die Regel der vierten Berührung ist hier ÜBERZOGEN.** Sie ist in diesem Lauf dreimal angewandt und einmal nicht. **In Sprint 25 ist dieses Ticket das erste, nicht das letzte.** |
| promt-team/T-0003 | dev | wartet-auf-Umgebung | offen | ⚠ Erneut **gemessen**: `which ollama` leer, `localhost:11434` ohne Antwort. **Kein „wartet auf dich".** |
| team-mail/T-0001 | dev | wartet-auf-Umgebung | offen | ⚠ Erneut **gemessen**: **0** `MAIL_IMAP_*` gesetzt. **Kein „wartet auf dich".** |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat: verworfen und als solche geführt. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**sieben**: `bx` `by` `cc` cm · `bz` `cd` test · `ca` `cb` pl) + Verifikation + Widget-Vertrag unverändert **v2.7**. |

## Sprint-Abschluss (Sprint 24, 2026-08-20)

**Geschlossen:** `projects/p11/T-0015` (vierte Berührung), `projects/p11/T-0003` (Klammer),
`platform/T-0021` (vierte Berührung), `platform/T-0022` (vierte Berührung, alle drei Fragen),
`promt-team/T-0010` (Entscheidung).

**Neue Anforderungen:** **SWR-163, SWR-164, SWR-165** — alle drei `reviewed` mit Nachweis.
**Geändert: SWR-135** auf die Layout-Hälfte zurückgeschnitten (v1.61) — *eine abgenommene
Anforderung wird geändert, und das ist dokumentiert, nicht stillschweigend getan.*

**Neu angelegt:** `projects/p11/T-0016` (die Frontend-Hälfte des Rückbaus, gezählt).
**Umgeschnitten statt terminiert:** `promt-team/T-0008` (entsperrt, neue DoD).

**Verschoben:** `platform/T-0027` (1.), `projects/p12/T-0011` (**4.**) — beide mit Grund im
Ticket.

**Verifikation:** **1201 Python-Tests** (über die Sammlung **gemessen**, **72**
Testdateien), **111 JS-Tests grün**, Matrix **165 SWRs / 0 Lücken**, Briefkasten 0 offen,
entschiedene unverbuchte DRs 0, Pflichtartefakte 0 fehlend, Decision-Log gegen Ticketmarker
0, Parkplatz **9506** am Ende des Laufs (gemeldet, **kein Befund**; die Zahl ist eine
Momentaufnahme und wächst mit jedem Commit).

⚠ **Nicht startklar:** der Altbefund über **vier** Statusübergänge steht unverändert. ✅
**Dieser Lauf hat keinen neuen hinzugefügt** — zum ersten Mal seit Sprint 22 wächst die
Zahl nicht.

### ✅ Ein Widerspruch in der eigenen Schlussmessung — und er ist aufgelöst

Die Schlussverifikation lieferte **zwei** Zahlen für dieselbe Sache: die Sammlung meldete
**1201** Tests, die Summe der gefahrenen Blöcke **1208**.

Die Ursache war eine **veraltete Stapelliste**: die Blöcke waren nach Dateiindex
geschnitten, und dieser Lauf hat *währenddessen* zwei Testdateien angelegt — eine Datei lief
dadurch in zwei Blöcken.

> **Gefunden hat das nicht die Sorgfalt, sondern der Widerspruch zwischen zwei unabhängigen
> Messungen derselben Größe. Eine allein wäre unwidersprochen geblieben.**

⚠ Nachgerechnet über neu geschnittene, überschneidungsfreie Blöcke:
**387 + 288 + 384 + 122 + 20 = 1201**, deckungsgleich mit der Sammlung. Alle Blöcke grün
bis auf den einen bekannten Altbefund.

⚠ Das ist im selben Zug ein **Argument für den Zuschnitt von `platform/T-0027`**: eine
Prüfung, die die Berichtszahl gegen **eine** Quelle hält, hätte hier nichts gemerkt — beide
Zahlen waren korrekt erhoben, nur über verschiedene Mengen.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Zum zweiten Lauf in Folge hat eine **ältere Zusicherung** den eigenen Entwurf verworfen —
und zum zweiten Mal war es eine, die für sich genommen pedantisch aussieht.

> **Ein Zähltest über ein Literal prüft nichts über das Verhalten und alles über die
> Bauart. Wer ihn beim Aufräumen entfernt, weil er „nichts testet", entfernt genau den
> Wächter, der in zwei aufeinanderfolgenden Läufen zugeschlagen hat.**

### ⚠ Und der achte geschätzte Wert stand in einer Überschrift, die das Gegenteil verspricht

*„Was dieser Rückbau NICHT angefasst hat — gezählt, nicht übersehen"*: darunter stand
**9**, gemessen sind es **11**. Korrigiert vor dem Leser, gefunden durch Nachzählen und
nicht durch eine Prüfung. **Achter Fall in sieben Sprints.**


---

# Anhang: Sprint 23 (2026-08-20, abgeschlossen)

## Das Wichtigste (Sprint 23, 2026-08-20)

1. **✅ DAS TICKET, DAS VIER SPRINTS LANG NUR VERSCHOBEN WURDE, IST GEBAUT.**
   `platform/T-0020` → **SWR-158**: der Matrix-Generator liest seinen **Vorgänger**,
   bevor er ihn ersetzt. Verglichen wird an **IDs**, es gibt **kein Flag**, und bei einer
   verschwundenen ID wird **nichts geschrieben**.
   > **Der Schaden von Sprint 17 lebte und starb in einer Arbeitskopie. Eine Warnung nach
   > dem Schreiben hätte ihn gemeldet und trotzdem angerichtet.**
2. **✅ Die negative Pause ist gemessen — und das Ticket verdächtigte die falsche Zeile.**
   `platform/T-0026` → **SWR-159**. Über alle 31 Registerereignisse: sechs reguläre `ende`
   bei **+0,6 bis +1,1 Min**, der dokumentierte Nachtrag bei **+21,3**, und **eines bei
   −37,4**. Commit `911e57a` von **16:32:36** trägt die Zeile `"ende": "17:10"`.
   > **⚠⚠ Kein Prozess kann 38 Minuten vor seiner eigenen Uhr liegen. Nicht der START von
   > Sprint 17 ist falsch, sondern das ENDE von Sprint 16.**

   ⚠ Zwei der drei Hypothesen fallen am **Vorzeichen** und an der **Größe**: ein Nachtrag
   liefert einen positiven Abstand, ein Zonenversatz ein Vielfaches von 15 Minuten.
   ⚠ Die im Ticket vorgeschlagene Abhilfe (Register mit Offset) hätte den Fall **nicht
   gefunden** — beide Commits tragen `+02:00`. Deshalb **nicht gebaut**. `L-2026-08-20br`.
3. **✅ Zwei Tickets bei der VIERTEN Berührung — mit verschiedenem Ausgang, und das ist
   die Lehre.** `p11/T-0013` wartete auf **Kapazität** → **gebaut** (SWR-160, Widget-Inhalt
   hinter dem PIN-Lesegate). `promt-team/T-0008` wartete auf eine **Tatsache** → **`blocked`**
   mit eigenem Vorbedingungsticket.
   > **Ein Ticket viermal auf „Kapazität" zu terminieren, während es auf etwas wartet, das
   > kein Lauf herstellt, indem er das Ticket anfasst, heißt den Grund viermal falsch
   > aufzuschreiben.** `L-2026-08-20bv`.
4. **⚠⚠ DER GRÖSSTE BEFUND DIESES LAUFS IST DURCH EINEN EIGENEN FEHLER ANS LICHT
   GEKOMMEN.** Dieser Lauf hat `p11/T-0009` von `in_progress` direkt auf `done` gebucht —
   verboten seit Sprint 1. Die Frage *„warum ist dabei nichts rot geworden?"* ergab:
   **die Übergangsprüfung hat `projects/` (p10, p11, p12) seit Sprint 9 NIE angesehen.**
   **66 Statuswechsel ungeprüft**, darin vier Altfälle und der eigene.
   > **Zwei unabhängige Ursachen, beide für sich plausibel: ein übersprungener Zweig,
   > dessen KOMMENTAR das Gegenteil sagte, und ein Pfadfilter relativ zur Repo-Wurzel.**

   Repariert als **SWR-162**, Altbestand **52 → 56**. ⚠ Der eigene Verstoß wird **nicht
   geglättet**: er ist ab jetzt der **vierte** stehende Befund und der einzige, der diesem
   Lauf gehört. `L-2026-08-20bs`, `L-2026-08-20bw`.
5. **✅ Zum dritten Mal in zwei Läufen hat die Zählung vor der Reparatur den Ertrag
   geliefert — und zum dritten Mal fiel sie KLEINER aus als die Vermutung.**
   `platform/T-0022` Fragen 2+3 → **SWR-161**: von **sechs** Pflichtartefakten des
   Gründungswegs fehlte über 17 Repos genau **eines** (`platform` hatte kein
   Entscheidungslog), vier fehlten **nirgends**.
   > **Und die Antwort auf Frage 3 ist gemessen: der selbstheilende Weg aus SWR-152 hat
   > GENAU das Repo geheilt, in das jemand hineingelaufen ist. Den Mangel, in den noch
   > niemand gelaufen ist, findet nur eine Prüfung, die alle Repos durchgeht.**
6. **⚠ Eine Zusicherung aus Sprint 16 hat den eigenen Entwurf verworfen.** Die Uhrenprobe
   rief zuerst `git` **im Sprintzähler** auf — und wurde rot an
   `test_die_messung_ruft_KEIN_git_auf` (SWR-134): auf diesem Mount hinterlässt schon ein
   **lesender** Git-Aufruf eine Sperre.
   > **Eine Prüfung, die Uneinigkeit zwischen zwei Läufen erkennen soll und dabei selbst
   > sperrt, ist ihr eigener Schadensfall.** Nicht die Zusicherung wurde aufgeweicht,
   > sondern Material und Regel getrennt. `L-2026-08-20bt`.
7. **⚠ Und eine Zahl in diesem Lauf war ZUM SECHSTEN MAL geschätzt statt gemessen** — im
   Kommentar der eigenen Reparatur („kostet rund 2 s"; gemessen: 10 s → 36 s über alle
   Repos). ⚠ **Im selben Lauf, in dem `platform/T-0027` genau dafür aufgemacht wurde.**
8. **1185 Python-Tests** (über die Sammlung **gemessen**, **70** Testdateien), **111
   JS-Tests grün**, Matrix **162 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene
   unverbuchte DRs **0**, Plan-Drift **0**, Statusdrift **0**.
   ⚠ **Nicht startklar:** der Altbefund aus den Sprints 13/15 (**unverändert**) **plus
   ein neuer aus diesem Lauf**. Nichts geglättet.

## Sprint-Plan (Sprint 23)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0020 | cm | Sprint 23 | **erledigt** | ✅ **SWR-158**, bei der fünften Berührung gebaut. ID-Vergleich gegen den Bestand, kein Flag, es wird nichts geschrieben. Frage 3 **abgetrennt** als `T-0027`. |
| platform/T-0026 | cm | Sprint 23 | **erledigt** | ✅ **SWR-159**, nullte Verschiebung eingehalten. Die Messung dreht die Vermutung des Tickets um; der Offset-Vorschlag ist **verworfen**, weil er den Fall nicht fände. |
| projects/p11/T-0013 | dev | Sprint 23 | **erledigt** | ✅ **SWR-160**, **vierte Berührung: gebaut**. Inhalt hinter dem PIN-Lesegate, Kachel bleibt sichtbar, Vertrag **v2.7**. |
| projects/p11/T-0009 | dev | Sprint 23 | **erledigt** | ✅ Klammer über `T-0012` (SWR-150) und `T-0013` (SWR-160). ⚠ **Fehlerhaft gebucht** — siehe unten. |
| platform/T-0022 | dev | Sprint 24 | offen | ✅ Fragen **2+3 beantwortet und gebaut** (SWR-161). ⚠ **Dritte Verschiebung, nur noch Frage 1** (Reihenfolge der drei Schreibvorgänge) — ein Bau am Schreibweg einer Klasse-A-Entscheidung, Grund im Ticket. |
| platform/T-0021 | cm | Sprint 24 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. In diesem Lauf **erneut in Produktion getroffen** (drei Commits, jedes Mal mit `--nur-locks` umgangen). Neue Auflage aus SWR-159 im Ticket vermerkt. |
| platform/T-0027 | cm | Sprint 24 | offen | ⚠ **Neu, 0. Verschiebung.** Der Abschlussbericht ohne Prüfung für die eigenen Kennzahlen — **sechster** Beleg, einer davon aus diesem Lauf. |
| projects/p11/T-0015 | dev | Sprint 24 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Bei der **vierten** Berührung: gebaut oder geschnitten. |
| projects/p12/T-0011 | pl | Sprint 24 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. SWR-162 hat in diesem Lauf **belegt**, was ein Nachweis über den falschen Bestand kostet. |
| promt-team/T-0008 | test | Sprint 24 | **blocked** | ⚠ **Vierte Berührung, kein vierter Termin.** Gemessen: 0 Läufe für zehn Rollen, unverändert seit Sprint 18. `blocked_by: [T-0010]`. |
| promt-team/T-0010 | dev | Sprint 24 | offen | ⚠ **Neu, 0. Verschiebung.** Die Vorbedingung: Läufe je Rolle. ⚠ Drei Ausgänge, einer davon schafft `T-0008` ab. |
| promt-team/T-0003 | dev | wartet-auf-Umgebung | offen | ⚠ Wartet auf **Ollama** — in diesem Lauf erneut gemessen: `which ollama` leer, `localhost:11434` ohne Antwort. **Kein „wartet auf dich".** |
| team-mail/T-0001 | dev | wartet-auf-Umgebung | offen | ⚠ Wartet auf **Mail-Zugangsdaten** — gemessen: **0** `MAIL_IMAP_*` gesetzt. **Kein „wartet auf dich".** |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0015`; offen ist **nur noch `T-0015`**. ✅ Zum zweiten Mal in Folge vom PM nachgezogen, nicht vom Preflight. |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat: verworfen und als solche geführt. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (**sechs**: `br` `bs` cm · `bt` `bu` test · `bv` `bw` pl) + Verifikation + Widget-Vertrag auf **v2.7** nachgezogen. |

## Sprint-Abschluss (Sprint 23, 2026-08-20)

**Geschlossen:** `platform/T-0020` (nach vier Verschiebungen), `platform/T-0026` (nullte
Verschiebung gehalten), `projects/p11/T-0013` (vierte Berührung) und die Klammer
`projects/p11/T-0009`.

**Neue Anforderungen:** **SWR-158, SWR-159, SWR-160, SWR-161, SWR-162** — alle fünf
`reviewed` mit Nachweis. Widget-Vertrag **v2.7**.

**Neu angelegt:** `platform/T-0027` (der Abschlussbericht ohne eigene Prüfung),
`promt-team/T-0010` (Läufe je Rolle).

**Verschoben:** `platform/T-0021` (3.), `platform/T-0022` (3., nur noch Frage 1),
`p11/T-0015` (3.), `p12/T-0011` (3.) — **alle mit Grund im Ticket**.
**Blockiert statt verschoben:** `promt-team/T-0008`, mit gemessener Bedingung.

**Verifikation:** **1185 Python-Tests** (über die Sammlung **gemessen**, 70 Testdateien),
**111 JS-Tests grün**, Matrix **162 SWRs / 0 Lücken**, Briefkasten 0 offen, entschiedene
unverbuchte DRs 0, Plan-Drift 0, Statusdrift 0, Pflichtartefakte 0 fehlend.

⚠ **Nicht startklar, und zum ersten Mal seit vielen Läufen mit einem Befund MEHR:**
der Altbefund über drei Statusübergänge aus den Sprints 13/15 steht unverändert, **und
dieser Lauf hat einen vierten hinzugefügt** (`p11/T-0009`, `in_progress → done`).

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Der eigene Buchungsfehler war die billigste Sonde, die dieser Lauf bekommen konnte.

> **Ein eigener Fehler an einer geprüften Stelle ist ein kostenloser Test der Prüfung.
> Wer ihn schnell wegräumt, bezahlt mit der Antwort auf die einzige interessante Frage —
> und die Antwort war hier, dass die Prüfung seit Sprint 9 ein Drittel des Bestands nicht
> angesehen hat.**

Verankert in `L-2026-08-20bw` und gebaut als SWR-162.

### ⚠ Und zwei Zahlen dieses Laufs waren geschätzt statt gemessen

**(a)** Der Kommentar der eigenen Reparatur behauptete „rund 2 s" Mehrkosten; gemessen
sind es **10 s → 36 s** über alle 17 Repos. **Sechster** Beleg für `platform/T-0027`, im
selben Lauf, in dem das Ticket entstand.
**(b)** Die Commit-Nachricht zu den Lessons nennt **fünf**; es sind **sechs**. Korrigiert
im Bericht, nicht in der Historie.

> **Zweimal in einem Lauf, beide Male in einer Nebensache, beide Male vor dem Leser
> korrigiert und keines von beiden durch eine Prüfung gefunden. Genau das ist der
> Gegenstand von `platform/T-0027`.**

---

# Anhang: Sprint 22 (2026-08-20, abgeschlossen)

## Das Wichtigste (Sprint 22, 2026-08-20)

1. **✅ Der Brief, den Sprint 21 nur beantworten konnte, ist jetzt gebaut.**
   `team-mail/N-0004` sagte: *„im aktuellen sprint müsste das aufgefallen sein!?"* Der
   Preflight nennt ab jetzt **jedes Mal** die Pause seit dem letzten Sprintende — in
   Minuten und in Vielfachen des Takts, **auch wenn sie unauffällig ist**. Heute:
   *56 Min = 0,93x Takt.* Beim nächsten Ausfall steht dort *60,2x Takt — BEFUND*.
2. **⚠⚠ Die Messung dafür hat zwei Befunde geliefert, nach denen niemand gefragt hatte.**
   (a) `session.TAKT_MINUTEN` stand auf **30**, während das Register seit dem 17.08.
   **60** führt — die Kachel meldete Stille nach **einer** statt nach **zwei** Stunden.
   > **B033 in seiner leisesten Gestalt: nicht zwei Anzeigen, die sich widersprechen,
   > sondern zwei Konstanten, die sich nie begegnen.**

   (b) **Eine von sieben Pausen im Register ist negativ** (Sprint 17 startet 16:49,
   Sprint 16 endet 17:10). Nicht auf 0 geklemmt, als **Überlappung** gemeldet, Ursache
   **nicht geraten** — `platform/T-0026`. `L-2026-08-20bm`, `L-2026-08-20bn`.
3. **⚠ Und ein Test hielt eine DRITTE Kopie derselben Zahl fest.** `minutes=95` als
   „zwei Takte" — grün, solange der Irrtum galt, rot in dem Moment, in dem die beiden
   anderen Kopien in Einklang kamen.
   > **Ein Test, der eine Zahl festschreibt, die anderswo eine Tatsache ist, hält nicht
   > den Code fest, sondern den Irrtum.**
4. **✅ Die seit drei Tagen rote Zusicherung ist repariert — und das Datum NICHT
   hochgezählt** (`platform/T-0024`, SWR-157). Der Ertrag ist die **Zählung davor**:
   über 66 Testdateien gibt es **genau eine** Fundstelle dieser Bauart, während die
   richtige Gegenbauart (Schranke statt Gleichheit) an **zwei** Stellen längst existierte.
   > **Der Fehler war nicht Unwissen, sondern eine Gelegenheit — die Zahl stand gerade
   > da und war richtig.** `L-2026-08-20bp`.
5. **⚠ Die drei Fragen, die `platform/T-0020` seit vier Sprints blockierten, sind
   beantwortet — und zwei davon UMGEKEHRT zur Vermutung im Ticket.** Gemessen über alle
   **95 Commits** der Trace-Matrix: in **94 Übergängen** ist **nie** eine Anforderungs-ID
   verschwunden.
   > **⚠⚠ Der Vorfall, der das Ticket ausgelöst hat (143 → 24), steht NICHT in der
   > Historie. Er ist im selben Lauf entstanden und im selben Lauf repariert worden — er
   > hat die Arbeitskopie ruiniert und die Commits nie erreicht.** Wieder eine Prüfung
   > auf eine Spur, die es nicht gibt (dieselbe Familie wie `platform/T-0025`).
6. **⚠ Die zwei Klammern sind diesmal VOM PM nachgezogen worden und nicht vom
   Preflight** — nach zwei Läufen, in denen er es tun musste.
7. **1147 Python-Tests** (über die Sammlung **gemessen**, 66 Testdateien), Matrix
   **157 SWRs / 0 Lücken**, Briefkasten **0 offen** (58/58 beantwortet).
   ⚠ **Nicht startklar**: der Altbefund über drei Statusübergänge aus den Sprints 13
   und 15 steht unverändert. **Der rote Test von Sprint 21 ist weg** — es bleibt
   **einer** statt zweier. Nichts geglättet.

## Sprint-Plan (Sprint 22)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0025 | cm | Sprint 22 | **erledigt** | ✅ **SWR-156.** Pause seit dem letzten Sprintende, immer genannt, ab 2 Takten Befund. Aus Brief `team-mail/N-0004`. |
| platform/T-0024 | test | Sprint 22 | **erledigt** | ✅ **SWR-157.** Zusicherung ohne Ablaufdatum; Zählung vor der Reparatur: genau **1** Fundstelle. |
| platform/T-0020 | cm | Sprint 23 | offen | ⚠ **4. Verschiebung des BAUS** — die **drei Vorabfragen sind in diesem Lauf beantwortet**, als Messung an 95 Commits. Grund im Ticket, und er ist diesmal **nicht** Kapazität. |
| platform/T-0026 | cm | Sprint 23 | offen | ⚠ **Neu, 0. Verschiebung.** Die negative Pause. Erste DoD ist eine **Messung** an den Commit-Zeiten der beiden Läufe. |
| platform/T-0021 | cm | Sprint 23 | offen | ⚠ **2. Verschiebung des Baus**, Grund im Ticket. ⚠ In diesem Lauf **erneut in Produktion getroffen** (`cannot lock ref 'HEAD'`), Umgehung hat wieder gewirkt. |
| platform/T-0022 | dev | Sprint 23 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Frage 2 ist eine **Zählung** — dieselbe Bauart, die in diesem Lauf zum zweiten Mal den Ertrag geliefert hat. |
| projects/p11/T-0013 | dev | Sprint 23 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Bei der **vierten** Berührung: gebaut oder geschnitten. |
| projects/p11/T-0015 | dev | Sprint 23 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Rückbau gehört in einen Lauf, der ihn ganz trägt. |
| projects/p12/T-0011 | pl | Sprint 23 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. |
| promt-team/T-0008 | test | Sprint 23 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Beim nächsten Mal ist der Zuschnitt („eine Rolle je Lauf") die **erste** Frage. |
| promt-team/T-0003 | dev | wartet-auf-Umgebung | offen | ⚠ Wartet auf eine Umgebung mit **Ollama**. **Kein „wartet auf dich".** |
| team-mail/T-0001 | dev | wartet-auf-Umgebung | offen | ⚠ Wartet auf eine Umgebung mit **Mail-Zugangsdaten** (`MAIL_IMAP_*`). **Kein „wartet auf dich".** |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0015`; offen sind `T-0013` und `T-0015`. ✅ **Diesmal vom PM nachgezogen**, nicht vom Preflight. |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Klammer über `T-0013`. ✅ Ebenso vom PM. |
| p0/T-0008, T-0047, T-0072 · p1/T-0018 | mensch/cm/dev | — | **rejected** | Kein offener Arbeitsvorrat: verworfen und als solche geführt. Sie stehen hier, weil „nicht im Plan" sonst von „nicht nachgesehen" nicht zu unterscheiden wäre. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + Lessons (`bm` cm · `bn` cm · `bo` pl · `bp` test · `bq` test) + Verifikation + Widget-Vertrag unverändert (v2.6 — SWR-156/157 berühren keine Vertragsfläche). |

## Sprint-Abschluss (Sprint 22, 2026-08-20)

**Geschlossen:** `platform/T-0025` und `platform/T-0024` — beide **Befunde über die
eigene Arbeit**, einer davon vom Auftraggeber gemeldet.

**Neue Anforderungen:** **SWR-156**, **SWR-157**, beide `reviewed` mit Nachweis.

**Im Lauf beantwortet, ohne dass es geplant war:** die **drei Vorabfragen von
`platform/T-0020`** — die Messung an 95 Commits ist als Nebenprodukt der
Terminierungspflicht entstanden (jede offene Aufgabe wird terminiert, und wer terminiert,
liest das Ticket).

**Verschoben:** `platform/T-0020` (4., nur der Bau), `platform/T-0021` (2.),
`platform/T-0022` (2.), `p11/T-0013` (3.), `p11/T-0015` (2.), `p12/T-0011` (2.),
`promt-team/T-0008` (3.) — **alle mit Grund im Ticket**.

**Im Lauf dazugekommen:** `platform/T-0026` — die negative Pause im Register.

**Verifikation:** **1147 Python-Tests** (über die Sammlung **gemessen**, 66 Testdateien),
Matrix **157 SWRs / 0 Lücken**, Briefkasten 0 offen, entschiedene unverbuchte DRs 0.

⚠ **Nicht startklar**, aber **ein** roter Test statt zweier: der **Altbefund** über drei
unzulässige Statusübergänge aus den Sprints 13 und 15 — unverändert, **keiner aus diesem
Lauf**. `test_widget_post.BestandTest` ist **grün**.

### ⚠ Der Befund dieses Laufs über sich selbst

Zweimal in Folge hat eine Prüfung gefehlt, weil sie auf eine **Spur** schaute: Sprint 21
fand, dass ein ausgefallener Lauf keine hinterlässt. Sprint 22 fand, dass der
Matrix-Vorfall aus Sprint 17 ebenfalls keine hinterlassen hat — er lebte und starb in
einer Arbeitskopie.

> **Unsere Prüfungen lesen Commits, und Commits sind das, was übrig bleibt, wenn ein Lauf
> gut ging. Was einen Lauf zerstört oder gar nicht erst stattfinden lässt, steht dort
> nicht drin.**

Verankert in `L-2026-08-20bn` und im Kopf von `platform/T-0020`.

### ⚠ Und eine Zahl in diesem Bericht wäre ZUM VIERTEN MAL fortgeschrieben worden

Der Entwurf trug **1128** Python-Tests aus dem Bericht von Sprint 21. Gemessen über die
Sammlung sind es **1147** (66 statt 65 Dateien). Korrigiert **vor** dem Commit — wieder
durch **Nachzählen**, wieder ohne Prüfung. ⚠ **Fünfter Beleg für Frage 3 von
`platform/T-0020`**; sie ist jetzt der einzige Teil dieses Tickets, der noch offen ist.

---

# Anhang: Sprint 21 (2026-08-20, abgeschlossen)

## Das Wichtigste (Sprint 21, 2026-08-20)

1. **Ein neuer Brief des Auftraggebers hat den Sprint bestimmt** (`pm/N-0043`, 08:24) —
   vier Wünsche zum Cockpit. ⚠ Der Brief war beim ersten Briefkasten-Durchlauf dieses
   Laufs **noch nicht da**; gefunden hat ihn der **Preflight**. Genau dafür wird der
   Briefkasten seit B036 zweimal geprüft.
2. **⚠⚠ Der Befund dieses Laufs ist eine Messung über uns selbst.** Punkt 3 des Briefes
   („beim Start muss der Status auf in_progress gehen") liest sich wie etwas, das wir
   längst tun — `board.UEBERGAENGE` schreibt es seit Sprint 1 vor. Gemessen über die
   **committete Historie, 320 Ticketdateien**:

   | | |
   |---|---|
   | geschlossene Aufgaben, die **nie** `in_progress` waren | **159** |
   | Median-Aufenthalt in `in_progress` bei den übrigen 141 | **22 Sekunden** |
   | Maximum über den gesamten Bestand | 30 Minuten |

   > **Der Status wurde gesetzt, weil die Prüfung ihn verlangt, und nicht, weil er
   > jemandem etwas sagt. Eine formal erfüllte Regel hat ihren Zweck verfehlt — und es
   > ist niemandem aufgefallen, weil die Prüfung dabei grün war.**
3. **⚠ Und daraus folgt, dass Punkt 4 des Briefes ohne Punkt 3 wirkungslos gewesen wäre.**
   „Am Sprintende steht nichts auf `in_progress`" war schon immer erfüllt — nicht durch
   Disziplin, sondern weil der Zustand 22 Sekunden lebt.
   > **Eine Prüfung, die auf einem Bestand grün ist, in dem der geprüfte Zustand gar
   > nicht vorkommt, prüft nichts.** (`L-2026-08-17ai`, dritter Beleg)
4. **✅ Drei Anforderungen geschlossen: SWR-153, SWR-154, SWR-155.** Die Kachel „Letzte
   Session" nennt die **Sprintnummer** (aus dem **Register** über den **Commit**, nicht
   aus der Überschrift), der Plan erscheint in **Kapiteln mit Nummer im Titel**, und der
   Preflight meldet Aufgaben, die angefangen und liegengeblieben sind.
5. **✅ Die neue Arbeitsregel gilt ab diesem Lauf und ist in der Historie nachweisbar:**
   `platform/T-0023` und `pm/T-0069` gingen **vor** der ersten inhaltlichen Zeile auf
   `in_progress`, jeweils mit eigenem Commit.
6. **⚠ `platform/T-0021` Frage 1 ist beantwortet — als Messung, nebenbei, an den eigenen
   Commits dieses Laufs.** `objects/**/tmp_obj_*` ist **kein** Sperrproblem (Warnung,
   Exit 0). Die Sperre ist `.git/index.lock`, und die Ursache ist schärfer als vermutet:
   > **Umbenennen ist auf diesem Mount erlaubt, Löschen nicht. Git beendet einen
   > SCHREIBENDEN Indexvorgang mit einem Rename — der geht durch. Einen LESENDEN
   > (`git status`) beendet es mit einem Unlink — der scheitert und lässt die Sperre
   > stehen, an der der nächste Aufruf stirbt (Exit 128).**

   Der harmlose Lesevorgang hinterlässt die Sperre, der Schreibvorgang räumt sie auf.
7. **⚠⚠ Eine Zusicherung stand seit drei Tagen rot, und dieser Lauf hat sie gefunden.**
   `test_widget_post` hält den **echten** Bestand gegen ein **fest eingetragenes Datum**.
   Am 17.08. um **22:22** — **vier Minuten nach dem Abschlussbericht von Sprint 20
   (22:18)** — ist ein neuer Digest entstanden. Seitdem ist der Test rot; gelaufen ist
   die volle Suite in diesen drei Tagen nicht.
   > **Zum zweiten Mal in vier Tagen trifft etwas nach dem Abschlussbericht ein und wird
   > zum Altbestand des nächsten Laufs. Beim ersten Mal war es eine Klasse-A-Entscheidung
   > des Auftraggebers, diesmal eine Textdatei.**

   Neu als `platform/T-0024`. ⚠ **Nicht geglättet** — das Datum im Test wird *nicht*
   hochgezählt.
8. **⚠ Und eine Zahl in diesem Bericht war ZUM DRITTEN MAL fortgeschrieben statt
   gemessen.** Der Entwurf nannte **1155** Python-Tests; gemessen sind es **1128**.
   Korrigiert **vor** dem Commit — aber wieder durch **Nachzählen** und nicht durch eine
   Prüfung. Dritter Fall derselben Familie nach Sprint 18 und 19 (`L-2026-08-17bf`), und
   damit der dritte Beleg für **Frage 3 von `platform/T-0020`**.
9. **1128 Python-Tests (gemessen über die Sammlung), 111 JS-Tests grün, Matrix 155 SWRs /
   0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs **0**.
   ⚠ **Nicht startklar** und **zwei** rote Tests: der Altbefund über drei Statusübergänge
   aus den Sprints 13 und 15 (unverändert, **keiner aus diesem Lauf**) und der eben
   gefundene `platform/T-0024`. Nichts geglättet.

## Sprint-Plan (Sprint 21)

*Default nach `pm/D006`: in diesem Sprint schließen. ⚠ Jede Verschiebung trägt ihren
Grund **im Ticket**, nicht hier (`L-2026-08-17ag`).*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0023 | dev | Sprint 21 | **erledigt** | ✅ **SWR-153 + SWR-154.** Sprintnummer an der Session-Kachel, Kapitel mit Nummer im Titel. Aus Brief `pm/N-0043` Punkte 1+2. |
| pm/T-0069 | pl | Sprint 21 | **erledigt** | ✅ **SWR-155** + die Arbeitsregel, in diesem Lauf angewandt. Aus Brief `pm/N-0043` Punkte 3+4. |
| platform/T-0021 | cm | Sprint 22 | offen | ⚠ **1. Verschiebung des Baus** — Frage 1 (die erste DoD, eine **Messung**) ist in diesem Lauf **beantwortet**: `tmp_obj_*` ist Müll, `index.lock` ist die Sperre, Ursache ist „Rename erlaubt, Unlink nicht". Der Bau folgt der Messung, Grund im Ticket. |
| platform/T-0020 | cm | Sprint 22 | offen | ⚠ **3. Verschiebung**, Grund im Ticket. Frage 3 ist die eigentliche und hat in diesem Lauf einen weiteren Beleg bekommen. |
| platform/T-0022 | dev | Sprint 22 | offen | ⚠ SWR-152 ist gebaut; die **drei Fragen** sind unbeantwortet. Frage 2 ist eine Zählung und der nächste Schritt. |
| projects/p11/T-0013 | dev | Sprint 22 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. PIN-Lesegate ist eine **Zugriffs**entscheidung. |
| projects/p11/T-0015 | dev | Sprint 22 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. Rückbau; die Entscheidung liegt vor (`T-0014`). |
| projects/p12/T-0011 | pl | Sprint 22 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. Der Vollständigkeitsnachweis muss über die **neuen Textsorten** laufen. |
| promt-team/T-0008 | test | Sprint 22 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Goldset für die übrigen zehn Rollen. |
| promt-team/T-0003 | dev | wartet-auf-Umgebung | offen | ⚠ **Entblockt** (D000), wartet auf eine Umgebung mit **Ollama** — in diesem Lauf erneut gemessen: `which ollama` leer, `localhost:11434` ohne Antwort. **Kein „wartet auf dich".** |
| team-mail/T-0001 | dev | wartet-auf-Umgebung | offen | ⚠ Wartet auf eine Umgebung mit **Mail-Zugangsdaten** — gemessen: keine `MAIL_IMAP_*` gesetzt. **Kein „wartet auf dich".** |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0015`; offen sind `T-0013` und `T-0015` (beide Sprint 22). ⚠ Stand beim Planen noch auf Sprint 20 — **vom Preflight nachgezogen, zum zweiten Mal in Folge**. |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Klammer über `T-0013` (Sprint 22). ⚠ Ebenso vom Preflight nachgezogen. |
| platform/T-0024 | test | Sprint 22 | offen | ⚠ **Neu, 0. Verschiebung.** Die rote Zusicherung mit festgeschriebenem Datum. Erste DoD ist eine **Zählung**: wie viele Zusicherungen derselben Bauart gibt es? |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen, **zweimal** geprüft) + Lessons (`bh`, `bi`, `bj`) + Verifikation + Widget-Vertrag unverändert (v2.6 — SWR-153/154 berühren `/api/session` und `/api/sprint`, keine Vertragsfläche). |

## Sprint-Abschluss (Sprint 21, 2026-08-20)

**Geschlossen:** `platform/T-0023` und `pm/T-0069` — **beide aus dem Brief des
Auftraggebers**, beide am selben Tag, an dem er ihn geschrieben hat.

**Neue Anforderungen:** **SWR-153, SWR-154, SWR-155**, alle drei `reviewed` mit Nachweis.

**Im Lauf beantwortet, ohne dass es geplant war:** `platform/T-0021` **Frage 1** — die
erste DoD dieses Tickets war ausdrücklich eine **Messung** und keine Meinung. Sie ist
als Nebenprodukt der eigenen Commits dieses Laufs entstanden.

**Verschoben:** `platform/T-0020` (3.), `platform/T-0021` (1., Bau), `platform/T-0022`
(1.), `p11/T-0013` (2.), `p11/T-0015` (1.), `p12/T-0011` (1.), `promt-team/T-0008` (2.)
— **alle mit Grund im Ticket**. Der Grund ist in allen Fällen derselbe und er wird nicht
schöner, wenn man ihn siebenmal aufschreibt: **die Kapazität eines Laufs**, verbraucht
durch den Brief. ⚠ Er trägt sein Verfallsdatum: er gilt für Sprint 21.

**Im Lauf dazugekommen:** `platform/T-0024` — die rote Zusicherung, die seit drei Tagen
niemand gesehen hat.

**Verifikation:** **1128 Python-Tests** (über die Sammlung **gemessen**, 65 Testdateien),
**111 JS-Tests grün** (von 104), Matrix **155 SWRs / 0 Lücken**, Briefkasten 0 offen,
entschiedene unverbuchte DRs 0.

⚠ **Nicht startklar**, und **zwei** rote Tests statt einem:

1. der **Altbefund** über drei unzulässige Statusübergänge aus den Sprints 13 und 15 —
   unverändert, **keiner aus diesem Lauf**;
2. `test_widget_post.BestandTest` — **rot seit dem 17.08. 22:22**, gefunden in diesem
   Lauf, als eigenes Ticket `platform/T-0024` verbucht.

Nichts geglättet, kein Test angepasst, um grün zu werden.

### ⚠ Zum zweiten Mal in Folge hat der Preflight dieselben zwei Klammern nachgezogen

`p11/T-0003` und `p11/T-0009` standen beim Planen wieder auf **Sprint 20** — genau wie in
Sprint 20 selbst, wo derselbe Befund an denselben zwei Tickets stand. Gefunden hat es
wieder der **Preflight** und nicht der, der den Plan geschrieben hat.

> **Dass derselbe Handgriff zweimal hintereinander vergessen wurde, ist kein
> Konzentrationsproblem. „Eine Klammer folgt ihren Teilen" ist eine mechanische Regel —
> und mechanische Regeln gehören an eine Prüfung, nicht an eine Erinnerung.**

Notiert als Nachbar von `platform/T-0020`.

### ⚠ Der Befund dieses Laufs über sich selbst

Der Auftraggeber hat eine Regel verlangt, **die es seit Sprint 1 gibt**. Die bequeme
Antwort wäre „haben wir schon" gewesen, und sie wäre belegbar richtig gewesen: die
Übergangsprüfung erzwingt `open → in_progress → in_review → done`, und ein Sprung
darüber hinweg ist ein Prüfbefund.

Nachgemessen hat sie 22 Sekunden gelebt.

> **Eine Regel kann formal erfüllt und in der Sache verfehlt sein, und die Prüfung, die
> sie erzwingt, merkt davon nichts — sie prüft die Reihenfolge der Zustände, nicht ihre
> Dauer. Der Mensch, der auf die Anzeige sieht, prüft genau umgekehrt.**

Aufgefallen ist es, weil wir vor dem Antworten **nachgezählt** haben statt zu behaupten.
Verankert als `L-2026-08-20bh`.

---

## ⚠⚠ Nachtrag zu Sprint 21 (2026-08-20 11:50) — nach dem Abschluss, und deshalb kein neuer Sprint

**Zum DRITTEN Mal in vier Tagen ist etwas nach dem Abschlussbericht eingetroffen.** Diesmal
ein Brief (`team-mail/N-0004`, **11:35**), der genau diesem Bericht (**11:16**) vorwirft,
etwas übersehen zu haben — und er hat recht.

> *„in der konfiguration ist tägliches routine eigerichtet, jedoch wurde das nicht
> ausgeführt. die letzten 2 tage war server down, aber im aktuellen sprint müsste das
> aufgefallen sein!?"*

**Gemessen aus dem eigenen Register:** die Pause zwischen dem Ende von Sprint 20 und dem
Start von Sprint 21 betrug **3 612 Minuten = 60,2 Stunden** bei einem hinterlegten Takt
von **60 Minuten** — das **Sechzigfache**. Sprint 21 hat es nicht gemeldet.

> **`nicht_beendete()` prüft Sprints OHNE `ende` — also Läufe, die mittendrin abbrachen.
> Das ist eine Prüfung auf eine SPUR. Ein Lauf, der ausfällt, hinterlässt keine Spur.**

⚠ **Und dieser Lauf ist an der Stelle vorbeigelaufen, an der es sichtbar war:** SWR-153 hat
der Kachel „Letzte Session" an genau diesem Tag den Zeitpunkt und die Sprintnummer des
letzten Laufs gegeben. Niemand hat gefragt, warum dieser Zeitpunkt zweieinhalb Tage
zurücklag. **Die Angabe existierte, die Frage nicht.** `L-2026-08-20bk`, neu als
`platform/T-0025`.

### ⚠ Und die Nachprüfung des eigenen Abschlusses hat zwei Fehler in ihm gefunden

1. **`platform/T-0021` wurde ohne Begründung von Sprint 20 auf 22 gezogen**, während dieser
   Bericht an **zwei** Stellen „Grund im Ticket" behauptete. Grund nachgetragen.
   > **Ein Ticket, in dem in diesem Sprint etwas Gutes passiert ist, sieht bearbeitet aus —
   > die Verschiebung daneben verschwindet hinter dem Teilerfolg.** (`L-2026-08-20bl`)
2. **Drei Testzahlen in den Anforderungszeilen SWR-153/154/155 waren geschätzt statt
   gezählt** (10/17/10 statt **12/20/9**). Das ist derselbe Fehlertyp, den Punkt 8 oben an
   sich selbst rügt — **im selben Lauf noch einmal und eine Etage tiefer**. Korrigiert.

⚠ Beides ist der **vierte** Beleg für **Frage 3 von `platform/T-0020`**: der
Abschlussbericht hat für seine eigenen Aussagen keine Zusicherung. Gefunden hat es beide
Male eine **Nachprüfung** und keine Prüfung.

**Der Abschluss von Sprint 21 wird dadurch nicht umgeschrieben.** Was oben steht, war zu
seinem Zeitpunkt der gemessene Stand; dieser Nachtrag steht darunter und nicht an seiner
Stelle.

---

# Anhang: Sprint 20 (2026-08-17, abgeschlossen)

## Das Wichtigste (Sprint 20, 2026-08-17)

1. **Wir waren in Sprint 20** (Start 21:45, Kennung `2026-08-17T2145-cowork-s20`).
   ⚠ **Anlass war kein Plan, sondern ein Fehlschlag in Produktion**, gemeldet vom
   Auftraggeber.
2. **⚠⚠ Eine KLASSE-A-ENTSCHEIDUNG ließ sich nicht verbuchen.** Er hat
   `promt-team/T-0009` mit **A** entschieden; die Inbox starb mit `[Errno 2] No such
   file or directory` — `promt-team` hat nie ein `management/decisions/decision-log.md`
   bekommen.
   > **Der Schreibweg setzte eine Datei voraus, die ein ANDERER Weg anlegt. Solange
   > jedes Repo durch diesen anderen Weg entstanden ist, ist die Annahme unsichtbar
   > richtig — sie wird an dem Repo sichtbar, das anders entstand.**

   Betroffen waren **zwei** Repos, gemessen. Repariert als **SWR-152**
   (`platform/T-0022`).
3. **⚠⚠ Kein bestehender Test hätte das finden können** — jede Fixture legt ihre
   Verzeichnisse **selbst** an. `L-2026-08-17bg`.
4. **✅ `promt-team/T-0009` verbucht (D000, Option A)**, **✅ G4 für `p12-v1.0` erteilt
   (D003)**, **Klammer `p12/T-0003` geschlossen**.
5. **1087 Python-Tests**, 104 JS-Tests grün, Matrix 152/0, Briefkasten 0 offen.
   ⚠ Nicht startklar — Altbefund unverändert.

## Sprint-Plan (Sprint 20, Abschlussstand)

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0022 | dev | Sprint 20 | offen | ✅ **SWR-152 gebaut und abgenommen.** ⚠ Das Ticket bleibt **offen**: drei benannte Fragen sind unbeantwortet. |
| promt-team/T-0009 | pl | Sprint 20 | **erledigt** | ✅ **D000, Option A** verbucht. |
| projects/p12/T-0010 | pl | Sprint 20 | **erledigt** | ✅ **D003, Option A** verbucht: **G4 erteilt**. |
| projects/p12/T-0003 | pl | Klammer | **erledigt** | ✅ Klammer geschlossen — **Baseline `p12-v1.0` abgenommen**. |

## Sprint-Abschluss (Sprint 20, 2026-08-17)

**Geschlossen:** `promt-team/T-0009` und `projects/p12/T-0010` (beide **Klasse-A-DRs des
Auftraggebers**), dazu die **Klammer `p12/T-0003`**.

**Verifikation:** 1087 Python-Tests, 104 JS-Tests grün, Matrix 152/0, Briefkasten 0
offen, Plan-Drift 0, Statusdrift 0. ⚠ Nicht startklar — Altbefund unverändert.



</details>

<!-- kennzahlen v1 | gemessen 2026-08-22 16:55
beitraege_im_lauf=0 briefe_im_lauf=0 briefkasten_offen=0 ladefehler=0 luecken=0 parkplatz=12933 post_im_lauf=0 swr=218 testdateien=113 tests=1611 tickets_offen=40 wartet_auf_mensch=0
-->

</details>

</details>

</details>
