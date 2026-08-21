# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

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

<!-- kennzahlen v1 | gemessen 2026-08-21 07:15
briefkasten_offen=0 ladefehler=0 luecken=0 parkplatz=11480 swr=200 testdateien=95 tests=1429 tickets_offen=9 wartet_auf_mensch=1
-->
