# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Sprint 32, 2026-08-21)

1. **✅ Zwei Aufgaben erledigt, keine verschoben** — beide waren letzten Sprint für
   „diesmal" angekündigt und sind diesmal gebaut.
2. **⚠⚠ Der eigentliche Ertrag dieses Laufs ist, dass unsere eigene Prüfung uns erwischt
   hat — vier Mal, und jedes Mal schwer.** Wir haben eine Reparatur gebaut, sie selbst
   für fertig gehalten, und **ein unabhängiges Gegenlesen** hat vier ernste Fehler darin
   gefunden. Der schlimmste: unsere Ausnahme galt immer dann, wenn *irgendein* Sprint
   läuft — und während gearbeitet wird, läuft immer einer.
   > **Eine Bedingung, die während der ganzen Arbeitszeit wahr ist, ist keine Bedingung.
   > Sie ist ein offenes Tor mit einer Aufschrift.**
   Dazu ein Schlupfloch: wer eine unbequeme Aufgabe **verwirft**, hätte damit die Meldung
   losgewerden können. Alles behoben und am echten Bestand gegengeprüft.
3. **⚠⚠ Sie haben während des Laufs beide offenen Fragen beantwortet — und das ist die
   dritte Messung derselben Sache.** `T-0077` stand **vier Sprints** in einer
   Empfehlungsliste und wurde nicht beantwortet. Als es zum ersten Mal als **Frage mit
   Optionen, Frist und Voreinstellung** dastand, war es in **sieben Minuten** entschieden
   — bei sieben Tagen Frist.
   > **Fragen ist billiger als Ausweichen. Und den Preis des Ausweichens zahlt nicht der,
   > der fragt.**
4. **⚠⚠ Sieben Briefe kamen WÄHREND des Laufs — und unser Haken „Briefkasten erfüllt"
   stand da schon.** Beim Start: 0 offen, richtig gemessen. Beim Abschluss: 7. Alle
   beantwortet und einsortiert, aber:
   > **„Briefkasten zuerst" ist eine Reihenfolge und keine Zusage. Was am Anfang gemessen
   > und am Ende berichtet wird, ist eine Momentaufnahme in der Aufmachung einer Garantie.**
   ⚠ **Und dieselbe Nachlässigkeit ein zweites Mal im selben Lauf:** unsere Sichtung der
   offenen Aufgaben hat die verschachtelten Projekte nicht mitgelesen — **Ihre p13-Freigabe
   ist uns dadurch in der Planung entgangen.** Gefunden hat es die Schlussrechnung, nicht
   die Planung.
5. **⚠ Ihre Antwort A hat eine Lage erzeugt, für die wir keinen Zustand haben.** Drei
   Aufgaben warteten auf `T-0077`. Jetzt ist entschieden — aber die Antwort war „alles
   bleibt", also besteht der Grund fort. „Gesperrt" passt nicht mehr, ein Termin wäre
   eine Zusage ohne Arbeit, und Schließen wäre Ihre Option C gewesen, die Sie nicht
   gewählt haben. **Zum dritten Mal in drei Sprints liegt der Fehler zwischen zwei
   richtigen Regeln.** Aufgeschrieben statt schnell übermalt.
6. **Zahlen:** Anforderungen **202 / 0 Lücken**, Organigramm grün (20 Dateien),
   Briefkasten **0 offen** (am **Ende** gemessen, nicht am Anfang), Workflows **6 / 0
   unabgedeckt**, Work Products **56 / 0 Lücken**, offene Aufgaben **21** — und diese Zahl
   sagen unsere Werkzeuge ab jetzt wieder **einstimmig** (letzten Sprint waren es 9
   gegen 12).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`abschluss.cmd` ausführen** | **Der wichtigste Punkt, und er ist gewachsen: fünf Tage plus fünf komplette Sprints.** Du hast selbst gefragt, ob der Auto-Commit klemmt — er klemmt nicht, er **darf** nicht: wir pushen nie selbst. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ⚠⚠ **Zwei neue Fragen an dich, Frist 28.08.** | **`pm/T-0078`** — dein Projekt `team-termine`: Gründung ist Klasse A, und du willst **in einen fremden Kalender schreiben** (`dimitri.john83@…`). Default **A** = Projekt startet, Kalender **nur lesend**. **`pm/T-0081`** — dein Digest-Brief nennt **zwei** Empfängeradressen, Guardrail 1 erlaubt **eine**. Default **A** = Guardrail bleibt. ⚠ In beiden Fällen genügt Schweigen, und **das Widget bzw. der Digest wird trotzdem gebaut** — nur der letzte Schritt wartet. |
| ✅ **Deine sieben Briefe sind alle beantwortet** | In derselben Datei, mit Einordnung. Umgesetzt wird ab Sprint 33 — Grund für die Verschiebung ist die **Ankunftszeit** (06:32–07:03, nach unserem Durchgang), nicht Kapazität. |
| ⚠ **Dein Ollama-Takt: entschieden ist A** | Er läuft weiter und meldet ehrlich Leerlauf. **Kein Ticket wurde an Ollama delegiert, Token-Ersparnis 0** — gemessen, nicht geschätzt: alle Ollama-Läufe stehen auf `fehler` (`model 'llama3.1:8b' not found`). ⚠ Falls du das ändern willst, wäre `ollama pull llama3.1:8b` oder ein Register-Eintrag der nächste Schritt — dein alter Punkt „`ollama list`" ist damit immer noch offen. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11612 Dateien** (Stand 09:07). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`) — dein **ältester** offener Punkt, seit Sprint 21, und er blockiert jetzt zusätzlich deinen Digest-Wunsch. Dazu deine Zählung der Kacheln im Reiter „Dashboard". |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens: unsere Reparatur war kaputt, und unsere eigenen Prüfungen haben es nicht
gemerkt.** Wir haben sechs Zusicherungen geschrieben, alle grün. Ein unabhängiges
Gegenlesen hat dann die komplette Verdrahtung **entfernt** — und alle sechs blieben grün,
weil sie die Funktion direkt aufriefen statt den Betrieb. **Eine Prüfung, die nur die
Funktion kennt, sagt nichts darüber, ob sie jemals aufgerufen wird.**

**Zweitens: zwei unserer Prüfer hatten genau den Fehler, den sie prüfen.** Der eine
prüfte, ob eine Regel *dasteht*, statt ob sie *benutzt* wird — und blieb grün, während
drei Zeilen darüber die alte Fassung weiterlief. Der andere schlug gegen seine **eigene
Erklärung** an, weil dort das schlechte Beispiel zitiert steht.

**Drittens: wir haben zweimal im selben Lauf zu eng gesucht.** Beim Briefkasten und bei
den offenen Aufgaben hat unser Handlauf die verschachtelten Projekte nicht mitgelesen,
während unser Werkzeug es tut. Beim Briefkasten ist nichts passiert; bei den Aufgaben ist
**deine p13-Freigabe** durchgerutscht. **Zwei Wege, dieselbe Frage, verschieden weit — und
der engere war der, den wir von Hand gegangen sind.**

---

<details><summary>Archiv: Sprint 31</summary>

## Das Wichtigste (Sprint 31, 2026-08-21)

1. **✅ Drei Aufgaben erledigt, keine verschoben.** Darunter beide, die letzter Sprint
   ausdrücklich für „diesmal" angekündigt hatte, und eine, die zum **vierten** Mal
   drankam und deshalb entschieden werden **musste**.
2. **⚠⚠ Dreimal an einem Tag lag der Fehler nicht in einer Prüfung, sondern zwischen
   zweien — und das ist der eigentliche Ertrag dieses Laufs.**
   Für eine **gesperrte** Aufgabe gab es bisher **keinen** zulässigen Termin: ein alter
   Termin war ein Fehler, kein Termin war ein Fehler, und ruhig blieb es nur mit einer
   Zusage, die das Team gar nicht halten kann.
   > **Eine Lage, in der die bequeme Handlung die einzige ist, die grün macht, ist genau
   > die Bauart, die uns 83 abgebrochene Läufe gekostet hat.**
   Die Ausnahme gab es längst — sie hing nur an der falschen Sorte Merkmal. **Repariert
   und am echten Bestand nachgemessen**, nicht im Test: drei Meldungen sind weg.
3. **⚠⚠ Unsere eigene Prüfung von letztem Sprint hat ihre Grundmenge nicht verdient.**
   Sie las eine **Schreibweise** und nannte sie eine Konvention. Nachgezählt: **111 von
   112** Lehren tragen eine Regel — als Auswahl ist das keine Auswahl. Und die
   Trefferquote ist innerhalb (24 %) und außerhalb (15 %) fast gleich.
   > **Die Prüfung hat nie Lehren getrennt, die eine Absicherung BRAUCHEN. Sie hat
   > Lehren getrennt, die jemand mit Doppelpunkt geschrieben hat.**
   Umgebaut, ohne einen einzigen Dauerbefund zu erzeugen: der Bestand ist **benannt** und
   bleibt still, rot wird nur Neues — ab jetzt in **jeder** Schreibweise.
4. **⚠⚠ Eine Frage, die dreimal weitergereicht wurde, war längst beantwortet.** Seit drei
   Sprints suchten wir einen „zweiten Schreibweg" ins Entscheidungslog. Gemessen: **es
   gibt ihn nicht als Programm** — es ist die **Hand**, und sie schreibt mit 103 von 158
   Zeilen die **Mehrheit**. Der Schaden, den ein Bau verhindert hätte, wird seit zwei
   Sprints ohnehin gefangen.
   > **Wir haben bei jeder Verschiebung den GRUND geprüft und nie die GÜLTIGKEIT der
   > Frage. Das ist ab jetzt Teil jeder Terminierung.**
5. **⚠⚠ Der unangenehmste Punkt betrifft wieder uns selbst: diese Session hat Ihren
   15-Minuten-Takt blockiert.** Um **06:15** lief er zweimal sauber durch. Ab **06:30**
   bis **07:01** brach er **sechsmal** ab — weil wir unsere Aufgaben geschlossen haben,
   bevor wir den Plan neu geschrieben hatten.
   > **Der Plan wird laut Beschluss am Sprint-ENDE geschrieben. Also ist der Bestand
   > während JEDES Sprints widersprüchlich — und genau dann kann Ihr Takt nie laufen.
   > Das ist kein Ausrutscher, das ist die Dauer eines Sprints.**
   ⚠ **Das stellt richtig, was hier letzten Sprint stand:** `pm/T-0077` ist **nicht** die
   einzige Sperre. Aufgeschrieben und terminiert, nicht schnell repariert.
6. **1429 Prüfungen für die Technik** über 95 Dateien (zweimal unabhängig gezählt),
   **200 Anforderungen ohne Lücke**. Briefkasten: **0 offen**, keiner eingegangen.
   Offene Aufgaben: **12** (drei geschlossen, zwei neu angelegt) — ⚠ oder **9**, je
   nachdem, welches unserer beiden Werkzeuge man fragt; siehe unten.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt). **B** = dein 15-Minuten-Takt bekommt echte Aufgaben. **C** = der Ollama-Zweig wird beendet. ⚠ **Korrektur gegenüber letztem Sprint:** die Frage ist **nicht** die einzige Sperre — siehe Punkt 5. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus vier komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Dein Schnelltakt läuft grundsätzlich** | Um 06:15 zweimal `STARTKLAR`. Dass er danach wieder abbrach, war **unsere** Arbeit und nicht dein Rechner — repariert wird das im nächsten Sprint (`platform/T-0052`). |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11480 Dateien** (Stand 07:15). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Eine Zusicherung aus dem **letzten** Sprint hat diese Session aufgehalten —
und genau dafür war sie gebaut. Sie hielt einen **bekannten Mangel** fest und trug in
ihrem eigenen Text den Auftrag, beim Beheben umgedreht zu werden. Nach der Reparatur
wurde sie rot. **Hätten wir den Mangel nur in Prosa vermerkt, hätte die Datei nach dem
Fix schweigend weiter den alten Zustand beschrieben.** Sie hat dabei noch einen zweiten,
echten Fehler gefunden, den keine unserer neuen Prüfungen gesehen hätte.

**Zweitens:** Eine unserer eigenen Zahlen war zuerst falsch formuliert. Wir haben sie
**korrigiert und benannt**, statt sie stehen zu lassen — aufgefallen ist es, weil unsere
eigene Prüfung die Behauptung nicht hergab.

**Drittens:** Beim Zusammenstellen der Abschlusszahlen haben wir gemerkt, dass **zwei
unserer Werkzeuge „offene Aufgaben" verschieden zählen** (9 gegen 12; die Differenz sind
die drei gesperrten). Das war vor **vier** Sprints schon einmal entschieden worden — die
Festlegung stand in einem Kommentar und in keiner Prüfung, und das neuere Werkzeug hat sie
nicht übernommen. **Wir schreiben deshalb beide Zahlen mit ihrer Definition hin, statt
eine still zu wählen.**

---

</details>

<details><summary>Archiv: Sprint 30</summary>

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

</details>

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
