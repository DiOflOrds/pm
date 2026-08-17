# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 19** (2026-08-17, Start 20:20, Kennung `2026-08-17T2020-cowork-s19`).
   Sprint 18 war ordentlich beendet; dieser Lauf hat **keine fremde Buchung** nachtragen
   müssen.
2. **✅ `projects/p12/T-0006` gebaut — die Zusammenführung ist eingelöst, und sie ist eine
   ZAHL.** `ALTBESTAND_TLINKS_AUFRUFE` steht von **4 auf 0**: `tlinks` ist nicht „nicht mehr
   aufgerufen", sondern **entfallen**. **SWR-097 bis SWR-101** stehen einzeln auf
   `reviewed`, jede mit ihrem Nachweis.
3. **⚠⚠ Der Befund dieses Laufs: ein neuer Zweig war toter Code, und der Zähltest sah ihn
   stehen.** Der Code-Zaun-Zweig war gebaut und wurde **nie erreicht** — Absatz- und
   Listenpfad sammeln Folgezeilen, bis ein bekanntes Muster kommt, und ```` ``` ```` stand in
   dieser Abbruchregel nicht.
   > **Ein neuer Block-Zweig ist erst dann erreichbar, wenn die Fortsetzungsregel des
   > vorherigen Blocks ihn kennt. Beide Stellen sind für sich genommen richtig.**

   ⚠ Gefunden hat es der **Verhaltenstest**, nicht der Zähltest — *ein Muster im Quelltext
   ist eine Absicht; erst der Knoten, der danach dasteht, ist ein Befund.* ⚠ Und dessen
   **erste Fassung war ebenfalls grün**: sie hatte den Zaun am Textanfang, wo keine
   Fortsetzungsregel greift. `L-2026-08-17az`.
4. **✅ Drei eingefrorene Zusicherungen aus Sprint 18 sind rot geworden — genau die drei und
   keine vierte — und UMGEDREHT statt gelöscht.**
   > **Ein eingefrorener Befund ohne die Zusage, ihn beim Bauen umzudrehen, ist eine Warnung
   > mit Zeitstempel. Die Zahl der rot gewordenen Zusicherungen ist selbst eine Messung.**

   `L-2026-08-17ba`. Das beantwortet nebenbei die zweite offene Frage von `platform/T-0020`
   — an einem Fall statt an einer Überlegung.
5. **✅ `projects/p11/T-0011` bei der VIERTEN Berührung gebaut** (**SWR-151**), nach
   `L-2026-08-17x`: gebaut, nicht zerlegt, weil das Ticket seit Sprint 17 im eigenen Text
   sagt, dass es **keine Naht** hat. Damit ist die **Klammer `p11/T-0008`** geschlossen — ein
   Ticket, das viermal verschoben und dem Auftraggeber in Sprint 11 zugesagt war.
6. **⚠⚠ Die bestimmende Frage von `T-0011` war DoD 2 und nicht die Technik.** Zwei
   benachbarte Ansichten, eine speichert und eine nicht: SWR-133 hat Persistenz für den
   Faltzustand ausdrücklich **abgelehnt**.
   > **Falten ist ein Griff beim Lesen. Eine Auswahl ist eine Aussage. Der Einwand aus
   > SWR-133 verbietet die Persistenz nicht — er verlangt die ERKLÄRUNG.**

   Sie steht im **Kopf** der Ansicht: Zahl, **Namen** und ein Weg zurück. ⚠ Und die andere
   Hälfte ist eine **Messung**: eine Zusicherung hält fest, dass der Faltzustand weiterhin
   flüchtig ist — sonst wäre die Begründung gegenstandslos, **ohne dass jemand sie
   zurückgenommen hat**. `L-2026-08-17bc`.
7. **⚠ Gespeichert wird das ABGEWÄHLTE, nicht das Gewählte.**
   > **Eine gespeicherte Auswahl altert gegen einen wachsenden Bestand: sie sagt „zeig
   > diese", und was danach dazukommt, fällt lautlos aus der Ansicht.**

   Ein Team, das ein `widget.yaml` neu hinlegt, hätte sonst für jeden, der einmal
   konfiguriert hat, **nichts** getan. `L-2026-08-17bb`.
8. **✅ `projects/p11/T-0014` ENTSCHIEDEN (Option B) — und die Messung hat zwei Optionen an
   ihrer Voraussetzung erledigt.** Das Ticket verlangte *„erst messen, dann entscheiden"*;
   der einzige benannte künftige Leser war `p11/T-0011`. Nach dessen Bau steht fest: es liest
   `/api/widgets` und braucht `/api/dashboard` **nicht**.
   > **Option A hätte einen falschen Satz in einen Docstring geschrieben, Option C war an
   > genau diesen Bedarf konditioniert. Über ihren Preis musste niemand mehr reden.**

   ⚠ Die **Ausführung** ist `p11/T-0015` (Sprint 20) und **keine Verschiebung**: ein
   Entscheidungsticket ist mit der Entscheidung fertig; eine abgenommene Anforderung
   zurückzuschneiden ist ein Bau mit eigener DoD. `L-2026-08-17be`.
9. **⚠⚠ Ein Werkzeugbefund, den dieser Lauf am eigenen Leib gemessen hat** (`platform/T-0021`,
   **neu**): auf diesem Mount hinterlässt **jeder Commit** `tmp_obj`-Reste, an denen der
   **nächste** Git-Aufruf scheitert — dreimal in Folge gemessen.
   > **Ein Vorlauf, der einmal am Anfang räumt, schützt gegen den Zustand von gestern und
   > nicht gegen den, den dieser Lauf gerade selbst erzeugt.**

   ⚠ Die zweite Gefahr ist die unangenehmere: `setze_status` nimmt den Wechsel korrekt
   zurück — *und ein korrekt zurückgenommener Wechsel ist von einem nie versuchten nicht zu
   unterscheiden.* `L-2026-08-17bd`.
10. **1077 Python-Tests, davon 1 rot** (der Altbefund über drei unzulässige Übergänge aus den
    Sprints 13 und 15 — **keiner aus diesem Lauf**), **104 JS-Tests grün** (von 78), Matrix
    **151 SWRs / 0 Lücken**, Briefkasten **0 offen**. ⚠ **Nicht startklar**, und das bleibt
    die richtige Meldung.

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
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: 1077 Python-Tests (1 rot, Altbefund), 104 JS-Tests grün, Matrix 151/0. ⚠ Die Suite läuft in **Blöcken** — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. |
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

**Verifikation:** **1077 Python-Tests, 1076 grün / 1 rot** (der Altbefund über drei
unzulässige Übergänge — **keiner aus diesem Lauf**), **104 JS-Tests grün** (von 78), Matrix
**151 SWRs / 0 Lücken**, Briefkasten **0 offen**, entschiedene unverbuchte DRs **0**,
Plan-Drift 0, Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: zwei aus Sprint 13 (`platform/T-0014`, `pm/T-0064`) und
einer aus Sprint 15 (`pm/T-0052`), **alle unverändert**. Nichts geglättet, kein Test
angepasst, um grün zu werden.

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
