# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 17, 2026-08-17)

1. **✅ Du hattest recht, und wir hatten es falsch stehen.** Dein Zuruf um 17:54 — *„IMAP ist
   schon längst eingerichtet"* — stimmt. Die Aufgabe, die den Tages-Digest baut, stand bei
   uns seit mehreren Durchläufen als **„wartet auf dich"**. Der Handgriff, auf den sie
   angeblich wartete, war längst erledigt und bei uns auch so vermerkt — nur eben an einer
   anderen Stelle als in dem Satz, den wir dir vorgelegt haben.
   > **Eine Aufgabe, die fälschlich sagt „wartet auf dich", schiebt dir die Schuld dafür zu,
   > dass sie liegen bleibt. Das ist schlimmer, als wenn sie einfach offen dastünde.**

   Wir haben den Satz gestrichen. ⚠ Eine Frage bleibt, und sie ist die einzige: die Routine
   läuft in einer abgeschotteten Umgebung, und dort sind die **Zugangsdaten nicht gesetzt**
   — nachgesehen, nicht vermutet. Sie gehören dorthin auch nicht ins Projekt (sie sind
   geheim). Die Frage steht im Brief.
2. **✅ Drei Aufgaben, die viermal bzw. dreimal liegengeblieben sind, sind erledigt statt
   erneut verschoben.** Der Knopf, mit dem du Aufgaben auf den nächsten Durchlauf setzen
   kannst; die Vorlage für eine Team-Gründung; und das Aufräumen einer Regel, die im
   Cockpit dreimal danebenstand.
3. **⚠⚠ Unser eigenes Werkzeug hat uns in diesem Lauf einen Totalschaden vorgetäuscht.**
   Wir wollten die Übersicht erneuern, welche Anforderung von welchem Test abgedeckt ist —
   und haben den Befehl **ohne einen Zusatz** aufgerufen. Ergebnis: die Übersicht wurde mit
   **24 statt 145** Anforderungen überschrieben und meldete **101 Lücken**. Ohne Fehler,
   ohne Warnung, mit den Worten „Übersicht geschrieben".
   > **Das sah aus wie ein Einbruch unserer Qualität und war ein vergessener Zusatz.**

   Wäre der Lauf an dieser Stelle abgebrochen, hätte der nächste versucht, 101 erfundene
   Lücken zu „reparieren". Repariert ist es im selben Lauf: den falschen Aufruf gibt es
   nicht mehr, beide Varianten liefern jetzt dasselbe.
4. **⚠ Fünf unserer Prüfungen haben in diesem Lauf ihre eigenen Verfasser widerlegt** — vier
   davon beim allerersten Versuch. Eine wollte einen Fehler messen und maß einen anderen.
   Eine verlangte, dass eine Datei mitgespeichert wird, die sich gar nicht ändert. Eine
   fiel genau in die Falle, vor der drei Absätze weiter oben in derselben Datei gewarnt
   wird. Und zwei schrieben eine Zahl fest, die sich planmäßig ändert.
   > **Eine Warnung im Nachbarcode verhindert den Fehler nicht. Die Prüfung, die ihn
   > durchprobiert, tut es.**
5. **⚠⚠ Wir waren heute nicht allein in deinen Ordnern.** Ab etwa 18:10 arbeitet eine
   **zweite Sitzung** an denselben Dateien (ein Post-Widget fürs Dashboard). Wir haben ihre
   Arbeit **nicht angefasst** und aus demselben Grund den Durchlauf **nicht
   abgeschlossen**: ein Sprint, der beendet wird, während noch jemand darin arbeitet, ist
   keine abgeschlossene Runde, sondern eine falsche Buchung. Wer zuletzt fertig wird,
   schließt ihn.
6. **1016 Prüfungen für die Technik (1 rot, der alte Befund von vorgestern — unverändert),
   65 für die Oberfläche (von 51), 147 Anforderungen ohne Lücke.** **Bei dir liegt nichts
   Neues** — außer der einen Frage zu den Zugangsdaten.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠ **Eine Frage zu den Mail-Zugangsdaten** | Sind `MAIL_IMAP_HOST/USER/PASS` in der Umgebung gesetzt, in der die **Routine** läuft — nicht nur in deiner eigenen Shell? Ein `setx` wirkt erst in **neu gestarteten** Programmen. Läuft Mission Control noch aus einer Sitzung von vorher, sieht es die Daten nicht. Davon hängt der Tages-Digest ab. Antwort in `team-mail/N-0003`. |
| ⚠ **Deine Zählung von vorgestern steht weiter aus** | Wie viele Kacheln siehst du im Reiter „Dashboard" **ohne Scrollen**? Davon hängt ab, ob auch die lange Sprint-Tabelle eine Kur braucht. ⚠ Wir können es nicht selbst messen — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ✅ **Der Knopf, um den du gebeten hattest, ist da** | *„Offene Aufgaben aller Teams für den nächsten Durchlauf priorisieren — Knopf statt Einzelbearbeitung."* An jeder Zeile der Aufgabenliste steht er jetzt. Klickst du ihn an einer Aufgabe, die schon dran ist, sagt er dir das — und tut nichts. |
| ⚠ **Unsere Prüfung bleibt rot, und zwar zu Recht** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15 stehen unverändert in der Geschichte. Neu dazugekommen ist **keiner**. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es wieder etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was heute wichtig war — in Ruhe erklärt

### Der Satz, der dir die Schuld zugeschoben hat

In unserem Plan stand bei der Digest-Aufgabe: *„fällig ab IMAP-Einrichtung, und die ist
eine Handlung des Menschen."* Das war ein Satz, der einmal gestimmt hat. Danach wurde die
Einrichtung erledigt — und bei uns auch abgehakt, im Feld des zugehörigen Tickets. Nur der
**Satz** blieb stehen.

Keine unserer Prüfungen hat widersprochen, und der Grund ist einfach: sie lesen **Felder**,
keine Sätze. Der Satz war für jede Prüfung unsichtbar und ist lautlos gealtert.

Das Unangenehme daran ist nicht der Fehler selbst, sondern seine Richtung. Ein Satz, der
„wartet auf den Menschen" sagt, sieht aus wie eine Erklärung und ist eine Zuweisung. Bei
einer Aufgabe, die einfach offen dagestanden hätte, wärst du beim Lesen vermutlich
gestolpert. So bist du es erst gestolpert, als du es zufällig besser wusstest.

Wir haben denselben Merksatz — *was nur im Fließtext steht, prüft niemand* — heute an einer
anderen Stelle sauber angewandt. Hier nicht.

### Wie ein vergessener Zusatz aussah wie ein Zusammenbruch

Wir führen eine Übersicht, welche unserer Anforderungen von welchen Prüfungen abgedeckt
sind. Gestern standen dort 143 Anforderungen und **keine** Lücke.

Heute haben wir das Werkzeug aufgerufen, das diese Übersicht erzeugt — und einen Zusatz
vergessen, mit dem es **alle** Bereiche durchsucht statt nur den ersten. Es hat daraufhin
die Übersicht mit 24 Anforderungen und **101 Lücken** überschrieben. Keine Fehlermeldung.
Die Meldung lautete „Übersicht geschrieben".

Beides für sich war vernünftig eingestellt: ein Zusatz schaltet etwas *hinzu*, und der
Normalfall soll ohne Zusätze laufen. Zusammen ergeben sie: *der unvollständige Modus
schreibt an die Stelle des vollständigen.*

Wir haben es umgedreht. Das Werkzeug durchsucht jetzt immer alles; wer etwas Bestimmtes
will, sagt es ausdrücklich. Und findet es gar nichts, schreibt es **nichts** — statt eine
leere Übersicht an die Stelle der echten zu legen.

### Warum wir heute nicht „fertig" melden

Seit etwa 18:10 arbeitet eine zweite Sitzung an denselben Dateien. Wir haben ihre Arbeit
nicht angerührt und deshalb auch den Durchlauf nicht abgeschlossen: Wer eine Runde für
beendet erklärt, während ein anderer noch darin arbeitet, sortiert dessen Arbeit
nachträglich in eine abgeschlossene Runde ein — und dann stimmt hinterher keine Zählung
mehr.

Uns ist bewusst, dass am Ende möglicherweise **niemand** die Runde schließt und unser
Startcheck das beim nächsten Mal meldet. Das ist der bessere von beiden Ausgängen: eine
gemeldete offene Runde ist ein Hinweis, eine falsch geschlossene ist eine falsche Angabe.

### Was als Nächstes kommt

Sprint 18: die **Goldset-Fälle** (20 reale Beispiele — ohne sie läuft die Qualitätsprüfung
der KI-Rollen nicht an), die **Deep-Links** vom Dashboard in die Detailseiten, und die
**Widget-Konfiguration** mit Speichern. Dazu die Antwort auf die Zugangsdaten-Frage, sobald
sie vorliegt.
