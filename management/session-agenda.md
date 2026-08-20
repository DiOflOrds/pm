# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 21, 2026-08-20)

1. **✅ Dein Brief von heute Morgen ist beantwortet — und drei der vier Punkte sind schon
   gebaut.** Die Kachel „Letzte Session" nennt ab jetzt den **Sprint**, der Plan steht in
   **eigenen Kapiteln mit Nummer** („Sprint 21 (aktuell)", „Sprint 22 (nächster)",
   „Später"), und es gibt eine Prüfung, die meldet, wenn eine Aufgabe angefangen und
   liegengeblieben ist.
2. **⚠⚠ Dein dritter Punkt hat uns beim Nachmessen etwas über uns selbst gezeigt.** Die
   Regel „beim Start auf *in Arbeit* setzen" **gibt es bei uns seit dem ersten Sprint**.
   Wir hätten „haben wir schon" antworten können, und es wäre belegbar richtig gewesen.
   Nachgezählt über alle Aufgaben, die wir je geschlossen haben:
   > **159 von 300 hatten den Status nie. Die übrigen trugen ihn im Mittel
   > 22 Sekunden.**

   Wir haben ihn gesetzt, weil unsere Prüfung ihn verlangt — kurz bevor eine Aufgabe
   fertig gemeldet wird. Nicht beim Anfangen, wo er dir etwas sagt. **Ab jetzt beim
   Anfangen**; in diesem Lauf schon so gemacht, du kannst es nachsehen.
3. **⚠ Dein vierter Punkt wäre ohne den dritten wirkungslos gewesen.** „Am Sprintende
   steht nichts mehr auf *in Arbeit*" war bei uns immer erfüllt — nicht aus Disziplin,
   sondern weil der Zustand 22 Sekunden lebte. Eine Prüfung, die auf etwas schaut, das es
   praktisch nicht gibt, ist immer grün und sagt nichts.
4. **⚠⚠ Und wir haben eine Prüfung gefunden, die seit drei Tagen rot ist.** Sie vergleicht
   unseren Mail-Digest mit einem festen Datum. Am 17.08. um **22:22** ist ein neuer
   Digest entstanden — **vier Minuten nachdem wir den letzten Sprint als grün gemeldet
   haben**. Seitdem ist sie rot, und niemand hat es gesehen, weil in diesen drei Tagen
   niemand alle Prüfungen laufen ließ. Wir haben sie **nicht** grün gemacht.
5. **1128 Prüfungen für die Technik** (gezählt, nicht geschätzt), **111 für die
   Oberfläche**, **155 Anforderungen ohne Lücke**.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Dein Brief von heute ist beantwortet und zu drei Vierteln erledigt** | `pm/N-0043`. Punkte 1, 2 und 4 sind gebaut, Punkt 3 ist ab sofort unsere Arbeitsweise. **Einstufung Klasse B** — du musst nichts entscheiden. |
| ⚠ **Sieh dir das neue Cockpit an und sag uns, ob die Kapitel so stimmen** | Wir haben zwei Kapitel („aktuell" und „nächster") **auch dann** stehen lassen, wenn nichts drinsteht — sonst wäre „nichts geplant" von „nicht nachgesehen" nicht zu unterscheiden. „Später" erscheint nur mit Inhalt, so wie du es geschrieben hast. |
| ⚠ **Eine unserer Prüfungen ist rot und bleibt es vorerst** | Nicht wegen eines Fehlers im Programm, sondern weil sie ein Datum festgeschrieben hat. Wir zählen das Datum **nicht** hoch, damit sie grün wird — das würde den Befund nur bis zum nächsten Digest verschieben. Als `platform/T-0024` eingeplant. |
| ⚠ **Der alte rote Befund steht unverändert** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15. Neu dazugekommen ist **keiner**. |
| ⚠ **Die Frage zu den Mail-Zugangsdaten steht weiter offen** | Aus Sprint 17, `team-mail/N-0003`: Sind `MAIL_IMAP_HOST/USER/PASS` in der Umgebung gesetzt, in der die **Routine** läuft? |
| ⚠ **Ollama fehlt weiterhin in unserer Umgebung** | Nachgesehen, nicht vermutet. **Kein Handlungsbedarf**, wenn die Routine ohnehin schon dort läuft, wo Ollama erreichbar ist. |
| ⚠ **Deine Zählung steht weiter aus** | Wie viele Kacheln siehst du im Reiter „Dashboard" **ohne Scrollen**? |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was in Sprint 21 passiert ist — in Ruhe erklärt

### Warum wir auf deinen dritten Punkt nicht „haben wir schon" geantwortet haben

Du hast geschrieben, eine Aufgabe müsse beim Start auf *in Arbeit* gehen. Bei uns steht
diese Regel seit dem allerersten Sprint im Programm, und eine Prüfung erzwingt sie: wer
eine Aufgabe von *offen* direkt auf *fertig* setzt, bekommt einen Fehler.

Wir hätten das schreiben können. Stattdessen haben wir nachgezählt, wie lange dieser
Zustand bei uns tatsächlich existiert hat — über jede Aufgabe, die wir je geschlossen
haben.

**Im Mittel 22 Sekunden.** Bei mehr als der Hälfte gar nicht.

Der Grund ist banal und deshalb lehrreich: Wir haben den Status gesetzt, *weil die
Prüfung ihn verlangt* — also kurz vor dem Fertigmelden, an der Stelle, an der er im Weg
steht. Nicht *beim Anfangen*, wo er dir sagen würde, woran gerade gearbeitet wird.

> **Eine Regel kann buchstabengetreu befolgt und in der Sache verfehlt sein. Unsere
> Prüfung sieht die Reihenfolge der Zustände — du siehst ihre Dauer. Sie hat nichts
> gemerkt, weil sie das Falsche misst.**

### Warum dein vierter Punkt auf den dritten warten musste

Du willst, dass am Ende eines Sprints kein *in Arbeit* mehr dasteht. Das war bei uns
immer schon so — aber nicht, weil wir sauber abschließen, sondern weil der Zustand
ohnehin nur Sekunden lebte. Eine Prüfung darauf wäre grün gewesen und hätte nichts
geprüft.

Jetzt, wo der Status von Anfang an steht, hat sie einen Sinn. Sie **meldet** und räumt
nicht auf: ein Programm, das den Status am Sprintende stillschweigend zurückstellt,
würde ein Liegenbleiben unsichtbar machen — und dann hättest du wieder eine Anzeige, die
schöner ist als die Lage.

### Die rote Prüfung, die drei Tage niemand gesehen hat

Eine unserer Prüfungen liest den echten Mail-Digest und vergleicht ihn mit dem Datum
`2026-08-16`. Am 17.08. um 22:22 ist der Digest vom 17. entstanden — vier Minuten
nachdem wir Sprint 20 als abgeschlossen und grün gemeldet hatten.

Das ist zum zweiten Mal innerhalb von vier Tagen dasselbe Muster: **etwas trifft ein,
nachdem der Bericht geschrieben ist.** Beim ersten Mal war es deine Entscheidung, die um
21:57 kam und die der Bericht von 21:45 nicht kennen konnte. Diesmal eine Textdatei.

Wir haben das Datum in der Prüfung **nicht** hochgezählt. Das hätte sie grün gemacht und
den Befund bis zum nächsten Digest verschoben. Die eigentliche Frage — darf eine Prüfung
überhaupt ein Datum festschreiben, wenn der Ordner von selbst weiterwächst? — steht als
eigene Aufgabe.

### Und eine Zahl in unserem eigenen Bericht war zum dritten Mal geschätzt

Im Entwurf dieses Berichts stand **1155** Prüfungen. Gezählt sind es **1128**. Wir haben
es vor dem Speichern korrigiert — aber wieder durch Nachzählen und nicht, weil irgendeine
Prüfung uns darauf gestoßen hätte. Das ist nach Sprint 18 und 19 das dritte Mal, und wir
schreiben es hin, weil es die Lage ist.

---

# Anhang: Sprint 20 — was dort wichtig war

## Das Wichtigste (Stand Sprint 20, 2026-08-17)

1. **✅ Deine beiden Entscheidungen sind angekommen und verbucht.** Die eine (`p12/T-0010`,
   G4) ging beim ersten Versuch durch; die andere (`promt-team/T-0009`) nicht — **und der
   Fehler lag bei uns.**
2. **⚠⚠ Warum die zweite gescheitert ist.** Für das promt-team gab es das Buch nicht, in
   dem Entscheidungen festgehalten werden — es wird beim **Gründen** eines Teams angelegt,
   und dieses Team ist anders entstanden.
   > **Der Weg setzte etwas voraus, das ein anderer Weg herstellt. Solange jedes Team
   > normal gegründet wurde, war die Annahme unsichtbar richtig.**
3. **⚠⚠ Keine unserer über tausend Prüfungen hätte das finden können** — jede Prüfung baut
   sich ihre Ordner selbst.
4. **✅ Damit ist P12 abgenommen.** Dein **G4** steht; die Baseline `p12-v1.0` ist fertig.
5. **⚠ Eine deiner Entscheidungen hätten wir fast übersehen** — sie kam zwölf Minuten
   **nach** unserem Abschlussbericht.
6. **1087 Prüfungen für die Technik, 104 für die Oberfläche, 152 Anforderungen ohne
   Lücke.**
