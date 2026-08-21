# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

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
