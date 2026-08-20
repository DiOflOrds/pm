# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

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
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0015`; offen sind `T-0013` und `T-0015` (beide Sprint 22). |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Klammer über `T-0013` (Sprint 22). |
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
