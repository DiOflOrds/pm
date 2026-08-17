# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 19, 2026-08-17)

1. **✅ Die Zusammenführung im Cockpit ist fertig — und sie ist an einer Zahl nachweisbar.**
   Es gab zwei Wege, Text auf dem Bildschirm darzustellen: einer konnte Formatierung und
   keine Ticketnummern, der andere Ticketnummern und keine Formatierung. Jetzt gibt es
   **einen**. Der alte Weg ist **entfernt**, nicht nur unbenutzt — von **4** Verwendungen auf
   **0**.
2. **⚠⚠ Und dabei haben wir etwas gebaut, das niemand erreichen konnte.** Ein neuer Zweig für
   Code-Blöcke war fertig, die Prüfung war **grün** — und der Zweig wurde nie aufgerufen. Der
   Absatz davor hat ihn stillschweigend verschluckt.
   > **Die Prüfung las den Quelltext und sah den Zweig dastehen. Ob ihn jemand erreicht,
   > konnte sie nicht sehen.**

   Gefunden hat es eine Prüfung, die stattdessen das **Ergebnis** anschaut. ⚠ Und deren
   erster Versuch war ebenfalls grün, weil sein Beispiel die Stelle nicht traf.
3. **✅ Du kannst dein Dashboard jetzt selbst einrichten.** Welche Kacheln du siehst und in
   welcher Reihenfolge — und es bleibt so, auch nach einem Neustart.
   ⚠ **Was ausgeblendet ist, steht immer oben**, mit Namen und einem Knopf zurück. Das ist
   kein Beiwerk: wir hatten dieselbe Speicherei beim Zuklappen der Cockpit-Gruppen mit gutem
   Grund **abgelehnt** — *sonst fehlt etwas und niemand weiß, warum.* Der Einwand gilt
   weiter; er verbietet das Speichern nicht, er verlangt die Erklärung.
4. **⚠ Ein neues Team-Widget erscheint bei dir von selbst.** Gespeichert wird, was du
   **weggeklickt** hast — nicht, was du ausgewählt hast.
   > **Eine gespeicherte Auswahl veraltet: sie sagt „zeig diese vier", und alles, was danach
   > dazukommt, ist unsichtbar. Man vermisst nichts, von dem man nie erfahren hat.**
5. **✅ Eine Entscheidung getroffen, die wir seit einem Sprint aufgeschoben hatten** — und die
   Antwort kam aus einer **Messung**, nicht aus einer Meinung. Es ging um eine Schnittstelle,
   die niemand mehr liest. Zwei der drei Möglichkeiten haben sich erledigt, sobald feststand,
   dass die einzige Anwendung, die sie hätte brauchen können, sie nicht braucht.
6. **⚠⚠ Unser Werkzeug bremst sich selbst aus, und jetzt wissen wir warum.** Jeder
   Speichervorgang lässt in dem Ordner, den du uns gegeben hast, Reste zurück, die Git dort
   nicht löschen darf — und der **nächste** Speichervorgang scheitert daran. Dreimal
   hintereinander gemessen.
   > **Unsere Startprüfung räumt am Anfang auf. Was sie stört, entsteht danach — durch genau
   > die Arbeit, die sie ermöglichen soll.**
7. **1079 Prüfungen für die Technik (1 rot, der alte Befund von vorgestern — unverändert),
   104 für die Oberfläche (von 78), 151 Anforderungen ohne Lücke.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **Eine NEUE Entscheidung: das Abnahmetor für den Renderer** | Die Arbeit ist fertig und geprüft, aber die Abnahme (**G4**) dürfen wir nicht selbst erteilen. Dazu gehört eine zweite Frage: Ticket-Texte, Entscheidungs-Texte und die zwei Dokumentenansichten zeigen weiterhin **Rohtext**. ⚠ **Etwas hat sich dort trotzdem geändert, und das gehört gesagt:** ihre Ticketlinks kamen aus dem alten Weg, der weg musste — **fett** und `Code` werden dort ab jetzt mitdargestellt. Die *Struktur* (Überschriften, Tabellen) bleibt Rohtext, und ob sie umgestellt wird, entscheidest du. Steht in `projects/p12/T-0010`, **Frist 20.08.**, Default **A** (so lassen). |
| ⚠⚠ **Die Anbieter-Frage von gestern steht weiter offen** | `promt-team/T-0009`: Um zu messen, wie gut eine KI-Rolle **heute wirklich** arbeitet, braucht sie einen Anbieter. **A:** lokales Ollama, kostenlos. **B:** Claude mit Deckel, kostet. **C:** warten. Empfehlung **A zuerst, B danach**; Default **A**. **Frist 19.08.** — das ist morgen. Daran hängt der Erstauftrag des promt-teams. |
| ⚠ **Die Frage zu den Mail-Zugangsdaten steht weiter offen** | Aus Sprint 17, `team-mail/N-0003`: Sind `MAIL_IMAP_HOST/USER/PASS` in der Umgebung gesetzt, in der die **Routine** läuft? Der Tages-Digest fehlt weiterhin. |
| ⚠ **Deine Zählung steht weiter aus** | Wie viele Kacheln siehst du im Reiter „Dashboard" **ohne Scrollen**? ⚠ Wir können es nicht selbst messen — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ⚠ **Unsere Prüfung bleibt rot, und zwar zu Recht** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15 stehen unverändert in der Geschichte. Neu dazugekommen ist **keiner**. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es wieder etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

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
