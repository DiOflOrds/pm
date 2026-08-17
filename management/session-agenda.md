# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 20, 2026-08-17)

1. **✅ Deine beiden Entscheidungen sind angekommen und verbucht.** Die eine (`p12/T-0010`,
   G4) ging beim ersten Versuch durch; die andere (`promt-team/T-0009`) nicht — **und der
   Fehler lag bei uns.**
2. **⚠⚠ Warum die zweite gescheitert ist.** Jedes Team hat ein Buch, in dem Entscheidungen
   festgehalten werden. Für das promt-team gab es dieses Buch nicht — es wird beim **Gründen**
   eines Teams angelegt, und dieses Team ist anders entstanden. Unser Speicherweg legt die
   *Seite* an, aber nicht das *Regal*, in dem sie stehen soll.
   > **Der Weg setzte etwas voraus, das ein anderer Weg herstellt. Solange jedes Team
   > normal gegründet wurde, war die Annahme unsichtbar richtig.**

   Betroffen waren zwei Teams. Repariert, mit acht Prüfungen abgesichert.
3. **⚠⚠ Und das Unangenehmste daran: keine unserer über tausend Prüfungen hätte das finden
   können.** Jede Prüfung baut sich ihre Ordner selbst — also auch den, der in Wirklichkeit
   fehlte. Genau diese Sorge steht seit Sprint 16 als offene Frage bei uns; heute hat sie zum
   ersten Mal **echten Schaden** angerichtet statt nur dazustehen.
4. **⚠ Wir haben das Buch angelegt statt deine Entscheidung abzulehnen** — und die Kehrseite
   davon schreiben wir dazu:
   > **Eine getroffene Entscheidung, die am Ablageort scheitert, ist verloren, sobald das
   > Fenster zu ist.**

   Ein Weg, der einen Mangel im Vorbeigehen repariert, macht ihn allerdings **unsichtbar**.
   Ob das richtig ist oder ob es lieber gemeldet werden sollte, ist eine offene Frage in
   unserem Ticket — wir haben sie nicht stillschweigend beantwortet.
5. **✅ Damit ist P12 abgenommen.** Dein **G4** steht; die Baseline `p12-v1.0` ist offiziell
   fertig. ⚠ Was mit der Abnahme **ausdrücklich offen bleibt**, steht als eigenes Ticket da
   und nicht im Kleingedruckten: Ticket-Texte und Dokumentenansichten laufen weiter als
   Rohtext.
6. **⚠ Eine deiner Entscheidungen hätten wir fast übersehen.** Die zu P12 kam um **21:57** —
   zwölf Minuten **nach** unserem Abschlussbericht, der noch „keine offenen Entscheidungen"
   meldete. Das war zu diesem Zeitpunkt richtig und wäre einen Tag später falsch gewesen.
   Gefunden hat es eine Prüfung, die den echten Bestand abklopft.
7. **⚠ Die Ollama-Messung kann in unserer Umgebung nicht laufen** — nachgesehen, nicht
   vermutet: kein Ollama installiert, kein Dienst erreichbar. **Das wartet nicht auf dich**,
   sondern auf eine Umgebung, in der Ollama läuft. Der Unterschied ist uns wichtig: eine
   Aufgabe, die fälschlich „wartet auf dich" sagt, schiebt dir die Schuld an ihrem
   Liegenbleiben zu.
8. **1087 Prüfungen für die Technik, 104 für die Oberfläche, 152 Anforderungen ohne Lücke.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ✅ **Deine zwei Entscheidungen sind verbucht — nichts liegt mehr bei dir** | `promt-team/T-0009` → **A** (Ollama, 0 €) und `p12/T-0010` → **A** (G4 erteilt). Beide stehen im Entscheidungsbuch des jeweiligen Teams und im Ticket. |
| ⚠ **Damit die Ollama-Messung laufen kann, braucht sie eine Umgebung mit Ollama** | Unsere hat keins (nachgesehen). Wenn die Routine dort läuft, wo Ollama erreichbar ist, misst sie beim nächsten Lauf von selbst. **Kein Handlungsbedarf, wenn das schon so ist** — wir sagen es nur, damit du weißt, woran es sonst liegt. |
| ⚠ **Die Frage zu den Mail-Zugangsdaten steht weiter offen** | Aus Sprint 17, `team-mail/N-0003`: Sind `MAIL_IMAP_HOST/USER/PASS` in der Umgebung gesetzt, in der die **Routine** läuft? Der Tages-Digest fehlt weiterhin. |
| ⚠ **Deine Zählung steht weiter aus** | Wie viele Kacheln siehst du im Reiter „Dashboard" **ohne Scrollen**? Wir können es nicht selbst messen. |
| ⚠ **Unsere Prüfung bleibt rot, und zwar zu Recht** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15 stehen unverändert. Neu dazugekommen ist **keiner**. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was in Sprint 20 passiert ist — in Ruhe erklärt

### Der Fehler, den du gesehen hast

Du hast auf „A" geklickt, und statt einer Bestätigung kam ein Dateipfad und `[Errno 2]`.

Der Grund ist banal und deshalb lehrreich: unser Programm öffnet das Entscheidungsbuch mit
einem Befehl, der eine **Datei** anlegt, wenn sie fehlt — aber keinen **Ordner**. Der Ordner
entsteht normalerweise beim Gründen eines Teams. Das promt-team ist nicht auf diesem Weg
entstanden.

Was uns daran am meisten beschäftigt, ist nicht der fehlende Ordner, sondern dass **keine
unserer Prüfungen ihn hätte finden können**. Jede Prüfung legt sich ihre Ordner selbst an,
bevor sie misst — und prüft damit eine Welt, die sie selbst aufgeräumt hat. Diese Sorge steht
seit drei Tagen als offene Frage bei uns; heute hat sie zum ersten Mal etwas kaputtgemacht.

Die neue Prüfung fängt deshalb mit dem Gegenteil an: sie **stellt den kaputten Zustand her**
und weist nach, dass er wirklich zum Absturz führt. Erst danach prüft sie die Reparatur.

### Und eine unserer eigenen Prüfungen war heute falsch rot

Sie sollte nachsehen, ob wir das Buch **vor** dem Schreiben anlegen. Dafür hat sie in der
Datei nach einem Namen gesucht — und dabei die **Stelle gefunden, an der dieser Name
definiert wird**, statt die, an der er benutzt wird.

> **Eine Textsuche kann eine Definition nicht von ihrem Aufruf unterscheiden — und die
> Definition steht nun einmal weiter oben.**

Das ist bei uns in drei Tagen jetzt **sechsmal** passiert, in verschiedenen Verkleidungen.
Wir haben es jedes Mal einzeln repariert und noch keine Regel, die es verhindert. Das steht
so in unseren Unterlagen, weil es die ehrliche Lage ist.

---

# Anhang: Sprint 19 — was dort wichtig war

## Was heute wichtig war — in Ruhe erklärt

### Wir haben etwas gebaut, das nie aufgerufen wurde — und die Prüfung war grün

Der Renderer sollte lernen, Code-Blöcke unverändert darzustellen. Der Zweig dafür war
geschrieben, und unsere Prüfung bestätigte: „ja, der Zweig steht da."

Nur: der Renderer arbeitet Zeile für Zeile. Steht vor einem Code-Block ein normaler Absatz,
sammelt der Absatz alle Folgezeilen ein, bis eine Zeile kommt, die er als **etwas anderes**
erkennt. Und „Code-Block" stand in dieser Liste nicht. Der Absatz hat den Block einfach
mitgenommen.

> **Beide Stellen waren einzeln richtig. Falsch war nur, dass die eine nichts von der
> anderen wusste.**

Gefunden hat es eine Prüfung, die nicht in den Quelltext schaut, sondern nachsieht, was
tatsächlich auf dem Bildschirm entsteht. Und die erste Fassung dieser Prüfung war auch grün —
weil sie den Code-Block ganz an den Anfang gesetzt hatte, wo kein Absatz davorstehen kann.

### Warum dein Dashboard sich etwas merkt und das Cockpit nicht

Als wir im Cockpit die Gruppen zuklappbar gemacht haben, hatten wir uns bewusst dagegen
entschieden, das zu speichern. Die Begründung von damals steht bis heute im Code: *ein
Zustand, der einen Neustart überlebt, müsste beim Wiedersehen erklärt werden — sonst fehlt
etwas und niemand weiß, warum.*

Beim Dashboard speichern wir jetzt. Das sieht nach Widerspruch aus, und wir haben uns die
Antwort nicht leicht gemacht:

> **Zuklappen ist ein Griff beim Lesen. Eine Auswahl ist eine Aussage. Das eine wieder
> aufzumachen kostet einen Klick — das andere jedes Mal neu zu treffen macht es wertlos.**

Der alte Einwand ist damit nicht überholt, sondern zur **Auflage** geworden: was du
ausgeblendet hast, steht oben in der Ansicht — mit Anzahl, mit Namen, mit einem Knopf
zurück. Und wir haben eine Prüfung eingebaut, die aufpasst, dass das Cockpit-Zuklappen
weiterhin **nicht** gespeichert wird. Sonst wäre unsere Begründung eines Tages
gegenstandslos, ohne dass jemand sie zurückgenommen hätte.

### Eine Entscheidung, die sich durch Nachsehen fast von selbst erledigt hat

Eine Schnittstelle im Programm hatte keinen Nutzer mehr. Drei Möglichkeiten standen zur
Wahl: behalten, wegbauen, umwidmen. „Behalten" und „umwidmen" stützten sich beide auf
dieselbe Annahme — *die neue Dashboard-Konfiguration wird sie schon brauchen.*

Diese Konfiguration ist heute gebaut worden. Sie braucht die Schnittstelle **nicht**.

> **Damit waren zwei der drei Möglichkeiten erledigt, ohne dass jemand über ihre Vor- und
> Nachteile reden musste. Beide waren Aussagen über etwas, das es noch nicht gab.**

### Und eine Zahl in unserem eigenen Bericht war zum zweiten Mal geschätzt

Gestern haben wir aufgeschrieben, dass wir unsere Testzahl **fortgeschrieben statt gezählt**
hatten. Heute stand im ersten Entwurf dieses Berichts wieder eine geschätzte Zahl — 1077
statt der gemessenen 1079.

> **Der Lauf, der die Warnung von gestern beim Schreiben vor Augen hatte, hat denselben
> Fehler an derselben Stelle gemacht. Eine Lesson aufzuschreiben schließt keine Lücke.**

Korrigiert, bevor es jemand liest. Die richtige Antwort ist kein dritter Merksatz, sondern
eine Prüfung — sie steht als offene Frage in `platform/T-0020`.

### Was als Nächstes kommt

Sprint 20: der **Werkzeugbefund** (er kostet jeden Lauf Zeit), das **Mail-Widget hinter dem
PIN**, der **Rückbau** der ungenutzten Schnittstelle und die dritte Berührung von
`platform/T-0020`. Dazu deine zwei Antworten, sobald sie vorliegen.
