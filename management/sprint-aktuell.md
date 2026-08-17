# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste (Sprint 20, 2026-08-17)

1. **Wir sind in Sprint 20** (Start 21:45, Kennung `2026-08-17T2145-cowork-s20`). ⚠ **Anlass
   ist kein Plan, sondern ein Fehlschlag in Produktion**, gemeldet vom Auftraggeber.
2. **⚠⚠ Eine KLASSE-A-ENTSCHEIDUNG ließ sich nicht verbuchen.** Er hat `promt-team/T-0009`
   mit **A** entschieden; die Inbox starb mit `[Errno 2] No such file or directory` —
   `promt-team` hat nie ein `management/decisions/decision-log.md` bekommen. `open(..., "a")`
   legt eine **Datei** an, aber kein **Verzeichnis**; das Verzeichnis legt `pool.gruende` bei
   der Gründung an.
   > **Der Schreibweg setzte eine Datei voraus, die ein ANDERER Weg anlegt. Solange jedes
   > Repo durch diesen anderen Weg entstanden ist, ist die Annahme unsichtbar richtig — sie
   > wird an dem Repo sichtbar, das anders entstand.**

   Betroffen waren **zwei** Repos (`promt-team`, `platform`), gemessen. Repariert als
   **SWR-152** (`platform/T-0022`).
3. **⚠⚠ Kein bestehender Test hätte das finden können** — jede Fixture legt ihre
   Verzeichnisse **selbst** an, und damit auch die, die in Produktion fehlte. Das ist wörtlich
   die offene Erkennungsfrage aus Sprint 16 (`L-2026-08-17ai`), zum **ersten Mal an einem
   echten Schaden** belegt statt als Sorge formuliert. Die neue Teststrecke beginnt deshalb
   mit einer **Gegenprobe**, die den echten Zustand herstellt. `L-2026-08-17bg`.
4. **⚠ Angelegt statt abgewiesen — und die Kehrseite ist benannt.** Ein sauberer 400er wäre
   ehrlicher gewesen als der Errno und hätte den Menschen mit einer getroffenen
   Klasse-A-Entscheidung stehen lassen, die er nicht verbuchen kann.
   > **Eine getroffene Entscheidung, die am Ablageort scheitert, ist verloren, sobald das
   > Fenster zu ist.**

   ⚠ Ein selbstheilender Weg macht den Mangel **unsichtbar**; ob das Anlegen in den
   Schreibweg gehört oder als Befund in den Preflight, ist **offene Frage 3** in
   `platform/T-0022`.
5. **✅ `promt-team/T-0009` verbucht (D000, Option A)** — Ollama lokal als Baseline-Stufe,
   0 €. `promt-team/T-0003` ist damit **entblockt**.
6. **⚠ Und `T-0003` wartet jetzt auf eine UMGEBUNG, nicht auf den Menschen — gemessen:**
   `which ollama` leer, `localhost:11434` ohne Antwort. Der Wartegrund steht als **Feld und
   Messung im Ticket** und nicht als Satz im Plan — genau der Fehler, bei dem uns der
   Auftraggeber in Sprint 17 mitten im Lauf erwischt hat (`L-2026-08-17ag`).
7. **⚠⚠ Ein Bestandstest hat eine ZWEITE Entscheidung gefunden, die niemand gemeldet hatte.**
   Der Auftraggeber hat um **21:57** auch `p12/T-0010` mit **A** entschieden — erfolgreich,
   p12 hat ein Log. Der Abschlussbericht von Sprint 19 (21:45) meldete „entschiedene
   unverbuchte DRs: **0**", und das war zu diesem Zeitpunkt **richtig**.
   > **Eine Entscheidung, die nach dem Abschlussbericht eintrifft, ist für diesen Bericht
   > unsichtbar und für den nächsten Lauf ein Altbestand. Der Bestandstest ist die einzige
   > Stelle, die beides verbindet.**
8. **✅ Damit ist G4 für `p12-v1.0` ERTEILT** (D003) und die **Klammer `p12/T-0003`
   geschlossen** — das Projekt P12 ist an seiner Baseline abgenommen. ⚠ Der **benannte
   Folgepunkt** ist mit G4 **ausdrücklich offengehalten** und liegt als `p12/T-0011`; die
   **zwei Vorbehalte** der Abnahme gelten weiter.
   > **Ein erteiltes Gate sagt „das Beauftragte ist geliefert und geprüft". Es sagt nicht
   > „hier ist nichts mehr offen" — und der Unterschied verschwindet, sobald nur der Haken
   > übrig bleibt.**
9. **⚠ Drei Befunde hat der Preflight an DIESEM Lauf gefunden**, nicht der Verfasser des
   Plans: eine Plan-Drift (`promt-team/T-0003`), eine Statusdrift (`T-0009` done vs. Plan
   offen) und **zwei Klammern, die auf einem vergangenen Sprint offenstanden**.
   > **Eine Klammer, die auf einem vergangenen Sprint stehen bleibt, sieht aus wie etwas
   > Liegengebliebenes und ist etwas Wartendes.**
10. **1087 Python-Tests** (gemessen über die Sammlung, **nicht** fortgeschrieben — die Lehre
    von `L-2026-08-17bf` diesmal angewandt), **104 JS-Tests grün**, Matrix **152 SWRs /
    0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs **0**.
    ⚠ **Nicht startklar** — der Altbefund über drei Statusübergänge aus den Sprints 13 und 15
    ist unverändert, **keiner aus diesem Lauf**.

## Sprint-Plan (Sprint 20, Abschlussstand)

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0022 | dev | dieser Sprint | offen | ✅ **SWR-152 gebaut und abgenommen**, der Fehlschlag ist behoben. ⚠ Das Ticket bleibt **offen**: drei benannte Fragen sind unbeantwortet — die Reihenfolge im Schreibvorgang ist nur an ihrer ersten Datei abgesichert, weitere Pflichtartefakte sind **ungezählt**, und ob Heilen oder Melden richtig ist, ist nicht entschieden. |
| promt-team/T-0009 | pl | dieser Sprint | **erledigt** | ✅ **D000, Option A** verbucht. |
| projects/p12/T-0010 | pl | dieser Sprint | **erledigt** | ✅ **D003, Option A** verbucht: **G4 erteilt**. |
| projects/p12/T-0003 | pl | Klammer | **erledigt** | ✅ Klammer geschlossen — **Baseline `p12-v1.0` abgenommen**. |
| promt-team/T-0003 | dev | Sprint 21 | offen | ⚠ **Entblockt** (D000). Wartet auf eine **Umgebung mit Ollama** — gemessen, nicht vermutet. **Kein „wartet auf dich".** |
| projects/p12/T-0011 | pl | Sprint 21 | offen | ⚠ **Neu.** Der Folgepunkt aus G4. Drei Punkte **vor** dem Bauen, darunter: der Vollständigkeitsnachweis muss über die **neuen Textsorten** laufen — der bestehende misst Briefe. |
| projects/p11/T-0013 | dev | Sprint 20 | offen | ⚠ 1. Verschiebung (Sprint 19), Grund im Ticket. PIN-Lesegate ist eine **Zugriffs**entscheidung. |
| projects/p11/T-0015 | dev | Sprint 20 | offen | Rückbau; die Entscheidung liegt vor (`T-0014`). |
| platform/T-0020 | cm | Sprint 20 | offen | ⚠ 2. Verschiebung (Sprint 19). Frage 3 ist die eigentliche. |
| platform/T-0021 | cm | Sprint 20 | offen | ⚠ Werkzeugbefund aus Sprint 19; kostet jeden Lauf Zeit. Erste DoD ist eine **Messung**. |
| promt-team/T-0008 | test | Sprint 20 | offen | Goldset für die übrigen zehn Rollen. |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Folgt `T-0013`/`T-0015` (Sprint 20) — vom Preflight nachgezogen. |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Folgt `T-0013` (Sprint 20) — vom Preflight nachgezogen. |
| pm/T-0001..0003, platform/T-0001, team-dashboard/T-0001 | pl/coach/cm | jeder Sprint | **erfüllt** | Takt: Agenda + Briefkasten (0 offen) + **eine** Lesson (`bg`) + Verifikation + Vertrag unverändert (v2.6). |
| team-mail/T-0001 | dev | jeder Sprint | offen | ⚠ Wartet auf eine Umgebung mit Mail-Zugangsdaten — **kein „wartet auf dich"**. |

## Sprint-Abschluss (Sprint 20, 2026-08-17)

**Geschlossen:** `promt-team/T-0009` und `projects/p12/T-0010` (beide **Klasse-A-DRs des
Auftraggebers**), dazu die **Klammer `p12/T-0003`** — **Baseline `p12-v1.0` abgenommen**.

**Im Lauf dazugekommen:** `platform/T-0022` (der Produktionsfehler, **offen** mit drei
Fragen) und `projects/p12/T-0011` (der Folgepunkt aus G4).

**Neue Anforderung:** **SWR-152**, `reviewed` mit Nachweis (8 Zusicherungen).

**Verifikation:** **1087 Python-Tests** (über die Sammlung **gemessen**), **104 JS-Tests
grün**, Matrix **152 SWRs / 0 Lücken**, Briefkasten 0 offen, entschiedene unverbuchte DRs
**0**, Plan-Drift 0, Statusdrift 0.

⚠ **Nicht startklar** — Altbefund unverändert, keiner aus diesem Lauf. Nichts geglättet.

### ⚠ Der Befund dieses Laufs über sich selbst

Eine Zusicherung dieses Laufs war **falsch rot**: sie suchte dateiweit nach
`_naechste_d_id(log_pfad)` und fand die **Definition** statt des Aufrufs.

> **Eine Textsuche kann eine Definition nicht von ihrem Aufruf unterscheiden — und die
> Definition steht nun einmal vor dem Aufruf.**

**Sechster Fehlalarm derselben Familie in drei Tagen** (nach fünf über Kommentare). Gemessen
wird jetzt **im Rumpf der Funktion** und nicht in der Datei. ⚠ Die Familie wächst, und keine
Regel hat sie bisher verhindert — sie steht als Kandidat neben `platform/T-0020`.

---

# Anhang: Sprint 19 (2026-08-17, abgeschlossen)

## Sprint-Plan (Abschlussstand)

*Sprint 19 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 20; danach ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| projects/p12/T-0006 | pl | dieser Sprint | **erledigt** | ✅ **SWR-097–101.** Ein Renderweg; `tlinks` **entfallen** (4 → 0), Erkennung im Inline-Pass, Zäune verbatim, Briefe + Reports über `mdRender`. ⚠ Der Zaun-Zweig war zuerst **toter Code**. |
| projects/p11/T-0011 | dev | dieser Sprint | **erledigt** | ✅ **SWR-151.** Vierte Berührung, gebaut statt zerlegt. Ausschlussliste, kein Schreibweg zum Server, Erklärung im Kopf der Ansicht. |
| projects/p11/T-0014 | pl | dieser Sprint | **erledigt** | ✅ **Entschieden: Option B.** Die Messung an `T-0011` hat A und C an ihrer Voraussetzung erledigt. Ausführung → `p11/T-0015`. |
| projects/p11/T-0008 | dev | Klammer | **erledigt** | ✅ Klammer geschlossen: `T-0010` (SWR-135) + `T-0011` (SWR-151). Viermal verschoben, dem Auftraggeber zugesagt — eingelöst. |
| pm/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten geprüft — **0 offen**, in allen 17 Repos. |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: **sechs** Lessons SOFORT verankert (`az`, `ba` test · `bb`, `bc` dev · `bd` cm · `be` pl). |
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: 1079 Python-Tests (1 rot, Altbefund), 104 JS-Tests grün, Matrix 151/0. ⚠ Die Suite läuft in **Blöcken** — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag unverändert bei **v2.6** — SWR-151 speichert **im Browser** und berührt keine Vertragsfläche. |
| team-mail/T-0001 | dev | jeder Sprint | offen | ⚠ Der Digest fehlt weiter. Diese Sandbox hat die Zugangsdaten nicht (Datenklasse `geheim`); die Rückfrage steht seit Sprint 17 in `team-mail/N-0003`. **Kein „wartet auf dich"** — es wartet auf eine Umgebung mit Zugangsdaten. |
| projects/p12/T-0010 | pl | **beim Menschen** | offen | ⚠ **Neu, Inbox-DR (Klasse A).** G4 für `p12-v1.0` **und** der benannte Folgepunkt (Ticket-/DR-Body, zwei Dokumentenansichten). Frist **2026-08-20**, Default **A**. |
| promt-team/T-0009 | pl | **beim Menschen** | offen | ⚠ Inbox-DR aus Sprint 18 (Klasse A), **unbeantwortet**. Frist **2026-08-19**, Default **A** (Ollama, 0 €). |
| promt-team/T-0003 | dev | Sprint 20 | blocked | `blocked_by: [T-0009]` — der Wartegrund ist ein **Feld** und kein Fließtext. |
| projects/p11/T-0013 | dev | Sprint 20 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. `blocked_by` seit SWR-150 erfüllt — terminiert, nicht blockiert. ⚠ Ein PIN-Lesegate ist eine **Zugriffs**entscheidung und **kein** Verstecken (B025). |
| platform/T-0020 | cm | Sprint 20 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Frage 2 hat dieser Lauf **an einem Fall** beantwortet (3 rote Zusicherungen, genau die erwarteten). Frage 3 bleibt die eigentliche. |
| projects/p11/T-0015 | dev | Sprint 20 | offen | ⚠ **Neu, 0. Verschiebung.** Die **Ausführung** von `T-0014` (Rückbau). ⚠ `_zustand` bleibt — SWR-146 hängt daran. |
| platform/T-0021 | cm | Sprint 20 | offen | ⚠ **Neu, 0. Verschiebung.** Werkzeugbefund dieses Laufs. Erste DoD ist eine **Messung**: ist `tmp_obj_*` eine Sperre oder Müll, den `verbuche` als Fehlschlag liest? |
| promt-team/T-0008 | test | Sprint 20 | offen | Goldset für die übrigen zehn Rollen. ⚠ Braucht Läufe, die es selbst nicht erzeugt. |
| projects/p11/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0007`–`T-0015`; offen sind `T-0013` und `T-0015` (beide Sprint 20). |
| projects/p11/T-0009 | dev | Klammer | nachgezogen | Klammer über `T-0012` (**done**) / `T-0013` (Sprint 20). |
| projects/p12/T-0003 | pl | Klammer | nachgezogen | Klammer über `T-0004`–`T-0010`; offen ist nur noch der **G4-DR beim Menschen**. |

⚠ **Eine Klammer zählt nicht als verschoben.** Sie war nie an der Reihe — sie wartet auf
ihren letzten Teil. Die Verschiebungszählung läuft an den **Teilen** (`L-2026-08-17x`).

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected` und warten auf eine **Handlung des Menschen**. Sie erscheinen seit SWR-138 im
Abschnitt „Für dich: Handlungen".

## Sprint-Abschluss (Sprint 19, 2026-08-17)

**Geschlossen:** `projects/p12/T-0006`, `projects/p11/T-0011`, `projects/p11/T-0014` — **drei
Sachtickets**, dazu die **Klammer `p11/T-0008`** und **fünf** Takt-Pflichten.

**Im Lauf dazugekommen:** `projects/p12/T-0010` (**G4-Inbox-DR, Klasse A**),
`projects/p11/T-0015` (Ausführung der Entscheidung) und `platform/T-0021` (Werkzeugbefund).

**Neue/abgenommene Anforderungen:** **SWR-097 bis SWR-101** wechseln zum ersten Mal auf
`reviewed` — einzeln, jede mit ihrem Nachweis — und **SWR-151** ist neu. Das sind **sechs**.

**Verschoben:** `p11/T-0013` (1.) und `platform/T-0020` (2.), beide mit Grund **im Ticket**.

**Verifikation:** **1079 Python-Tests, 1078 grün / 1 rot** (der Altbefund über drei
unzulässige Übergänge — **keiner aus diesem Lauf**), **104 JS-Tests grün** (von 78), Matrix
**151 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs **0**,
Plan-Drift 0, Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: zwei aus Sprint 13 (`platform/T-0014`, `pm/T-0064`) und
einer aus Sprint 15 (`pm/T-0052`), **alle unverändert**. Nichts geglättet, kein Test
angepasst, um grün zu werden.

### ⚠ Eine Zahl in diesem Bericht war ZUM ZWEITEN MAL fortgeschrieben statt gemessen

Der erste Entwurf dieses Abschlusses nannte **1077** Python-Tests. Gemessen sind es **1079**
(61 Testdateien, über die Sammlung gezählt). Die 1077 entstand aus dem Stand von Sprint 18
**plus einer Erwartung** über die eigenen Neuzugänge.

> **Es ist derselbe Fehler, den Sprint 18 als eigenen Abschnitt aufgeschrieben hat — im
> Abschlussbericht des nächsten Sprints, von einem Lauf, der die Warnung beim Schreiben vor
> Augen hatte.**

⚠ Aufgefallen ist es wieder **beim Nachzählen** und nicht durch eine Prüfung. Das ist genau
**Frage 3 von `platform/T-0020`**: der Abschlussbericht hat für seine eigenen Kennzahlen
keine Zusicherung — und die Wiederholung binnen eines Sprints ist der Beleg, dass eine
aufgeschriebene Lesson diese Lücke nicht schließt. `L-2026-08-17bf`.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Sprint 18 hat eine Messung gebaut, die seine eigene Arbeit widerlegte. Sprint 19 hat etwas
anderes getan: er hat **einen Zweig gebaut, den niemand erreichen konnte** — und der Zähltest,
der dafür gebaut war, war dabei **grün**.

> **Eine Statikprüfung darf eine neue Verzweigung melden, aber nicht abnehmen. Zu jedem neuen
> Zweig gehört ein Beispiel, das ihn IM ZUSAMMENHANG trifft.**

Dazu ein zweiter Befund an der **Prüfstrecke selbst**: der Inline-Pass fragt seit der
Umstellung `Regeln` nach dem Ticketziel, und der Nachweis-Harnisch lud `regeln.js` nicht. Der
bequeme Weg wäre ein **Ersatz-`Regeln` im Test** gewesen — *eine zweite Antwort auf genau die
Frage, gegen die SWR-150 gebaut ist.* Geladen wird jetzt die echte Datei, in der Reihenfolge
von `index.html`, und der Ladeweg liegt **einmal** in `_app_laden.cjs`.

⚠ Die Erkennungsfrage aus Sprint 16 — *welche unserer über 1000 Zusicherungen prüfen etwas,
das die Testdatei selbst eingerichtet hat?* — bleibt **unbeantwortet** (`L-2026-08-17ai`).
Dieser Lauf hat sie nicht beantwortet; er hat aber die 27 neuen Zusicherungen gegen den
**wirklichen** Bestand gemessen und die 15 Verhaltenszusicherungen von SWR-151 kennen den
Quelltext gar nicht — sie sehen nur Eingabe und Ergebnis.

### Was in Sprint 20 zuerst kommt

1. **`platform/T-0021`** — der Werkzeugbefund. Er kostet jeden Lauf Zeit und erzeugt
   Rücknahmen, die wie „nie versucht" aussehen. Erste DoD ist eine **Messung**.
2. **`projects/p11/T-0013`** — Mail-Widget hinter dem PIN; schließt die Klammer `p11/T-0009`.
   ⚠ Zugriffsentscheidung, nicht Verstecken.
3. **`projects/p11/T-0015`** — der Rückbau; die Entscheidung liegt vor.
4. **`platform/T-0020`** — dritte Berührung; Frage 3 ist die eigentliche.
5. **Die beiden DRs verbuchen**, sobald die Antworten da sind (`promt-team/T-0009` bis 19.08.,
   `p12/T-0010` bis 20.08.).
