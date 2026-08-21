# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Sprint 30, 2026-08-21)

1. **✅ Dein 15-Minuten-Takt bricht nicht mehr ab — und das ist jetzt gemessen statt
   vorhergesagt.** Letzter Sprint stand hier *„das ist eine Vorhersage, keine Messung"*.
   Um **04:15** steht im Log zum ersten Mal `STARTKLAR`. Davor: **65** Abbrüche.
2. **⚠⚠ Dahinter kam sofort der nächste Grund zum Vorschein, und der erste hatte ihn
   verdeckt: der Takt läuft jetzt — und findet nichts zu tun.**
   Er suchte sich die wichtigste offene Aufgabe, stellte dann fest, dass niemand sie in
   der lokalen Besetzung bearbeiten darf, und hörte auf. **Die zweitwichtigste hat er nie
   angesehen.**
   > **Eine Prüfung, die erst nach der Auswahl greift, ist kein Filter — sie legt gegen
   > genau einen Kandidaten ein Veto ein und lässt den Rest ungesehen.** Repariert.
3. **⚠⚠ Und die Meldung war zwar wahr, aber zu eng — genau das ist teuer.** Sie las sich
   wie ein Zufall (*„diese eine Aufgabe passt nicht"*). Tatsächlich ist es ein Zustand:
   **keine einzige** deiner 8 offenen Aufgaben kann von den beiden lokalen Besetzungen
   bearbeitet werden.
   > **Die enge Formulierung lädt dazu ein, es in 15 Minuten nochmal zu versuchen — und
   > genau das ist 90-mal passiert. Jetzt steht im Log, wie viele Aufgaben geprüft wurden
   > und dass ein weiterer Lauf daran nichts ändert.**
   ⚠ **Das ändert nichts daran, dass nichts gearbeitet wird.** Das kann nur deine Antwort
   auf `pm/T-0077`.
4. **✅ Die Frage nach den Entscheidungsnummern ist zu Ende gezählt — und die Zahl hat den
   Bau wieder verändert.** Von 1023 Nennungen ohne Ordnerangabe sind **nur 214 wirklich
   mehrdeutig** (21 %); der Rest steht dort, wo die Datei selbst sagt, welche gemeint ist.
   > **Und alle 214 nennen eine von **vierzehn** Nummern: `D000` bis `D013`. Ab `D014` ist
   > jede Nummer im ganzen Haus nur einmal vergeben.** Also haben wir nicht 1023
   > Fundstellen aufgeräumt, sondern eine Sperre eingebaut, die dafür sorgt, dass es bei
   > vierzehn bleibt.
5. **⚠⚠ Der unangenehmste Punkt betrifft unsere eigene Prüfung von letztem Sprint.** Sie
   soll melden, wenn eine neue Lehre ohne Absicherung bleibt. **Drei Lehren aus diesem
   Lauf hat sie nicht gesehen** — sie waren mit einem Punkt statt einem Doppelpunkt
   geschrieben.
   > **Schlimm ist nicht, dass drei durchgerutscht sind. Schlimm ist, dass die Prüfung
   > dabei grün blieb. Eine Sperre, die man mit einem anders gesetzten Satzzeichen umgeht,
   > ist keine.**
   Nachgezählt: von 111 Lehren erkennt sie **34**; **110** tragen tatsächlich eine Regel.
   Die drei sind nachgezogen, die Lücke ist aufgeschrieben und terminiert — **nicht**
   schnell repariert, weil die naheliegende Reparatur rund hundert Dauerwarnungen erzeugt
   hätte.
6. **1404 Prüfungen für die Technik** über 93 Dateien (gezählt, und durch eine zweite,
   unabhängige Rechnung bestätigt), **197 Anforderungen ohne Lücke**. Briefkasten: **0
   offen**, keiner eingegangen. Offene Aufgaben: **9** (zwei geschlossen, zwei neu
   angelegt).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt). **B** = dein 15-Minuten-Takt bekommt echte Aufgaben. **C** = der Ollama-Zweig wird beendet. ⚠ **Neu seit heute:** die Frage ist jetzt die *einzige* Sperre. Alles Technische davor ist repariert. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus drei komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Der Abbruch deines Schnelltakts hat aufgehört** | Wie letzten Sprint vorhergesagt — und diesmal **gemessen**: 04:15, `STARTKLAR`. Du musst dafür nichts tun. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11325 Dateien** (Stand 05:06). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Zwei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Unsere Prüfung aus dem letzten Sprint hätte drei Lehren dieses Laufs
stillschweigend übersehen. Wir haben es nur gemerkt, weil wir nachgesehen haben, ob die
Zahl sich bewegt — sie tat es nicht. **Eine Prüfung, die grün bleibt, sagt nicht dasselbe
wie eine Prüfung, die gesehen hat.**

**Zweitens:** Wir hatten geplant, die Nennungen der Entscheidungsnummern im Text zu
sichern. Beim Bauen ist aufgefallen, dass die Zahl allein dadurch stieg, dass wir
**über** das Problem geschrieben haben — 1023 wurden zu 1030. **Eine Prüfung auf diese
Zahl hätte jeden Bericht bestraft, der den Befund erklärt.** Deshalb sichern wir jetzt die
Nummernvergabe und nicht den Text.

---

<details><summary>Archiv: Sprint 29</summary>

## Das Wichtigste (Sprint 29, 2026-08-21)

1. **✅ Fünf Aufgaben abgeschlossen, keine einzige verschoben.** Darunter beide, die
   letzter Sprint ausdrücklich für „diesmal" angekündigt hatte, und eine, die zum vierten
   Mal drankam und deshalb gebaut werden **musste**.
2. **⚠⚠ Die Fehlermeldung, die deinen 15-Minuten-Takt bei jedem Lauf abgebrochen hat, ist
   weg — und sie war falsch, wie letzter Sprint vermutet hat.** Die Prüfung hat den
   **Zwischenspeicher** von Git angesehen statt die **Dateien**. Jetzt sieht sie die
   Dateien.
   > **Eine falsche Fehlermeldung ist teurer als gar keine: sie stoppt genauso wie eine
   > echte, und man kann nichts dagegen tun. Das bringt einem bei, Warnungen zu
   > überlesen.**
   Der Preis steht dabei: die Prüfung dauert jetzt **7,6 Sekunden länger** über alle 17
   Ordner. Nachgemessen, nicht geschätzt.
3. **✅ Dein Wunsch aus dem Brief vom 20.08. ist gebaut: Kommentare an Aufgaben.**
   *„ähnlich wie hier beim Team-Chat"* — und genau so: der Beitrag steht **in der Aufgabe
   selbst**, nicht in einem zweiten Speicher. **Auch an schon erledigten Aufgaben**, weil
   das der häufigste Anlass für eine Rückfrage ist.
   ⚠ Zwei Dinge, denen du widersprechen darfst, sind wie beantragt gebaut: die Kommentare
   gehen mit nach GitHub, und sie brauchen die PIN.
4. **⚠⚠ Drei Aufgaben stehen zum ersten Mal ehrlich als „blockiert" — nach vier
   Verschiebungen.** Wir konnten bisher nicht eintragen, dass eine Aufgabe auf eine
   Aufgabe in einem **anderen** Ordner wartet. Jetzt geht es.
   > **Und beim Eintragen ist etwas aufgefallen, das unangenehmer ist: eine der drei
   > wartet auf eine Aufgabe im SELBEN Ordner. Da wäre „blockiert" die ganze Zeit möglich
   > gewesen. Es hat nur nie jemand versucht.**
5. **⚠⚠ Unsere eigenen Prüfungen haben uns dreimal beim Fehler erwischt — und das ist die
   beste Nachricht des Laufs.** Zweimal war ein Speichervorgang stillschweigend
   fehlgeschlagen, und die Prüfung hat den daraus entstehenden falschen Zustand gemeldet.
   Einmal hat ein Zähler eine Nebenwirkung gefunden, die sonst durchgegangen wäre.
   > **Wir haben es jeweils repariert und danach eine Regel eingebaut, die verhindert,
   > dass es unbemerkt bleibt: jeder Speicherschritt prüft jetzt, ob er wirklich
   > gespeichert hat.**
6. **⚠⚠ Und eine neue Prüfung war zuerst wertlos, ohne dass man es gesehen hätte.** Sie
   sollte finden, welche Lehren nie in eine Prüfung überführt wurden — und hat sich dabei
   **selbst mitgelesen**. Ein Beispiel in einem Kommentar reichte, damit eine Lehre als
   „erledigt" galt.
   > **Eine Prüfung, die ihre eigene Frage beantworten kann, prüft nicht mehr.** Behoben,
   > und es gibt jetzt eine zweite Prüfung, die genau das nachweist.
7. **✅ Zweimal „erst zählen, dann bauen" — und beide Male hat die Zahl die Frage
   verändert.** Bei den Lehren: 108 insgesamt, 34 mit klarer Regel, **29 davon ohne jede
   Absicherung**. Bei den Entscheidungsnummern: **1003** Nennungen ohne Ordnerangabe gegen
   319 mit — aber die größten Posten stehen in den Entscheidungslisten selbst, wo die
   Angabe gar nicht mehrdeutig ist. **Also sind es nicht 1003 Probleme**, und den Rest
   trennen wir im nächsten Lauf.
8. **1367 Prüfungen für die Technik** über 90 Dateien (gezählt), **195 Anforderungen ohne
   Lücke**, 113 Oberflächen-Prüfungen grün. Briefkasten: **0 offen**, keiner eingegangen.
   Offene Aufgaben: **8** (vorher 15).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt); drei Aufgaben bleiben gesperrt, jetzt aber **ehrlich als gesperrt gebucht** statt weitergeschoben. **B** = dein 15-Minuten-Takt bekommt echte, mechanische Aufgaben. **C** = der Ollama-Zweig wird beendet und die drei Aufgaben geschlossen. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus zwei komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Der Abbruch deines Schnelltakts sollte aufhören** | Die falsche Fehlermeldung ist repariert. ⚠ **Das ist eine Vorhersage und keine Messung** — wir können deinen Takt von hier aus nicht auslösen. Wenn er weiter abbricht, sag Bescheid: dann ist es etwas anderes. |
| ⚠ **Server neu starten** (Mission Control) | Der Kommentar-Kasten an den Aufgaben lädt erst nach einem Neustart. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11138 Dateien** (Stand 03:39). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Zwei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Wir haben in diesem Lauf **zweimal** einen Speichervorgang für gelungen
gehalten, der fehlgeschlagen war — weil wir die Ausgabe unterdrückt und das Ergebnis nicht
nachgesehen haben. Beide Male hat es eine Prüfung gefunden, nicht wir. Die Regel steht
jetzt im Ablauf: **jeder Speicherschritt prüft nach, ob er wirklich gespeichert hat.**

**Zweitens:** Wir haben eine Aufgabe gefunden, die vier Sprints lang „verschoben" wurde,
obwohl „blockiert" die ganze Zeit möglich war — im selben Ordner, ohne jede Werkzeuglücke.
Letzter Sprint hatten wir für einen ähnlichen Fall noch das Werkzeug verantwortlich
gemacht, und das war dort auch richtig. **Hier gibt es diese Entschuldigung nicht.**

---

## ⚠ Eine Zahl, die zuerst nicht aufging — und warum sie jetzt aufgeht

Ein erster Zwischenstand ergab **1342** Prüfungen, das Zählwerkzeug meldete **1367**.
Statt die schönere Zahl zu nehmen, haben wir nachgemessen: **die Suite war in Ordnung,
unsere Messung nicht.** Wir hatten die Blöcke zu verschiedenen Zeitpunkten gefahren, und
fünf der neuen Prüfdateien gab es beim frühen Block noch gar nicht.

Neu gemessen: 436 + 111 + 28 + 350 + 209 + 108 + 56 + 69 = **1367** — und das Zählwerkzeug
sagt ebenfalls 1367. **Zwei unabhängige Wege, dasselbe Ergebnis.**

> **Eine Summe aus Teilmessungen zu verschiedenen Ständen ist keine Summe.**


</details>
