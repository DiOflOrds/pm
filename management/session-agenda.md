# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 12, 2026-08-17)

1. **✅ Der Oberflächen-Lauf hat stattgefunden — und zwei der vier Dinge, die du direkt
   siehst, sind gebaut.** Dein Brief ist jetzt ein **Verlauf mit Antwortfeld**: unter jedem
   Brief steht ein eigenes Feld, jeder Beitrag zeigt Absender und Zeit, und wenn du
   nachfragst, trägt der Brief sichtbar „Nachfrage — wartet auf Antwort". Und die
   abgeschickte Nachricht **erscheint sofort**, ohne Neuladen.
2. **⚠⚠ Der ehrliche Teil zuerst: wir hatten dir vier Dinge zugesagt, und zwei davon
   liegen wieder.** Der Priorisieren-Knopf und der Abschnitt „Für dich: Handlungen" sind
   nicht gebaut. Dazu kommt: wir hatten dir gestern geschrieben, der Dashboard-Endpunkt und
   die Detailseiten kämen *„im Oberflächen-Lauf als Nächstes"* — **das war dieser Lauf, und
   wir haben es nicht geliefert.** Das steht so in den Tickets und hier, nicht in einer
   Fußnote.
3. **⚠⚠ Der Grund ist kein guter, aber ein messbarer — und er sagt etwas über uns.** Deine
   beiden gebauten Wünsche verlangen in ihrer Abnahme einen **Test der Oberfläche**. Beim
   Nachsehen: wir haben **741 Tests für die Technik und null für die Oberfläche**, bei
   1.500 Zeilen Oberflächen-Code. Seit fünf Läufen melden wir dir „Tests grün" — das war
   wahr, für die Tests, **die es gab**.
   > **Eine Prüfung, die es nicht gibt, meldet dasselbe wie eine, die grün ist: nichts.**
4. **Zum dritten Mal in drei Läufen derselbe Fehlertyp — und diesmal in einer neuen
   Gestalt.** Vorgestern: eine Prüfung, die niemand liest. Gestern: eine Regel, die keine
   Prüfung vertritt. Heute: eine **ganze Fläche ohne Prüfung**, an der das Fehlen nicht
   auffiel, weil Fehlen und Erfolg gleich klingen.
5. **✅ Gebaut haben wir deshalb zuerst die fehlende Prüfstrecke** — und zwar so, dass sie
   dich nichts kostet: kein Download, kein Paket, kein Konto. Sie nutzt nur, was in einem
   Werkzeug namens Node ohnehin eingebaut ist.
6. **⚠ Eine Frage dazu liegt bei dir** (`p12/T-0007` in der Inbox, Frist **24.08.**): darf
   Node eine Voraussetzung des Projekts werden? **Es kostet nichts und blockiert nichts** —
   antwortest du nicht, gilt am 24.08. „optional" und alles bleibt wie heute. Details unten.
7. **✅ Dein Wunsch vom 16.08. ist damit vollständig.** „Auf meine Fragen und deine
   Antworten direkt weiter kommentieren" — gestern das Innenleben, heute die Anzeige. Vier
   Verschiebungen, eine Zerlegung, jetzt fertig.
8. **⚠ Eine Aufgabe haben wir nach ZWEI Verschiebungen zerlegt statt nach vier.** Der
   Priorisieren-Knopf besteht aus zwei Dingen — der Liste aller offenen Aufgaben und dem
   Knopf daran. Gestern haben wir gelernt, bei vier Verschiebungen zu zerlegen; heute haben
   wir gefragt, auf **welche anderen** Fälle der Satz gerade zutrifft. Die Liste kommt im
   nächsten Lauf, der Knopf danach.
9. **⚠ Zwei Läufe von uns liefen heute Vormittag gleichzeitig** (10:25–11:21) und schrieben
   in dieselben Dateien. Der zweite hat das gemerkt und **nichts geschrieben**. Ursache:
   unser Sprintzähler kennt keinen *Endezeitpunkt* — er sieht, wann ein Lauf beginnt, nie,
   ob einer noch läuft. Aufgenommen als Aufgabe für den nächsten Lauf.
10. **⚠ Und wir haben uns heute beim Arbeiten selbst eine Datei zerschossen.** Ein
    Hilfsskript hat unsere Prüfstrecke auf **0 Bytes** gekürzt — beim Versuch, sie zu
    ändern, und *bevor* der Fehler gemeldet wurde. Folgenlos, weil wir auf einer Kopie
    gearbeitet haben. Es ist **dieselbe Sache wie `abschluss.cmd` in Sprint 1**, der
    einzige Punkt, der bis heute bei dir liegt. Die Regel dagegen steht jetzt.
11. **✅ Dein Brief von 12:00 ist schon beantwortet — im selben Lauf.** Du willst Aufgaben
    nach Rollen sehen und ein kompakteres Cockpit. Beides kommt im nächsten Lauf. ⚠ Die
    Rollen-Sicht bauen wir **in die Liste hinein**, die wir heute ohnehin geplant haben —
    zwei Listen derselben Sache driften auseinander und sagen dir dann zwei verschiedene
    Dinge. Und beim „kompakter" haben wir einen Widerspruch zu deinem Brief von heute
    Morgen gefunden und dir im Antwortbrief offengelegt statt ihn still aufzulösen:
    **kompakt heißt falten, nicht weglassen.**
12. **754 Tests für die Technik (+13), 16 für die Oberfläche (+16, von null)**, 130
    Anforderungen ohne Lücke, Startcheck startklar — am Ende gemessen. **Es liegt eine
    Sache bei dir: die Node-Frage.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Dein Brief ist jetzt ein Gespräch** | Unter **jedem** Brief steht ein eigenes Antwortfeld — du musst keinen neuen Brief mehr anfangen, um nachzufragen. Jeder Beitrag zeigt, **wer** ihn geschrieben hat und **wann**; deine Beiträge und unsere sind farblich getrennt. Und: fragst du an einem beantworteten Brief nach, springt er auf „offen" zurück **und trägt ein sichtbares Schild** — du siehst, dass deine Nachfrage angekommen ist, statt einen Brief zu sehen, der aussieht wie jeder andere offene. |
| ✅ **Die Nachricht steht sofort da** | Kein Neuladen mehr. ⚠ Und der Fall, an dem es früher unehrlich wurde: schlägt die Verbuchung fehl, ist deine Nachricht trotzdem **gespeichert** — sie liegt auf der Platte, bevor irgendetwas verbucht wird. Früher sahst du dann eine Fehlermeldung und deine Nachricht nicht. Jetzt siehst du sie, mit dem Vermerk „gespeichert, noch nicht verbucht". **Nicht noch einmal senden.** |
| ⚠⚠ **Was wir dir zugesagt und nicht geliefert haben** | Gestern stand hier: der Dashboard-Endpunkt und die Detailseiten kommen „im Oberflächen-Lauf als Nächstes". Der Lauf war heute. Sie sind nicht da — es ist die **dritte** Verschiebung. Auch der Priorisieren-Knopf und „Für dich: Handlungen" liegen weiter. Wir schreiben das hierhin und nicht ans Ende, weil wir dir gestern zugesagt haben, Verzug **laut** zu melden. |
| ⚠⚠ **Warum: wir mussten erst prüfen können, was wir bauen** | Deine beiden Wünsche verlangen in ihrer Abnahme einen Test der **Oberfläche**. Wir haben nachgesehen: 741 Tests für die Technik, **null** für die Oberfläche — bei 1.500 Zeilen Oberflächen-Code. Hätten wir trotzdem gebaut, hätten wir dir zwei Dinge als „geprüft" gemeldet, die niemand geprüft hat. Das ist genau der Fehler, den du zweimal gerügt hast, nur in einer neuen Verkleidung. |
| ⚠ **Eine Frage liegt bei dir — sie kostet nichts** | In der Inbox: **`p12/T-0007`, Frist 24.08.** Unsere neue Oberflächen-Prüfung braucht ein Werkzeug namens **Node**. Kein Geld, kein Download von Paketen, kein Konto, kein Internet — Node bringt den Prüfer selbst mit. Die Frage ist nur, ob dein Rechner das **mitbringen muss**. **Antwortest du nicht, gilt am 24.08. „optional"** und alles bleibt wie heute: fehlt Node, läuft dein Startcheck weiter und sagt dazu „übersprungen". Prüfen kannst du deinen Stand mit `node --version`. |
| ⚠ **Warum wir dabei sehr genau waren** | Wir hätten die neue Prüfung so bauen können, dass sie „grün" meldet, wenn sie gar nicht lief. Das wäre bequem und falsch gewesen — und es ist **exakt der Mechanismus**, durch den „null Oberflächen-Tests" fünf Läufe lang unsichtbar blieb. Sie kennt deshalb **drei** Zustände: grün, rot, **übersprungen**. Der teuerste Test der ganzen Strecke ist der, der verlangt, dass „übersprungen" nie als „grün" durchgeht. |
| ⚠ **Zwei von uns waren heute gleichzeitig unterwegs** | Zwischen 10:25 und 11:21 liefen zwei Routine-Sitzungen parallel und schrieben in dieselben Dateien. Die zweite hat es bemerkt und **nichts geschrieben** — richtig so. Ursache: unser Sprintzähler weiß, wann ein Lauf **anfängt**, nie, ob einer noch **läuft**. Wird im nächsten Lauf repariert. Für dich heißt das: falls ein Bericht heute Vormittag widersprüchlich aussah, war das der Grund. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1, weiter offen)** | Unverändert dein einziger Altpunkt. ⚠ **Und heute ist uns dasselbe noch einmal passiert**: ein Hilfsskript hat unsere Prüfdatei beim Ändern auf 0 Bytes gekürzt, bevor der Fehler überhaupt gemeldet wurde. Ohne Schaden, weil wir auf einer Kopie arbeiteten. Die Regel dagegen steht jetzt schriftlich: erst neben die Datei schreiben, dann umbenennen. |

---

## Was heute wichtig war — in Ruhe erklärt

### ⚠⚠ Die dritte Gestalt desselben Fehlers, in drei Tagen

Du hast in den letzten Läufen zwei Befunde von uns bekommen:

* **vorgestern:** eine Prüfung wurde berechnet und von **niemandem gelesen**.
* **gestern:** eine Regel wurde beschlossen und von **keiner Prüfung** vertreten.

Heute die dritte: eine **ganze Fläche ohne Prüfung**. Die Oberfläche — das, was du
tatsächlich siehst — hatte **null** automatische Tests, während die Technik dahinter 741
hat. Und niemandem fiel es auf, weil eine fehlende Prüfung und eine erfolgreiche Prüfung
dasselbe melden: nichts.

> **Eine Prüfung, die es nicht gibt, ist von einer grünen nicht zu unterscheiden.**

Das erklärt auch, warum unsere Abschlussberichte fünf Läufe lang „Tests grün" sagen
konnten, ohne zu lügen. Der Satz war wahr. Er war nur über etwas anderes wahr, als du beim
Lesen annehmen musstest.

### Was wir daraus gebaut haben

Wir haben die **Entscheidungen** aus der Anzeige herausgezogen. Bisher steckten sie
mittendrin: „male dieses Feld blau, wenn der Beitrag von dir ist" — Entscheidung und
Malerei in einem Satz, prüfbar nur mit einem echten Browser.

Jetzt stehen die Entscheidungen in einer eigenen Datei, die **nichts** über Bildschirme
weiß. Sie beantwortet Fragen: *Von wem ist dieser Beitrag? Ist dieser Brief durch eine
Nachfrage wieder offen?* Solche Fragen kann man ohne Browser prüfen — und genau das tun
jetzt 16 Tests.

⚠ **Fünf dieser 16 sind Gegenproben**, also Fälle, die absichtlich beweisen, dass die Regel
*falsch* wäre, wenn wir sie naheliegender gebaut hätten. Ein Beispiel: „ein Beitrag ist von
dir, wenn der Absender gleich dem Absender des Briefs ist" klingt richtig — ist es aber
nicht, weil du beim Senden einen anderen registrierten Namen wählen darfst. Dein zweiter
Beitrag wäre dann als **unsere** Antwort gezählt worden, und der Brief hätte dir nicht
angezeigt, dass deine Nachfrage aussteht.

### ⚠ Und wir haben die Regel gegen uns selbst gerichtet

Ein ADR ist ein Dokument, und gestern haben wir gelernt, was ein Dokument ohne Prüfung wert
ist. Also haben wir **im selben Lauf** die Prüfung dazu gebaut: Wandert eine Entscheidung
zurück in die Anzeige-Datei, wird ein Test rot.

Nebenbei ist uns dabei etwas Lehrreiches passiert: dieser Test wurde beim ersten Versuch
rot — an einem **Kommentar**. Die Datei erklärt in ihrem Kopf, warum sie den Bildschirm
nicht anfasst, und die Prüfung hat diese Erklärung für einen Verstoß gehalten. Eine
Prüfung, die die Begründung bestraft, erzieht dazu, Begründungen wegzulassen. Korrigiert —
mit einer zweiten Prüfung, die verhindert, dass diese Nachsicht zu viel durchlässt.

### Die Frage, die bei dir liegt — und warum wir sie nicht selbst entschieden haben

Unsere Regel lautet: alles, was **Geld, Recht, Außenwirkung, Zugänge oder ein neues
Werkzeug** betrifft, entscheidest du, nicht wir. Node ist ein neues Werkzeug. Also legen
wir es dir vor, obwohl es nichts kostet.

Wir hätten es leicht anders erzählen können — „ist ja gratis, also Klasse C". Genau diese
Bequemlichkeit ist der Grund, warum es die Regel gibt.

**Was du entscheidest**, in einem Satz je Möglichkeit:

* **A** — Node gehört dazu. Fehlt es, wird dein Startcheck **rot**. Ehrlichste Variante,
  verlangt eine einmalige Installation.
* **B (Default)** — wie heute: läuft, wenn Node da ist; sagt „übersprungen", wenn nicht.
  ⚠ Der Preis: ein Lauf kann „startklar" melden, obwohl die Oberfläche ungeprüft ist. Die
  Zeile sagt es, aber sie hält niemanden auf.
* **C** — wir bauen die Strecke zurück und prüfen die Oberfläche wieder von Hand. Der alte
  Zustand — dann aber **benannt**, mit einer dauerhaften Zeile im Startcheck.

Wir empfehlen **A**, *falls du Node ohnehin hast* (`node --version` sagt es dir), sonst
**B**. Gegen **C** sagen wir nichts Grundsätzliches: es ist die einzige ehrliche Antwort,
wenn du Node nicht auf dem Rechner willst.

### Was als Nächstes kommt

Sprint 13 ist der zweite Oberflächen-Lauf: **„Für dich: Handlungen"**, die
**projektübergreifende Liste** deiner offenen Aufgaben (der erste Teil des
Priorisieren-Knopfs) und der **Dashboard-Endpunkt**. Dazu die Reparatur am Sprintzähler,
damit zwei Läufe sich nicht mehr überholen können.

⚠ Drei dieser Aufgaben liegen zum **dritten** Mal in einer Plantabelle. Bei allen dreien
haben wir heute schon aufgeschrieben, **wo sie zerlegt werden**, falls sie ein viertes Mal
auftauchen — statt die Naht dann erst zu suchen. Das ist der Unterschied zu gestern.
