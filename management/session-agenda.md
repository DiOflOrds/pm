# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 16, 2026-08-17)

1. **✅ Der Fehler, den wir dir gestern gemeldet haben, kann jetzt nicht mehr passieren —
   und er ist heute zweimal aufgetreten, ohne Schaden.** Wir hatten geschrieben: einen
   Aufgabenstand zu ändern sind bei uns zwei Schritte, und klemmt der zweite, ist der Stand
   in der Datei und nicht in der Geschichte. Jetzt sind es **keine zwei Schritte mehr**:
   wer den Stand ändert, speichert ihn im selben Zug. Klemmt es, gilt die Änderung als
   **nicht passiert** und die Datei steht wieder wie vorher.
   > **Beim letzten Mal ging es gut aus, weil jemand hingesehen hat. Heute ging es gut aus,
   > weil eine Vorkehrung gegriffen hat — zweimal, an einem echten Fall.**
2. **⚠⚠ Dafür haben wir mitten im Lauf einen Fehler gefunden, der einen ganzen Sprint lang
   unentdeckt war.** Wir hatten letzte Woche eine Reparatur gebaut, die eine bekannte
   Klemme im Speichern automatisch löst. Heute stellte sich heraus: **sie lief meistens gar
   nicht.** Sie suchte ihr Werkzeug an der falschen Stelle und fand es nur, wenn der
   Aufrufer es zufällig schon dabeihatte.
   > **Die Reparatur wirkte überall dort, wo man sie ohnehin mitbrachte — also genau dort
   > nicht, wo sie hin sollte.**

   ⚠ Und das Unangenehmste daran: **unsere Prüfung dafür war die ganze Zeit grün.** Die
   Testdatei brachte das Werkzeug selbst mit. Gefunden hat es kein Test, sondern drei
   Speicherversuche, die während der Arbeit scheiterten.
3. **✅ Die Zahlen, auf die du seit deinem Brief zu den KI-Rollen wartest, sind da — und
   sie sind leer.** Von **7** aufgezeichneten Läufen meldet **kein einziger** Token; bei
   **6 von 7** fehlt die Angabe, um welche Art Aufgabe es ging. Auswertbar ist damit genau
   **ein** Lauf, und der lief über **Ollama**.
   > **Wir wissen jetzt, dass wir es nicht wissen — und an welchen Stellen genau.**

   Wir hätten dir stattdessen sieben Nullen zeigen können. Die hätten wie ein Ergebnis
   ausgesehen.
4. **⚠ Und wir haben uns die naheliegende Bequemlichkeit verboten.** Ein Durchschnitt über
   die Läufe, die zufällig etwas gemeldet haben, ist kein Durchschnitt über die Läufe.
   Jede Zahl in unserem Bericht sagt deshalb dazu, **auf wie vielen von wie vielen** sie
   beruht.
5. **✅ Messen statt schätzen — auch da, wo es unbequem war.** Für die Token verlangst du
   eine Trennung in „fester Anteil" und „wechselnder Anteil". Das Werkzeug liefert nur
   **eine** Zahl. Wir haben die Aufteilung deshalb **nicht** geschätzt, sondern **zweimal
   gemessen** und subtrahiert. Fehlt eine der beiden Messungen, schreiben wir **gar keine**
   Zahl hin.
6. **✅ Eine Aufgabe, die viermal liegengeblieben ist, ist zerlegt und ihr erster Teil
   erledigt:** wir haben nachgemessen, ob unsere Briefanzeige Text verschluckt. **Sie tut
   es nicht** — geprüft an **57** deiner und unserer Briefe.
7. **⚠ Dabei ist unsere eigene Messung zuerst falsch gewesen, nicht die Anzeige.** Sie
   meldete an sieben Briefen „fehlende Zeichen" — es waren die **Nummern der
   Aufzählungen**, die die Anzeige selbstverständlich selbst erzeugt.
   > **Ein erster roter Alarm ist genauso oft ein Fehler des Messgeräts wie einer des
   > Gemessenen.**
8. **✅ Eine Frage, die seit gestern zwischen zwei unserer Teams hing, ist entschieden.**
   Es ging darum, ob eine Zusatzangabe künftig vom Server mitgeliefert wird oder in der
   Anzeige selbst berechnet. Antwort: **vom Server**. Der Grund ist keine Vorliebe, sondern
   Zählung — die zweite Variante hätte dieselbe Regel ein fünftes Mal irgendwo
   hingeschrieben.
9. **936 Tests für die Technik (1 rot, der alte Befund von gestern — unverändert), 51 für
   die Oberfläche (von 45), 143 Anforderungen ohne Lücke.** **Bei dir liegt nichts Neues.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠ **Deine Zählung von vorgestern steht weiter aus** | Wir hatten dich gebeten, im Reiter „Dashboard" nachzusehen, **wie viele Kacheln du ohne Scrollen siehst**. Die Frage ist weiter offen; davon hängt ab, ob auch die lange Sprint-Tabelle im Cockpit eine Kur braucht. ⚠ Wir können es nicht selbst messen — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ✅ **Deine Frage zu den KI-Rollen ist beantwortet — mit einer Messung** | *„Welche Rollen über Claude, welche über Ollama?"* Antwort: **auswertbar ist genau ein Lauf, und der lief über Ollama.** Alles andere ist nicht erhoben. Der Bericht liegt in `promt-team/management/telemetrie-baseline.md`. |
| ⚠ **Unsere Prüfung bleibt rot, und zwar zu Recht** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15 stehen unverändert in der Geschichte. Wir haben nichts umgeschrieben und keinen Stichtag verschoben. Neu dazugekommen ist **keiner**. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es wieder etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was heute wichtig war — in Ruhe erklärt

### Die Vorkehrung, die im selben Lauf gebraucht wurde

Gestern haben wir dir geschrieben, dass „besser aufpassen" keine Reparatur ist. Heute haben
wir die Reparatur gebaut: das Ändern eines Aufgabenstands und das Abspeichern sind **ein**
Vorgang geworden. Klemmt das Speichern, wird die Datei auf den Stand von vorher
zurückgesetzt — Zeichen für Zeichen — und wir bekommen eine Fehlermeldung statt eines
stillen Verlusts.

Und dann ist genau das passiert. Bei einer Aufgabe klemmte es zweimal. Beim ersten Mal
wurde die Änderung zurückgenommen; beim zweiten Anlauf hat unser System den nächsten
Schritt **verweigert**, weil der vorherige noch nicht gespeichert war. Beides ist richtig,
und beides wäre gestern schiefgegangen.

### Der Fehler, der grün getestet wurde

Das ist der Teil, der uns beschäftigt. Wir hatten eine Reparatur für eine bekannte Klemme,
und wir hatten eine Prüfung dafür. Die Prüfung war grün. Die Reparatur lief nicht.

Der Grund: Die Reparatur suchte ihr Werkzeug im falschen Ordner. In der Prüfung fiel das
nicht auf, weil die **Testdatei** den richtigen Ordner ohnehin bereitstellt — sie hat also
die Bedingung selbst hergestellt, die sie prüfen sollte.

> **Eine Prüfung, die ihre eigene Voraussetzung mitbringt, prüft die Voraussetzung und
> nicht die Sache.**

Wir haben es repariert und eine Prüfung geschrieben, die den Ordner ausdrücklich
wegnimmt, bevor sie misst. Was wir **nicht** wissen: wie viele unserer 936 Prüfungen
dieselbe Schwäche haben. Wir haben die Frage aufgeschrieben statt sie für erledigt zu
erklären.

### Warum wir dir keine sieben Nullen zeigen

Du hattest nach Zahlen je KI-Rolle gefragt. Wir könnten dir eine Tabelle mit Nullen
liefern; sie wäre in jeder Zelle formal korrekt und in ihrer Aussage falsch, weil eine Null
zweierlei heißen kann — „gemessen, es war nichts" oder „nie erhoben".

Bei uns steht deshalb überall dabei, auf wie vielen Läufen eine Zahl beruht. Wo es null
sind, steht **„nicht geliefert"** und nicht **„0"**.

Und weil die Aufteilung der Token in einen festen und einen wechselnden Anteil vom Werkzeug
nur als **eine** Zahl kommt, haben wir sie nicht aufgeteilt, sondern ein zweites Mal
gemessen — mit einer Anfrage, die nichts erzeugt und nur zählt. Die Differenz ist dann
keine Schätzung, sondern die zweite Messung.

### Was als Nächstes kommt

Sprint 17: die **Umsetzung** der heute entschiedenen Vertragsfrage, die beiden
Änderungsanträge zum Projekt-Pool (beide zum dritten Mal verschoben — beim vierten Mal
entscheiden wir sie, statt sie noch einmal zu verschieben), und die **Goldset-Fälle**, für
die heute das Format entstanden ist.
