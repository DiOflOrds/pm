# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 15, 2026-08-17)

1. **✅ Die Sache, vor der wir dich zweimal gewarnt haben, kann jetzt nicht mehr
   passieren.** Zwei von uns können nicht länger gleichzeitig losrennen: unser Zählwerk
   weiß ab jetzt nicht nur, wann ein Lauf **anfängt**, sondern auch, wann er **fertig** ist.
   Wer starten will, während ein anderer noch arbeitet, wird abgewiesen — und erfährt, wer
   gerade läuft.
2. **⚠ Wir wollten das an einer Uhr festmachen und haben vorher nachgemessen — gut so.**
   Der Plan war: „wenn der letzte Lauf weniger als eine Stunde her ist, ist er wohl noch
   da." Gemessen über zwölf Abstände: der kürzeste war **15 Minuten**, und **7 von 12** lagen
   unter einer Stunde. Diese Regel hätte die **Mehrheit** unserer normalen Läufe abgewiesen —
   wir hätten uns selbst ausgesperrt.
   > **Eine Uhr kann einen arbeitenden Lauf nicht von einem abgestürzten unterscheiden.**
   Jetzt schauen wir stattdessen nach, ob überhaupt noch etwas geschrieben wird.
3. **✅ Zwei Aufgaben, die fünfmal liegengeblieben sind, sind angefasst.** Bei beiden war
   die Trennstelle seit Sprint 12 im Ticket notiert, und beide Male haben wir **genau dort**
   geschnitten und nicht irgendwo.
4. **✅ Und eine davon war deine Frage aus dem Brief vom 16.08.:** *„Warum sind die Tasks
   nicht in der Inbox, wenn sie an Menschen gerichtet sind?"* — deine Beobachtung war
   richtig, und die Ursache lag eine Etage tiefer als die Frage.
   > **Die Inbox hat sie nicht abgelehnt. Sie hat sie nicht gekannt.**
   Es fehlte kein Filter, sondern der Kanal. Jetzt stehen bei dir **zwei** Abschnitte:
   „Für dich: Entscheidungen" und „Für dich: Handlungen".
5. **⚠⚠ Und jetzt der Teil, der uns nicht gefällt: wir haben in diesem Lauf denselben
   Fehler zweimal gemacht, und einmal ist er stehengeblieben.** Wenn wir einen Aufgabenstand
   ändern, sind das bei uns **zwei** Schritte: erst in die Datei schreiben, dann abspeichern.
   Klemmt der zweite, steht der Stand in der Datei und **nicht** in der Geschichte. Beim
   ersten Mal haben wir es gesehen und geradegezogen. Beim zweiten Mal nicht.
   > **Es ist beim ersten Mal gut ausgegangen, weil jemand hingesehen hat — nicht, weil eine
   > Vorkehrung gegriffen hätte.** Und Aufmerksamkeit ist keine Vorkehrung.

   Wir haben es **nicht** weggeräumt. Es steht als Fehler in unserer Prüfung, und die
   Reparatur ist die dringlichste Aufgabe für den nächsten Lauf.
6. **⚠ Eine unserer eigenen Prüfungen hat uns beim Bauen erwischt — zum Guten.** Wir haben
   eine Regel („eine Null ist ein Ergebnis, kein fehlender Wert") auf ein Feld angewandt, für
   das sie nicht gedacht war. Ergebnis: die Lücke, die wir sichtbar machen wollten, wäre
   unsichtbar geblieben. Gefunden hat es ein Test, den wir selbst geschrieben hatten.
7. **⚠ Beim Planen ist uns eine Schwäche unseres Werkzeugs aufgefallen.** Wir können eine
   Aufgabe als „wartet auf eine andere Aufgabe" markieren — aber **nur innerhalb desselben
   Teams**. Wir führen 17 Teams und Projekte. Die häufigste Abhängigkeit bei uns ist die
   zwischen **zwei** Teams, und genau die können wir nicht eintragen. Sie steht deshalb im
   Text — wo keine Prüfung sie sieht. Benannt, nicht kaschiert.
8. **⚠ Und eine Zahl aus unserem letzten Bericht können wir nicht wiederfinden.** Wir hatten
   dir „2 rote Tests" gemeldet; heute gemessen ist es **ein** roter Test, der **drei**
   Verstöße auflistet. Ob damals wirklich zwei rot waren oder ob wir Verstöße als Tests
   gezählt haben, lässt sich nicht mehr entscheiden — also sagen wir beides, statt uns die
   bequemere Version auszusuchen.
9. **879 Tests für die Technik (1 rot, unser eigener Fehler von oben), 45 für die Oberfläche
   (von 40), 138 Anforderungen ohne Lücke.** **Bei dir liegt nichts Neues.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Schau in die Inbox — sie hat jetzt zwei Abschnitte** | Oben „Für dich: Entscheidungen" (wie bisher, mit Knöpfen), darunter **„Für dich: Handlungen"**: Aufgaben, bei denen du etwas **tun** sollst statt zu entscheiden. Ohne Knöpfe, denn es gibt nichts zu klicken. ⚠ Beide Abschnitte stehen auch da, wenn sie leer sind — damit du siehst, dass wir nachgesehen haben, statt zu rätseln, ob der Abschnitt fehlt. |
| ⚠ **Deine Zählung von gestern steht noch aus** | Wir hatten dich gebeten, im neuen Reiter „Dashboard" nachzusehen, **wie viele Kacheln du ohne Scrollen siehst**. Die Frage ist offen und wichtig: davon hängt ab, ob auch die lange Sprint-Tabelle im Cockpit eine Kur braucht. ⚠ Wir können es nicht selbst messen — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ⚠ **Wir haben in diesem Lauf einen Buchungsfehler gemacht** | Einen Aufgabenstand haben wir übersprungen: in der Geschichte steht „begonnen → fertig", der Zwischenschritt fehlt. Inhaltlich ist nichts verloren, die Arbeit ist da und geprüft. Aber unsere Prüfung ist deswegen rot, und das bleibt so, bis die Reparatur da ist. Wir haben nichts umgeschrieben. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es wieder etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was heute wichtig war — in Ruhe erklärt

### Warum wir die Uhr weggelassen haben

Die Aufgabe lautete: verhindere, dass zwei Läufe gleichzeitig arbeiten. Der naheliegende Weg
wäre eine Uhr — „wenn der letzte Start weniger als eine Stunde her ist, läuft er noch".

Bevor wir das gebaut haben, haben wir unsere eigenen Startzeiten nachgezählt. Zwölf
Abstände: Mittelwert 57 Minuten, kürzester **15 Minuten**, längster 124. **Sieben von zwölf**
lagen unter einer Stunde. Die Uhr hätte also in der Mehrheit der Fälle einen ganz normalen
Folgelauf für einen Doppelgänger gehalten.

Der eigentliche Grund ist aber ein anderer, und er ist einfach: **eine Uhr sieht bei einem
Lauf, der seit 15 Minuten arbeitet, genau denselben Wert wie bei einem, der vor 15 Minuten
abgestürzt ist.** Was die beiden unterscheidet, ist nicht die Zeit, sondern ob noch etwas
geschrieben wird. Genau das schauen wir jetzt nach — und wenn wirklich nichts mehr kommt,
übernimmt der nächste Lauf und vermerkt den anderen als abgebrochen.

### Deine Frage war richtig, und wir hatten die Antwort falsch erwartet

Du hast gefragt, warum Aufgaben, die an Menschen gerichtet sind, nicht in der Inbox stehen.
Man würde vermuten: da fehlt ein Häkchen, ein Filter ist zu streng. Nachgesehen: die Inbox
sucht nach **Entscheidungsvorlagen**. Eine Aufgabe, bei der du etwas tun sollst, ist keine
Entscheidungsvorlage — sie fällt durch jede Suche, ohne dass irgendwo etwas abgelehnt wird.

Das ist ein Unterschied mit Folgen: bei einem zu strengen Filter macht man ihn weiter. Hier
mussten wir einen **zweiten Ort** schaffen. Und zwar bewusst einen zweiten und nicht dieselbe
Liste, denn an den Entscheidungen hängen Knöpfe. Eine Liste, in der manche Zeilen Knöpfe
haben und manche nicht, ist eine Liste mit zwei Bedeutungen — und die verwirrt beim dritten
Hinsehen mehr, als sie beim ersten spart.

### Der Fehler, den wir zweimal gemacht haben

Wenn wir den Stand einer Aufgabe ändern, tun wir zwei Dinge: die Datei schreiben und die
Änderung abspeichern. Auf diesem Rechner klemmt das Abspeichern gelegentlich — eine
technische Eigenheit, die wir kennen und behandeln.

Was wir **nicht** bedacht hatten: klemmt es genau zwischen den beiden Schritten, dann steht
der neue Stand in der Datei, aber nicht in der Geschichte. Der nächste Schritt überschreibt
ihn, und die Zwischenstufe ist weg.

Das ist heute zweimal passiert. Beim ersten Mal stand die Fehlermeldung direkt auf dem
Schirm, wir haben es bemerkt und geradegezogen. Beim zweiten Mal lief es in derselben
Befehlszeile durch, in der schon der nächste Schritt folgte — bemerkt hat es erst unsere
Abschlussprüfung.

**Was wir daraus gemacht haben, ist keine Ermahnung an uns selbst.** „Besser aufpassen" ist
keine Reparatur. Die Reparatur ist, aus zwei Schritten **einen** zu machen: wer den Stand
schreibt, speichert ihn im selben Zug, und klemmt es, gilt die Änderung als nicht passiert.
Das ist die erste Aufgabe des nächsten Laufs.

### Eine Regel am falschen Ort — und ein Test, der es gemerkt hat

Wir haben eine Regel, auf die wir stolz sind: *eine Null ist ein Ergebnis, kein fehlender
Wert.* Null offene Briefe heißt „nichts zu melden", nicht „wir wissen es nicht.

Beim Bauen der Messgrundlage haben wir diese Regel auf **alle** Pflichtfelder angewandt —
auch auf eines, das den **Namen der Aufgabenart** enthält. Damit war ein leeres Namensfeld
plötzlich eine „echte Null", also ein gültiges Ergebnis. Und genau dieses Feld fehlt bei
**sechs von sieben** unserer Läufe — das ist der Befund, den wir sichtbar machen wollten.
Unsere eigene Prüfung hätte ihn durchgewinkt.

> **Es gibt keine Aufgabenart, die „nichts" heißt.** Für einen Messwert ist Null eine
> Antwort, für einen Namen ist Leere ein Loch.

Gefunden hat das kein Nachdenken, sondern ein Test, den wir vorher geschrieben hatten und
der rot wurde. Das ist der Grund, warum wir Tests vor dem Bauen schreiben.

### Was als Nächstes kommt

Sprint 16: die **Reparatur des Buchungsfehlers** (ein Schritt statt zwei), die **Vertragsfrage**
zum Cockpit, die wir nicht allein entscheiden dürfen, und die **Messgrundlage**, auf die du
seit deinem Brief zu den KI-Rollen wartest.
