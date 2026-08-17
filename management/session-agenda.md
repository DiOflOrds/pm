# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 14, 2026-08-17)

1. **✅ Danke — dein Push ist durch, und deine Messung war der Auslöser für alles Weitere.**
   Sprint 13 liegt auf GitHub. Und deine zwei Bildschirmfotos haben in zehn Sekunden eine
   Frage beantwortet, an der wir uns die Zähne ausgebissen hätten.
2. **⚠⚠ Deine Bilder haben uns widerlegt — und das ist die wichtigste Zeile hier.** Wir
   hatten angenommen, du musst so viel scrollen, weil es **zu viele Kacheln** sind. Deshalb
   haben wir das Zuklappen gebaut. Die Bilder zeigen: du siehst **drei** Kacheln, und links
   und rechts liegt je rund **ein Fünftel deines Bildschirms leer**. Die Kacheln stehen
   einzeln untereinander in einer schmalen Spalte.
   > **Wir haben das Richtige gebaut und die falsche Ursache behandelt.**
   Das Zuklappen bleibt nützlich. Es war nur nicht die Antwort auf deine Frage.
3. **✅ Also haben wir das Dashboard gebaut — den neuen Reiter „Dashboard".** Alle Teams und
   Projekte als **kompakte Kacheln nebeneinander**, über die **ganze** Breite deines
   Bildschirms. So viele je Reihe, wie hineinpassen — die Zahl steht nirgends im Code, sie
   ergibt sich aus deiner Bildschirmbreite.
4. **⚠ Das durften wir seit fünf Läufen und haben es nicht getan.** Du hast am 17.08. um
   08:11 entschieden, dass das Dashboard breiter sein darf als der Textbereich (`LAY-a`).
   Die Entscheidung lag da, die Architekturnotiz lag da — gebaut wurde es nicht, weil das
   zuständige Ticket **viermal** verschoben wurde. Gestern haben wir gelernt, dass eine
   Entscheidung unsichtbar bleiben kann; heute war es keine Unsichtbarkeit, sondern Verzug.
5. **⚠ Was wir dabei über uns gefunden haben.** Eine Prüfung sollte sicherstellen, dass die
   neue Ansicht die Regel *„fehlende Angabe ist nicht dasselbe wie eine Null"* an **einer**
   Stelle liest. Sie wurde rot — an **drei alten Stellen im Cockpit**, die dieselbe Regel
   jede für sich mitführen. Alle drei sind **richtig**. Genau das ist der Punkt: es ist
   dieselbe Bauart, die dich gestern eine doppelte Nachfrage gekostet hat. Wir haben sie
   **benannt und festgenagelt** (sie darf nicht wachsen), statt sie hastig umzubauen — der
   Umbau berührt einen Vertrag, der einen anderen Eigentümer hat.
6. **⚠⚠ Und wieder waren zwei von uns gleichzeitig unterwegs — diesmal mit Folgen.** Zwei
   Läufe haben zur selben Zeit in dieselben Dateien geschrieben und **beide** haben ihrer
   neuen Anforderung dieselbe Nummer gegeben (`SWR-134`). Gefunden haben wir es **nicht durch
   eine Prüfung**, sondern weil einer von uns eine Nummer in einer Datei fand, die er nie
   angefasst hatte.
   > **Unsere Regel gegen doppelte Nummern galt für Aufgaben-Nummern — nicht für
   > Anforderungs-Nummern.**
   Aufgelöst: die schon abgespeicherte Nummer gewinnt, unsere wurde auf `SWR-135` geändert.
   Es ist nichts verloren gegangen. Aber es ist gut ausgegangen, weil die beiden Läufe
   zufällig verschiedene Dateien angefasst haben — **das war Glück, keine Vorkehrung.**
7. **✅ Nebenbei hat der zweite Lauf etwas Nützliches gebaut** und dabei **unser** Ticket
   widerlegt: wir hatten notiert, es fehle ein Rückfall beim Aufräumen der Git-Sperren. Den
   gab es längst. Der eigentliche Befund war die **Reichweite** — von acht Stellen, die bei
   uns nach Git schreiben, benutzte genau **eine** die Reparatur.
8. **⚠ Ein roter Test bleibt liegen, unverändert seit gestern.** Die zwei Buchungsfehler von
   gestern stehen weiter da. **Dieser Lauf hat keinen neuen erzeugt** — die Regel von gestern
   hat gehalten.
9. **826 Tests für die Technik (2 rot, beide von gestern und benannt), 40 für die Oberfläche
   (von 29), 135 Anforderungen ohne Lücke.** **Bei dir liegt nichts.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Neuer Reiter „Dashboard" — schau ihn dir an** | Zweiter von links. Alle Teams und Projekte als kompakte Kacheln **nebeneinander**, über die ganze Breite. Je Kachel: offene Aufgaben, Briefe, Tickets, letzte Baseline, Digest. Ein Klick auf den Namen führt ins Cockpit dieses Projekts. ⚠ Und ein Detail, das dir vielleicht auffällt: **„keine Daten" sieht anders aus als eine 0** (kursiv und grau). Das ist Absicht — „es gibt hier nichts zu melden" und „dieses Projekt führt das gar nicht" sind zwei verschiedene Aussagen, und sie dürfen nicht gleich aussehen. |
| ⚠ **Bitte noch einmal zählen — jetzt lohnt es** | Du hast gemessen: 3 Kacheln bei aufgeklappten Gruppen. Öffne einmal den neuen Reiter „Dashboard" und sag uns, **wie viele Kacheln du jetzt ohne Scrollen siehst**. Wenn das Dashboard hält, was das Layout verspricht, sollte es ein Vielfaches sein. ⚠ Wir fragen, weil wir es **nicht selbst messen können** — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ⚠⚠ **Deine Messung hat unsere Annahme widerlegt** | Wir haben das Zuklappen gebaut, weil wir die *Menge* für das Problem hielten. Es war das *Layout*. Beides steht in den Tickets, weil eine Annahme, die man stillschweigend korrigiert, beim nächsten Mal wiederkommt. Offen ist jetzt eine kleine Frage an uns selbst: reicht das Dashboard, oder braucht auch die lange Sprint-Tabelle im Cockpit eine Kur? Deine Zahl von oben entscheidet das. |
| ⚠ **Zwei von uns liefen wieder gleichzeitig** | Und diesmal hat es Spuren hinterlassen: eine doppelt vergebene Nummer. Nichts ist verloren, alles ist aufgelöst — aber die Reparatur dafür (`platform/T-0013`) ist ab jetzt **das dringlichste offene Ticket**, das wir haben. Nicht weil es neu ist, sondern weil der Schaden zum zweiten Mal eingetreten ist und beim zweiten Mal nicht mehr folgenlos war. |
| ⚠ **Was weiter liegt** | `promt-team/T-0001` (die Messgrundlage, auf die du wartest) ist bei der **fünften** Verschiebung. `pm/T-0052` („Für dich: Handlungen") ebenfalls. Bei beiden liegt die Trennstelle benannt bereit — sie sind Kandidat 1 und 2 für den nächsten Lauf. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |

---

## Was heute wichtig war — in Ruhe erklärt

### Deine zehn Sekunden haben mehr geleistet als ein ganzer Lauf

Wir hatten dir geschrieben, wir können nicht messen, wie viel das Zuklappen bringt. Du hast
zwei Bilder geschickt. Darauf war beides zu sehen: dass das Zuklappen funktioniert **und**
dass es am eigentlichen Problem vorbeigeht.

Das ist der Unterschied zwischen einer Zahl und einem Bild. Wir hatten nach einer Zahl
gefragt („wie viele Kacheln") und eine Ursache bekommen („weil sie einzeln in einer schmalen
Spalte stehen"). Die Frage war zu eng gestellt — und das ist unser Fehler, nicht deiner.

### Die Entscheidung, die fünf Läufe lang dalag

Am 17.08. um 08:11 hast du entschieden: das Dashboard darf breiter sein als der Textbereich,
alles andere bleibt wie es ist. Wir haben daraufhin sauber aufgeschrieben, **wo** diese
Ausnahme im Code leben soll — und dann fünf Läufe lang etwas anderes gebaut.

Gestern haben wir dir berichtet, dass eine Entscheidung von dir unsichtbar bleiben kann, weil
unsere Prüfungen sie nicht lasen. Heute ist es der andere Fall: sie war sichtbar, sie war
richtig aufgeschrieben, und sie wurde trotzdem nicht wirksam — weil das Ticket, das sie
einlöst, immer hinter etwas Dringenderem stand.

**Beides zusammen ist dieselbe Frage:** was passiert bei uns mit einer Antwort von dir,
nachdem sie angekommen ist?

### Warum „keine Daten" jetzt anders aussieht als „0"

In deinem Cockpit steht bei manchen Projekten „keine Daten" und bei manchen eine 0. Das sind
zwei verschiedene Dinge, und unser eigener Vertrag sagt das seit Sprint 3 wörtlich: *„0
offene Briefe ist ein Ergebnis, kein Loch."*

Im neuen Dashboard steht die Unterscheidung an **einer** Stelle und wird von zwölf Prüfungen
gehalten — darunter mehrere, die absichtlich beweisen, dass die naheliegende Programmierung
falsch wäre. Die naheliegende wäre: *„wenn nichts drinsteht, schreibe keine Daten"*. Die ist
für eine echte 0 falsch, und du hättest bei einem Projekt mit null offenen Briefen „keine
Daten" gelesen — also gedacht, wir wüssten es nicht.

### Was als Nächstes kommt

Sprint 15: die **zwei Zerlegungen**, die zum fünften Mal liegen (`promt-team/T-0001`,
`pm/T-0052`), die Widget-Konfiguration am neuen Dashboard, und die Reparatur am Sprintzähler,
damit zwei Läufe sich nicht mehr überschreiben können.

