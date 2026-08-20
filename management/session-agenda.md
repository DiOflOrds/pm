# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 24, 2026-08-20)

1. **✅ Drei Aufgaben, die zusammen zehnmal verschoben worden waren, sind erledigt.** Alle
   drei standen zum **vierten** Mal an, und bei uns gilt dann: gebaut oder gestrichen.
   Keine ist ein viertes Mal verschoben worden.
   > **Der Grund für jede einzelne Verschiebung war „keine Zeit", und er war jedes Mal
   > wahr. Er wird nicht falsch, wenn man ihn viermal aufschreibt — er hört nur auf, eine
   > Aussage zu sein.**
2. **✅ Der Umbau, den wir dreimal aufgeschoben haben, ist durch — und die teuerste Stelle
   war die, an der nichts zu tun war.** Wir haben eine alte, ungenutzte Schnittstelle
   ausgebaut. Direkt daneben steht Code, der **genauso aussieht** und in Wahrheit an einer
   ganz anderen, abgenommenen Zusage hängt.
   > **Hätten wir ihn mitgenommen, wäre nichts rot geworden: unsere Prüfung fragte nur,
   > ob das Alte weg ist. Sie fragt ab jetzt beides — was weg sein muss und was dableiben
   > muss.**
3. **⚠⚠ Bei einem alten Werkzeugärger haben wir vier Sprints lang den Falschen verdächtigt.**
   Unsere Commits scheitern gelegentlich an einer Sperre. Wir dachten, sie bleibe liegen,
   wenn etwas **schiefgeht**. Gemessen: sie bleibt liegen, wenn etwas **klappt** — und
   zwar ausgerechnet beim harmlosesten Vorgang, dem reinen Nachsehen.
   > **Der Grund ist die Umgebung: Umbenennen darf unser Ordner, Löschen nicht. Wer
   > schreibt, benennt um und kommt durch. Wer nur liest, will löschen und scheitert.**

   Repariert. Ab jetzt räumt jeder Aufruf hinter sich her, statt die Rechnung dem nächsten
   zu hinterlassen.
4. **✅ Eine Zahl, die niemand je gemessen hat, ist jetzt sichtbar.** Weggeräumte Sperren
   werden bei uns nicht gelöscht (das darf der Ordner nicht), sondern beiseitegelegt.
   Inzwischen liegen dort **9382 Dateien**. Das ist kein Fehler und von hier aus nicht
   reparierbar — aber es steht ab sofort in jedem Startcheck.
   ⚠ Du kannst diesen Ablageplatz gelegentlich auf deinem Rechner leeren
   (`.git/verwaiste-locks` in den Projektordnern). **Eilig ist es nicht.**
5. **⚠⚠ Unser größter Fund heute ist wieder einer über uns selbst — und wieder hat ihn eine
   alte Prüfung gemacht.** Wir haben eine Regel gebaut, die wörtlich sagt: *dieser eine
   Textbaustein darf nur an einer Stelle stehen.* Und beim Bauen haben wir eine zweite
   Stelle angelegt.
   > **Aufgefallen ist es nicht uns, sondern einer Prüfung aus einem früheren Sprint, die
   > nichts weiter tut, als mitzuzählen, in wie vielen Dateien ein Textbaustein vorkommt.
   > Zum zweiten Lauf in Folge hat eine alte Prüfung unseren eigenen Entwurf gestoppt.**
6. **⚠ Und zum achten Mal stand eine geschätzte Zahl da, wo eine gemessene hingehört** —
   diesmal unter einer Überschrift, die ausdrücklich *„gezählt, nicht übersehen"* heißt.
   Korrigiert. Der Fall hat uns aber etwas gebracht: er zeigt, dass die naheliegende
   Lösung für dieses wiederkehrende Problem **nicht funktioniert hätte**.
7. **1201 Prüfungen für die Technik** (gezählt, nicht geschätzt), **111 für die
   Oberfläche**, **165 Anforderungen ohne Lücke**. Rote Prüfungen: **eine** — der bekannte
   Altbefund. ✅ **Zum ersten Mal seit zwei Läufen ist er nicht gewachsen.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠ **Eine neue Frage an dich gibt es NICHT** | Dieser Lauf hat nichts vorgelegt, was du entscheiden müsstest. |
| ⚠ **Wir melden wieder einen eigenen Fehler** | Wir haben beim Bauen einer Regel gegen sie selbst verstoßen. Gefunden hat es eine Prüfung aus einem früheren Sprint, nicht wir. Repariert und aufgeschrieben. **Klasse B**, du musst nichts entscheiden. |
| ⚠ **Eine geänderte Anforderung** | `SWR-135` (das Dashboard) ist auf seine **Layout-Hälfte** zurückgeschnitten worden — die Ausführung deiner Entscheidung vom 17.08. Eine abgenommene Anforderung zu ändern gehört dokumentiert, deshalb steht es hier. |
| ⚠ **Die alten Punkte stehen unverändert** | Die Mail-Zugangsdaten (`team-mail/N-0003`), Ollama in der Umgebung, deine Zählung der Kacheln im Reiter „Dashboard", und `abschluss.cmd` aus Sprint 1. |
| ⚠ **Neu und nicht eilig** | In den Projektordnern liegt unter `.git/verwaiste-locks` inzwischen einiges an Ballast (9382 Dateien). Wir können ihn nicht löschen, du schon. Es stört nichts. |
| ✅ **Zu pushen gibt es etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was in Sprint 24 passiert ist — in Ruhe erklärt

### Warum wir heute drei alte Aufgaben auf einmal geschlossen haben

Bei uns gilt eine Regel: wird eine Aufgabe zum vierten Mal angefasst, wird sie **gebaut
oder gestrichen**. Ein vierter Termin ist keine Planung mehr.

Heute standen **drei** Aufgaben gleichzeitig an dieser Grenze. Alle drei sind gebaut. Eine
vierte steht ebenfalls dort und ist es **nicht** — das haben wir im Plan ausdrücklich
vermerkt, statt es zu begründen. Sie ist im nächsten Lauf die erste.

### Warum ein Ausbau gefährlicher ist, als er aussieht

Etwas wegzunehmen liefert nichts Neues und kann alles kaputt machen. Deshalb hat dieser
Ausbau drei Sprints gewartet, bis ein Lauf ihn ganz tragen konnte.

Beim Bauen hat sich gezeigt, warum das richtig war: unmittelbar neben dem Auszubauenden
stand Code, der genauso aussah und in Wahrheit zu einer **anderen** Zusage gehörte. Unsere
erste Prüfung hätte das nicht bemerkt — sie fragte nur, ob das Alte verschwunden ist. Eine
solche Prüfung ist auch dann grün, wenn jemand zu viel weggeräumt hat.

> **Wer etwas entfernt, muss neben jedes „das ist weg" ein „und das ist noch da"
> schreiben.**

### Warum wir vier Sprints lang die falsche Ursache verdächtigt haben

Unsere Commits scheitern manchmal an einer Sperrdatei. Die Aufgabe dazu trug seit Tagen
einen Titel, der eine bestimmte Sorte Datei beschuldigte. Die Messung zeigt: diese Dateien
sind harmlos.

Die Sperre entsteht durch etwas, das niemand verdächtigt hätte — durch **erfolgreiches
Nachsehen**. Dein Ordner erlaubt Umbenennen, aber kein Löschen. Wer schreibt, benennt um
und kommt durch. Wer nur nachsieht, will die Sperre löschen und scheitert dabei still.

> **Der harmlose Lesevorgang hinterlässt die Sperre, an der der nächste Vorgang stirbt.**

Was wir vorher gebaut hatten, half nur dem Vorgang, der **schon gescheitert** war — also
dem Falschen. Ab jetzt räumt jeder Vorgang hinter sich her.

### Warum unser eigener Fehler heute wieder nützlich war

Wir haben eine Regel gebaut, die sagt: ein bestimmter Textbaustein darf nur an **einer**
Stelle im Code stehen. Und beim Bauen haben wir eine zweite Stelle angelegt — mit dem
eigenen Satz vor Augen.

Gestoppt hat uns eine Prüfung aus einem früheren Sprint, die nichts weiter tut, als
mitzuzählen, in wie vielen Dateien dieser Textbaustein vorkommt. Solche Prüfungen wirken
kleinlich; sie haben jetzt in **zwei aufeinanderfolgenden Läufen** je einen Fehler
verhindert, den ein Mensch beim Lesen nicht gesehen hat.

> **Eine aufgeschriebene Regel verhindert den Fehler nicht. Die Prüfung, die sie messbar
> macht, tut es.**

---

# Anhang: Sprint 23

## Das Wichtigste (Stand Sprint 23, 2026-08-20)

1. **✅ Die Aufgabe, die vier Läufe lang nur verschoben wurde, ist erledigt.** Unser
   Werkzeug für die Anforderungsübersicht **liest ab jetzt seinen Vorgänger, bevor es ihn
   ersetzt**. Verschwindet dabei auch nur eine Anforderung, schreibt es **gar nichts** und
   sagt, welche fehlt.
   > **Der Schaden vom 17.08. ist entstanden und repariert worden, ohne je in unserer
   > Geschichte aufzutauchen. Eine Warnung nach dem Schreiben hätte ihn gemeldet und
   > trotzdem angerichtet.**
2. **✅ Die negative Zeitmessung von gestern ist aufgeklärt — und wir haben die falsche
   Zeile verdächtigt.** Wir haben jede Registerzeit gegen den Zeitpunkt gehalten, zu dem
   sie gespeichert wurde. Ergebnis: **eine Zeile behauptet 17:10 und wurde um 16:32:36
   gespeichert.**
   > **Niemand kann 38 Minuten vor seiner eigenen Uhr liegen. Falsch ist also nicht der
   > Beginn des späteren Laufs, sondern das Ende des früheren.**

   ⚠ Zwei der drei denkbaren Erklärungen fallen damit weg, ohne dass wir raten mussten.
   ⚠ Die Abhilfe, die im Ticket stand, hätten wir gebaut und sie hätte diesen Fall **nicht
   gefunden** — deshalb ist sie **nicht** gebaut worden.
3. **✅ Zwei Aufgaben standen zum vierten Mal an, und sie sind verschieden ausgegangen.**
   Die eine wartete auf Zeit → **gebaut** (die Mail-Kachel zeigt ihre Inhalte jetzt erst
   nach PIN-Eingabe, bleibt aber sichtbar). Die andere wartete auf etwas, das kein Lauf
   herstellen kann → **blockiert**, mit einer eigenen Vorbereitungsaufgabe.
   > **Eine Aufgabe viermal auf „keine Zeit" zu verschieben, während sie in Wahrheit auf
   > etwas anderes wartet, heißt den Grund viermal falsch aufzuschreiben.**
4. **⚠⚠ Unser größter Fund heute kommt aus einem eigenen Fehler.** Wir haben einen
   Aufgabenstand falsch gebucht — ein Zwischenschritt fehlte. Statt ihn wegzuräumen, haben
   wir gefragt, **warum unsere Prüfung dabei nicht angeschlagen hat**. Antwort: sie hat
   **ein Drittel unserer Projekte seit dem 17.08. nie angesehen**. 66 Vorgänge ungeprüft.
   > **Ein eigener Fehler an einer geprüften Stelle ist ein kostenloser Test der Prüfung.
   > Wer ihn schnell wegräumt, bezahlt mit der Antwort.**

   Repariert. ⚠ Unser eigener Fehler bleibt **stehen und gemeldet** — nichts geglättet.
5. **⚠ Und zum sechsten Mal stand eine geschätzte Zahl da, wo eine gemessene hingehört** —
   diesmal in einer Nebenbemerkung unserer eigenen Reparatur. Dafür gibt es ab heute eine
   eigene Aufgabe; fünf aufgeschriebene Ermahnungen haben es nicht verhindert.
6. **1185 Prüfungen für die Technik** (gezählt, nicht geschätzt), **111 für die
   Oberfläche**, **162 Anforderungen ohne Lücke**. Rote Prüfungen: **eine** — der alte
   Befund aus den Sprints 13/15, **plus unser heutiger Fehler darin**.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠ **Eine neue Frage an dich gibt es NICHT** | Dieser Lauf hat nichts vorgelegt, was du entscheiden müsstest. |
| ⚠ **Wir melden einen eigenen Fehler** | Wir haben einen Aufgabenstand falsch gebucht. Er steht in der Geschichte und wird **nicht** herausgerechnet. Er hat uns einen viel größeren Fund eingebracht — eine Prüfung, die seit dem 17.08. ein Drittel unserer Projekte nicht angesehen hat. Beides ist repariert bzw. benannt. **Klasse B**, du musst nichts entscheiden. |
| ⚠ **Die alten Punkte stehen unverändert** | Die Mail-Zugangsdaten (`team-mail/N-0003`), Ollama in der Umgebung, deine Zählung der Kacheln im Reiter „Dashboard", und `abschluss.cmd` aus Sprint 1. |
| ⚠ **Der Startcheck ist langsamer geworden** | Von rund 60 auf rund 85 Sekunden. Der Grund ist die reparierte Prüfung: sie sieht jetzt alles an. Gemessen und bewusst bezahlt. |
| ✅ **Zu pushen gibt es etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was in Sprint 23 passiert ist — in Ruhe erklärt

### Warum wir vier Sprints gebraucht haben und der fünfte dann kurz war

Die Aufgabe „das Werkzeug soll merken, wenn die Anforderungsübersicht schrumpft" stand
seit dem 17.08. Sie wurde viermal verschoben, und dreimal war der Grund schlicht
Kapazität. Beim vierten Mal war es etwas anderes: im Ticket standen **drei Fragen**, die
vor dem Bauen zu beantworten waren.

Gestern sind sie beantwortet worden — als Messung über alle 95 gespeicherten Fassungen.
Heute war der Bau eine knappe Stunde. **Zwei der drei Antworten fielen umgekehrt aus als
im Ticket vermutet**, und genau deshalb war die Reihenfolge richtig: wer zuerst gebaut
hätte, hätte ein Flag eingebaut, das jeder Aufrufer setzt.

### Warum wir eine falsche Zeit nicht korrigiert haben

Gestern fanden wir eine negative Pause im Sprintregister. Heute wissen wir, **welche der
beiden Zeitangaben falsch ist** — und zwar durch einen dritten Zeugen: den Zeitpunkt, zu
dem die Zeile gespeichert wurde. Eine Zeile kann nicht später entstanden sein als ihre
Speicherung.

Das Ticket schlug vor, das Register künftig mit Zeitzonenangabe zu schreiben. Wir haben
nachgesehen: beide beteiligten Speicherungen tragen dieselbe Zeitzone. Die vorgeschlagene
Abhilfe hätte den einzigen Fall, den wir haben, **nicht gefunden**.

> **Eine Abhilfe, die den belegten Vorfall nicht erkennt, ist keine Abhilfe.**

Gebaut ist stattdessen eine Prüfung auf eine **Unmöglichkeit** statt auf eine Schwelle.
Über unsere gesamte Geschichte findet sie **genau einen** Fall und **keinen** Fehlalarm.

### Warum unser eigener Fehler heute nützlich war

Wir haben eine Aufgabe von „in Arbeit" direkt auf „fertig" gesetzt und den Zwischenschritt
„in Prüfung" ausgelassen. Das ist seit dem ersten Sprint verboten und wird geprüft.

Es ist **nichts** rot geworden. Diese Frage war interessanter als der Fehler selbst.

Die Antwort: unsere Prüfung suchte Aufgabendateien an einer Stelle, an der sie in einem
Drittel unserer Projekte gar nicht liegen — und übersprang diese Projekte zusätzlich aus
einem zweiten, unabhängigen Grund. **Beides sah für sich völlig harmlos aus, und daneben
stand ein Kommentar, der das Gegenteil behauptete.**

> **Ein Kommentar altert nicht mit. Er wird nur irgendwann unwahr, und niemand merkt es.**

Die Reparatur kostet uns 26 Sekunden je Startcheck. Wir zahlen sie, weil eine Prüfung, die
zwei Drittel prüft, nicht zu zwei Dritteln gut ist — sie ist grün.

### Warum eine Aufgabe jetzt „blockiert" heißt statt „nächster Sprint"

Für zehn unserer Rollen wollen wir Beispielfälle sammeln, an denen man messen kann, ob
eine Änderung besser oder schlechter ist. Das geht nur, wenn es **aufgezeichnete Läufe**
dieser Rollen gibt. Gemessen: es gibt **vier** für eine Rolle, **drei** für eine zweite
und **null** für die übrigen zehn — unverändert seit fünf Sprints.

Diese Aufgabe wartet also nicht auf Zeit. Sie wartet auf etwas, das kein Lauf herstellt,
indem er sie anfasst. Deshalb steht sie ab heute auf **blockiert**, und davor steht eine
eigene Aufgabe mit drei möglichen Ausgängen — einer davon ist, die Sache **zu streichen**.

---

# Anhang: Session-Agenda Sprint 22 (2026-08-20)

## Das Wichtigste (Stand Sprint 22, 2026-08-20)

1. **✅ Dein zweiter Brief von heute Morgen ist nicht nur beantwortet, sondern gebaut.**
   Du hast gefragt, warum uns nicht aufgefallen ist, dass die Routine zweieinhalb Tage
   aussetzte. Ab jetzt steht in **jedem** Startbericht eine Zeile mit der Pause seit dem
   letzten Lauf — heute *„56 Min = 0,93x Takt"*. Beim nächsten Ausfall steht dort
   *„60,2x Takt — BEFUND"*.
2. **⚠⚠ Beim Nachmessen dafür haben wir etwas gefunden, wonach niemand gefragt hatte:
   zwei Stellen unseres Programms führten zwei verschiedene Zahlen für denselben
   Sachverhalt.** Wie oft die Routine läuft, stand an einer Stelle als **30 Minuten** und
   an der anderen als **60**. Die Kachel „Letzte Session" hat deshalb seit dem 17.08.
   **eine Stunde zu früh** Alarm geschlagen.
   > **Zwei Anzeigen, die sich widersprechen, sieht man. Zwei Zahlen tief im Programm,
   > die einander nie begegnen, sieht niemand — beide sehen für sich richtig aus.**
3. **⚠⚠ Und der zweite Nebenbefund ist unangenehmer: eine unserer Zeitmessungen ist
   negativ.** Ein Lauf hat einen Start eingetragen, der **21 Minuten vor dem Ende des
   vorherigen** liegt. Das kann nur heißen, dass zwei Läufe verschiedene Uhren abgelesen
   haben. Wir haben den Wert **nicht auf null gerundet** — er ist der einzige Beleg dafür,
   dass es das Problem gibt. Als eigene Aufgabe verbucht, Ursache **noch nicht geraten**.
4. **✅ Die rote Prüfung aus dem letzten Bericht ist grün — ohne dass wir das Datum
   hochgezählt hätten.** Wir haben vorher gezählt, wie oft es diese Bauart bei uns gibt:
   **genau einmal**, über 66 Testdateien. Die *richtige* Bauart gab es dagegen schon an
   zwei Stellen.
   > **Der Fehler war also nicht Unwissen. Die Zahl stand gerade da und war richtig, und
   > jemand hat zugegriffen.**
5. **⚠ Eine Aufgabe, die seit vier Sprints an drei offenen Fragen hing, hat ihre
   Antworten bekommen — und zwei davon fielen umgekehrt aus als vermutet.** Wir haben
   alle **95 Fassungen** unserer Anforderungsübersicht verglichen: in **94 Übergängen**
   ist **nie** eine Anforderung verschwunden.
   > **⚠ Der Vorfall, der die Aufgabe ausgelöst hat, steht gar nicht in unserer
   > Geschichte. Er ist in einem Lauf entstanden und im selben Lauf repariert worden —
   > und alle unsere Prüfungen lesen nur, was ein Lauf hinterlässt.** Zum zweiten Mal in
   > zwei Läufen derselbe blinde Fleck.
6. **1147 Prüfungen für die Technik** (gezählt, nicht geschätzt), **157 Anforderungen
   ohne Lücke**. Rote Prüfungen: **eine statt zwei** — der alte Befund aus den Sprints 13
   und 15, unverändert.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Dein Brief von heute Morgen ist erledigt, nicht nur beantwortet** | `team-mail/N-0004` → `platform/T-0025`. **Den Ausfall selbst können wir weiterhin nicht verhindern** — ob die App läuft, liegt außerhalb unserer Reichweite. Dass wir ihn künftig **melden**, liegt jetzt drin. **Klasse B**, du musst nichts entscheiden. |
| ⚠ **Eine neue Frage an dich gibt es NICHT** | Dieser Lauf hat nichts vorgelegt, was du entscheiden müsstest. |
| ⚠ **Die alten Punkte stehen unverändert** | Die Mail-Zugangsdaten (`team-mail/N-0003`), Ollama in der Umgebung, deine Zählung der Kacheln im Reiter „Dashboard", und `abschluss.cmd` aus Sprint 1. |
| ⚠ **Der alte rote Befund steht unverändert** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15. Neu dazugekommen ist **keiner** — und der zweite rote Test von gestern ist weg. |
| ✅ **Zu pushen gibt es etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was in Sprint 22 passiert ist — in Ruhe erklärt

### Warum eine Zahl an zwei Stellen zwei Werte haben konnte

Wie oft die Routine läuft, ist eine Tatsache. Sie steht in unserem Sprintregister, und
jeder Lauf schreibt sie mit: **60 Minuten**. Daneben stand dieselbe Tatsache noch einmal
als feste Zahl im Programmtext der Kachel — **30 Minuten**, aus einer Zeit, als das
stimmte.

Nichts wurde dadurch rot. Beide Zahlen waren plausibel, keine Prüfung hat sie je
nebeneinandergelegt, und die Kachel hat einfach eine Stunde zu früh „keine Session"
gemeldet.

> **Wo eine Tatsache mitgeschrieben wird, ist die mitgeschriebene die Quelle. Eine feste
> Zahl daneben ist eine Annahme über die Vergangenheit — sie kann nur veralten.**

Beim Reparieren fiel eine **dritte** Kopie derselben Zahl auf: ein Test, der „zwei Takte"
als feste 95 Minuten schrieb. Er war grün, solange der Irrtum galt, und wurde in dem
Moment rot, in dem die anderen beiden zusammenfanden.

### Warum wir eine negative Zeit stehen lassen

Beim Durchmessen aller Pausen kam heraus, dass eine von sieben **negativ** ist: Sprint 17
trägt einen Start um 16:49, Sprint 16 ein Ende um 17:10.

Die Reihenfolge in der Datei ist einwandfrei. Wenn die Reihenfolge stimmt und die
Uhrzeiten sich widersprechen, dann stammen die Uhrzeiten nicht aus derselben Uhr.

Eine Zeile Programmtext hätte den Wert auf null gerundet und die Anzeige schön gemacht.
Wir haben es nicht getan, weil dieser negative Wert der einzige Beleg dafür ist, dass es
das Problem überhaupt gibt. Woran es lag, haben wir **nicht geraten** — es gibt drei
mögliche Erklärungen, sie führen zu verschiedenen Antworten, und der Fall trat einmal in
22 Sprints auf. Das rechtfertigt eine Messung und keine Umstellung.

### Warum wir vor einer Zehn-Minuten-Reparatur erst gezählt haben

Die rote Prüfung von gestern war in zehn Minuten zu reparieren. Ihr Ticket verlangte
vorher eine Zählung: *wie viele Prüfungen dieser Bauart gibt es bei uns?*

Die Antwort war **eine**. Die richtige Gegenbauart gab es an **zwei** Stellen bereits.

Das dreht die Schlussfolgerung um. Es lag nicht daran, dass wir es nicht besser wussten —
wir wussten es besser und haben an dieser einen Stelle die Zahl genommen, die gerade
dastand und richtig war. Eine Regel gegen Unwissen hätte nichts geändert.

### Der blinde Fleck, den wir zum zweiten Mal in zwei Läufen finden

Gestern: ein ausgefallener Lauf hinterlässt keine Spur, also kann keine Prüfung ihn
finden. Heute: der Vorfall, bei dem unsere Anforderungsübersicht von 143 auf 24 Einträge
schrumpfte, steht **nicht in unserer Geschichte** — er ist in einem Lauf entstanden und
im selben Lauf repariert worden.

> **Unsere Prüfungen lesen das, was ein Lauf hinterlässt. Was einen Lauf zerstört oder
> gar nicht erst stattfinden lässt, hinterlässt nichts.**

---

# Anhang: frühere Sessions

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
5. **⚠⚠ Nachtrag um 11:50 — dein zweiter Brief von heute hat recht.** Die Routine hat
   **60,2 Stunden** ausgesetzt, obwohl sie stündlich laufen soll: das **Sechzigfache des
   eigenen Takts**. Wir haben es nicht gemeldet, und der Grund ist unangenehm einfach:
   > **Wir prüfen, ob ein Lauf sauber zu Ende gekommen ist. Wir prüfen nicht, ob der
   > nächste jemals angefangen hat. Ein Lauf, der ausfällt, hinterlässt keine Spur — und
   > alle unsere Prüfungen sehen nur Spuren.**

   ⚠ Wir sind an der Stelle sogar **vorbeigelaufen**: die Kachel „Letzte Session" hat
   heute die Sprintnummer und den Zeitpunkt des letzten Laufs bekommen — und niemand hat
   gefragt, warum dieser Zeitpunkt zweieinhalb Tage zurücklag.
6. **⚠ Und beim Nachprüfen unseres eigenen Abschlusses haben wir zwei Fehler darin
   gefunden**: eine verschobene Aufgabe ohne Begründung (obwohl der Bericht zweimal
   „Grund im Ticket" behauptete) und drei geschätzte statt gezählte Testzahlen. Beides
   korrigiert, beides benannt.
7. **1128 Prüfungen für die Technik** (gezählt, nicht geschätzt), **111 für die
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
| ⚠⚠ **Dein zweiter Brief von heute ist beantwortet — und du hattest recht** | `team-mail/N-0004`. Die Routine hat **60,2 Stunden** ausgesetzt bei 60 Minuten Takt, und wir haben es nicht bemerkt. **Den Ausfall selbst können wir nicht verhindern** — ob die App läuft, liegt außerhalb unserer Reichweite. Dass wir ihn nicht **melden** konnten, liegt vollständig in ihr. Als `platform/T-0025` eingeplant. |
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
