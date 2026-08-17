# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 13, 2026-08-17)

1. **⚠⚠ Zuerst eine Entschuldigung: wir haben dich um eine Antwort gebeten, die du zwölf
   Minuten zuvor gegeben hattest.** Du hast die Node-Frage (`p12/T-0007`) um **11:48** mit
   „B — optional" beantwortet. Unser System hat deine Antwort angenommen und gespeichert.
   Danach haben wir dir in **drei Berichten** geschrieben, die Frage liege noch bei dir,
   Frist 24.08. — und **es ist eine E-Mail an dich hinausgegangen**, die dir einen „Neuen
   Decision Request" ankündigte, den du schon beantwortet hattest.
2. **Der Grund, in einem Satz: deine Antwort landete im Fließtext des Tickets, und unsere
   Prüfungen lesen nur Felder.**
   > **Eine Entscheidung im Fließtext ist für jede Prüfung unsichtbar.**
   Für „ist das entschieden?" gab es bei uns **vier verschiedene Antworten** an vier
   Stellen. Das Schlimmste daran: sie waren nicht alle falsch. Das Cockpit hat es **richtig**
   gemacht und deine Frage nach der Antwort nicht mehr angezeigt — der Startcheck hat sie
   weiter angezeigt. Zwei richtige Anzeigen, die sich widersprechen.
3. **✅ Repariert, und zwar an einer Stelle statt an vier.** Es gibt jetzt genau **eine**
   Antwort auf „ist das entschieden?", und alle vier Stellen fragen dort. Dazu eine neue
   Prüfung, die anschlägt, wenn eine Antwort von dir da ist und wir sie noch nicht verbucht
   haben. ⚠ Und ein Test, der **zählt**, dass es bei einer Stelle bleibt — sonst wäre „eine
   Stelle" eine Aussage über heute und nicht über nächste Woche.
4. **⚠ Der unangenehmste Teilbefund: unser eigener Test hat den Fehler zugesichert.** Der
   Test, der prüft, dass wir dich nicht an eine Frist erinnern, verlangte in derselben Zeile
   ausdrücklich, dass die „Neuer-Vorgang"-Mail hinausgeht. Das Fehlverhalten war also nicht
   ungeprüft — es war **geprüft und bestätigt**.
   > **Eine Prüfung, die den Fehler zusichert, ist schlimmer als keine.** Sie verteidigt ihn
   > gegen jede Änderung.
5. **✅ Beide Zusagen von gestern sind eingelöst.** Wir hatten dir geschrieben, die Liste
   aller offenen Aufgaben und das kompaktere Cockpit kämen „im nächsten Lauf". **Das war
   dieser Lauf, und beides ist da** — Details unten.
6. **⚠⚠ Und der ehrliche Teil: `p11/T-0008` liegt zum zweiten Mal in Folge unerledigt.**
   Der Dashboard-Endpunkt und die Detailseiten. Wir haben ihn dir in Sprint 11 zugesagt, in
   Sprint 12 nicht geliefert, und heute wieder nicht. Dazu zwei weitere Aufgaben, die zum
   **vierten** Mal verschoben sind. Bei vier Verschiebungen ist unsere eigene Regel:
   zerlegen. Wir haben es heute nicht getan. Die Trennstellen liegen benannt bereit.
7. **⚠⚠ Wir haben uns heute selbst bei einem Regelbruch erwischt — und ihn stehen
   lassen.** Beim Reparieren haben wir ein Ticket geschlossen, dann noch einen Fehler
   gefunden und es wieder aufgemacht. Das war richtig. Falsch war die Buchführung: wir haben
   einen Zwischenschritt nicht mit aufgeschrieben, und unsere Prüfung meldet dafür jetzt
   **einen unzulässigen Übergang**. Wir haben ihn **nicht weggeräumt** — kein Verschieben
   des Maßstabs, kein Umschreiben der Historie. Ein grüner Bericht, der durch Verschieben
   des Maßstabs grün wird, ist nichts wert.
8. **⚠ Eine Frage haben wir dir NICHT beantwortet, weil wir sie nicht messen können.** Beim
   kompakteren Cockpit stand in unserer eigenen Abnahme: *„wie viele Kacheln passen bei
   1920×1080 vor und nach der Änderung auf eine Seite?"* Dafür braucht man einen echten
   Browser, und den hat unsere Prüfstrecke bewusst nicht. **Wir haben gebaut, was du wolltest,
   und wissen nicht, um wie viel es besser wurde.** Zehn Sekunden von dir würden es klären —
   siehe unten.
9. **786 Tests grün, 1 rot (unser eigener Regelbruch aus Punkt 7), 29 Oberflächen-Tests grün
   (von 16), 133 Anforderungen ohne Lücke.** **Es liegt eine kleine Sache bei dir:** einmal
   Kacheln zählen.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **Entschuldigung: doppelte Nachfrage zur Node-Frage** | Deine Antwort von 11:48 („optional") war bei uns angekommen und gespeichert. Trotzdem haben dir drei Berichte und eine E-Mail gesagt, die Frage sei noch offen. **Deine Antwort war nie verloren** — sie war nur an einer Stelle notiert, an die unsere Prüfungen nicht schauen. Sie ist jetzt verbucht: **Node bleibt optional**, alles bleibt wie es ist. |
| ✅ **Neuer Reiter „Aufgaben" — alle offenen Aufgaben aller Teams und Projekte** | Direkt hinter dem Cockpit. **Nichts ist gekürzt** — das war der Punkt: du wolltest priorisieren, dazu musst du alles sehen. Voreinstellung ist **nach Rollen gruppiert** (dein Wunsch von 12:00), ein Knopf schaltet auf eine flache Liste. Jede Zeile zeigt **Rolle** und daneben getrennt **wer handelt** (Team oder du). ⚠ Bewusst **nicht** nach Dringlichkeit vorsortiert: das wäre eine erste Priorisierung neben deiner. |
| ✅ **Cockpit kompakter — zugeklappt heißt nicht weg** | Die drei Gruppen („Feste Teams", „Projekt-Teams", „Aktive Projekte") lassen sich zuklappen. **Die Zahl bleibt immer am Titel** stehen, also verschwindet nichts ohne Zähler. Der Zustand bleibt, wenn du zwischen Reitern wechselst. ⚠ Dein Wunsch von 06:20 („alles sehen") und der von 12:00 („weniger Scrollen") ziehen gegeneinander; wir haben es als **falten statt weglassen** aufgelöst — und dir das gesagt, statt es still zu entscheiden. |
| ⚠ **10 Sekunden von dir: Kacheln zählen** | `pm/T-0068`. Cockpit öffnen, Fenster 1920×1080, zählen: wie viele Projektkacheln siehst du **ohne Scrollen** — einmal mit offenen, einmal mit zugeklappten Gruppen? Zwei Zahlen in den Briefkasten, das reicht. **Warum du und nicht wir:** die Frage braucht einen echten Browser; unsere Prüfstrecke hat bewusst keinen, und ein zusätzliches Werkzeug dafür wäre wieder eine Frage an dich. Antwortest du nicht, passiert nichts — das Falten wirkt, es bleibt nur unbeziffert. |
| ⚠⚠ **Was wir dir zugesagt und wieder nicht geliefert haben** | `p11/T-0008` (der Endpunkt für die Dashboard-Kacheln und die Detailseiten): **zweiter Lauf in Folge nach einer ausdrücklichen Zusage.** Dazu `pm/T-0052` („Für dich: Handlungen") und `promt-team/T-0001` (die Messgrundlage, auf die du wartest) — beide zum **vierten** Mal verschoben. Unsere eigene Regel sagt: bei vier wird zerlegt. Heute nicht getan. Das steht hier oben und nicht am Ende. |
| ⚠ **Wir haben uns selbst einen Regelverstoß gebucht** | Beim Reparieren haben wir ein Ticket geschlossen, einen weiteren Fehler gefunden und es wieder geöffnet — richtig. Nur haben wir einen Zwischenschritt nicht mit aufgeschrieben, und unsere Prüfung meldet dafür einen unzulässigen Sprung. **Er bleibt sichtbar.** Ein Bericht, der durch das Verschieben seines Maßstabs grün wird, wäre wertlos. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1, weiter offen)** | Unverändert dein einziger Altpunkt. |

---

## Was heute wichtig war — in Ruhe erklärt

### ⚠⚠ Deine Antwort war da, und wir haben sie nicht gelesen

Um 11:48 hast du geklickt. Unser System hat deine Wahl übernommen, in das Ticket
geschrieben und gespeichert — alles korrekt. Zwei Minuten später hat derselbe Lauf begonnen,
die Berichte für dich zu schreiben. Und in denen stand: *„Es liegt eine Sache bei dir: die
Node-Frage."*

Der Grund ist so einfach, dass er unangenehm ist. Deine Antwort wurde als **Satz** in den
Ticket-Text geschrieben. Unsere Prüfungen lesen aber keine Sätze, sie lesen **Felder** — und
das Feld „Status" hat niemand umgestellt, weil das absichtlich unsere Arbeit ist und nicht
die deines Klicks (wir wollen nicht, dass dein Knopfdruck unseren Arbeitsstand verändert).

Dieser Handgriff hat **42 Mal funktioniert**. Er hat heute versagt, weil deine Antwort
**mitten im Lauf** kam: nach der Planung, vor den Berichten. Genau dort greift kein Handgriff.

### Das Beunruhigende: nicht alle unserer Anzeigen lagen falsch

Wir hatten **vier** Stellen, die entscheiden, ob eine Frage beantwortet ist — und sie waren
sich nicht einig. Das Cockpit hat es richtig gemacht: es hat deine Frage nach 11:48 nicht
mehr als offen geführt. Der Startcheck hat sie weiter geführt. Die E-Mail-Benachrichtigung
war die **schwächste** von allen und hat als einzige einen Menschen erreicht — dich.

> **Der Preis von vier Wahrheiten über ein Wort ist nicht eine falsche Anzeige. Es sind
> zwei richtige, die sich widersprechen — und du weißt nicht, welcher du glauben sollst.**

Repariert ist es an **einer** Stelle. Alle vier fragen jetzt dort. Und weil wir beim ersten
Anlauf zwei der vier übersehen haben (gefunden erst durch eine Suche im Quelltext), gibt es
jetzt einen Test, der die Stellen **zählt**.

### Der Test, der den Fehler verteidigt hat

Das ist der Teil, den wir dir am wenigsten gern schreiben. Es gab einen Test für die
E-Mail-Benachrichtigung. Er prüfte korrekt, dass wir dich nicht an eine Frist erinnern, wenn
du schon geantwortet hast. In **derselben Zeile** verlangte er, dass die „Neuer
Vorgang"-Mail trotzdem hinausgeht.

Das Fehlverhalten war also nicht unbemerkt. Es war **festgeschrieben**. Jeder, der es
korrigiert hätte, hätte einen roten Test bekommen und wäre wahrscheinlich zurückgerudert.

Wir haben in den letzten Läufen mehrfach gelernt, was eine fehlende Prüfung kostet. Das hier
ist die nächste Stufe: eine Prüfung, die das Falsche festhält, ist teurer als keine.

### Warum bei dir ein roter Test liegen bleibt

Beim Reparieren haben wir das Ticket geschlossen, danach zwei weitere Fehlerstellen gefunden
und es **wieder aufgemacht**. Das ist ausdrücklich vorgesehen; wir zählen sogar, wie oft es
passiert.

Nur haben wir dabei geschludert: intern ist das Ticket über einen Zwischenschritt gelaufen,
aber wir haben nur Anfang und Ende aufgeschrieben. Unsere Prüfung sieht deshalb einen Sprung,
den es nicht geben darf, und wird rot.

Wir könnten das in einer Minute grün machen — Stichtag verschieben, Test anpassen, Historie
umschreiben. Wir tun es nicht. **Ein grüner Bericht, der durch Verschieben des Maßstabs grün
wird, sagt dir nichts.** Genau diesen Satz haben wir gestern gelernt, als wir gemerkt haben,
dass „Tests grün" fünf Läufe lang über etwas anderes wahr war, als du beim Lesen annehmen
musstest.

### Viermal an einem Tag derselbe Mechanismus

Wenn man die Befunde dieses Laufs nebeneinanderlegt, ist es immer dieselbe Bewegung: **die
Regel war bekannt, und sie wurde beim Nachbarn nicht angewandt.**

* Gestern haben wir gelernt, den Briefkasten **zweimal** zu prüfen, weil bei einem
  Stundentakt eine Nachricht mitten im Lauf normal ist. Für **Entscheidungen** — die über
  denselben Weg kommen — haben wir es nicht gemacht.
* Beim Reparieren haben wir drei von fünf Stellen umgestellt und zwei übersehen.
* Ein Test hielt das Falsche fest.
* Und wir selbst haben einen Statusschritt nicht aufgeschrieben.

Die nützlichste Frage, die wir haben, ist deshalb nicht „was ist kaputt", sondern: *auf
welche anderen offenen Fälle trifft dieser Satz gerade zu?*

### Was als Nächstes kommt

Sprint 14: **die drei Zerlegungen, die heute liegen geblieben sind** (`p11/T-0008`,
`pm/T-0052`, `promt-team/T-0001`) — bei allen dreien ist die Trennstelle benannt, es ist
keine Denkarbeit mehr. Dazu der Knopf zum Priorisieren (`pm/T-0065`, jetzt entsperrt), die
Reparatur am Sprintzähler und die Lock-Räumung, die auf deinem Rechner nicht funktioniert.

⚠ Zum Sprintzähler eine Messung, die unseren eigenen Plan widerlegt hat: wir wollten
„weniger als eine Stunde her" als Erkennungsmerkmal für einen noch laufenden Nachbarlauf
nehmen. Gemessen über 12 Abstände: **Median 57 Minuten, Minimum 15.** Diese Regel hätte
**7 von 12** völlig normalen Läufen abgewiesen. Der Takt war eine Annahme, keine Messung —
das Ticket hatte selbst verlangt, das vorher zu prüfen, und diesmal haben wir es getan.
