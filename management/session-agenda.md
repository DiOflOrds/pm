# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Stand Sprint 18, 2026-08-17)

1. **✅ Die Aufgabe, die seit gestern die dringlichste war, ist erledigt.** Das Goldset —
   die Sammlung echter Beispiele, an denen sich die Qualität unserer KI-Rollen messen lässt.
   **51 Fälle**, jeder mit einem Beleg, wo er im Bestand steht.
2. **⚠⚠ Und dabei ist uns etwas Unangenehmes über unsere eigene Arbeit aufgefallen.** Wir
   haben, ohne dass es jemand verlangt hatte, eine zweite Messung eingebaut: *Unterscheidet
   unsere Prüfung überhaupt irgendetwas?* Ergebnis beim ersten Entwurf: **41 von 46
   Prüfungen gingen auch bei den falschen Beispielen auf.**
   > **Sie waren alle grün. Und sie haben nichts gemessen.**

   Repariert **vor** dem ersten Speichern: jetzt sind es 2 von 40. Ohne diese Messung wäre
   eine wertlose Sammlung als Maßstab in den Bestand gegangen.
3. **⚠ Wir schreiben ausdrücklich dazu, dass unsere gute Zahl nichts wert ist.** Der Bericht
   nennt eine Erfolgsquote von 100 % — und sagt **vor** der Tabelle, dass man sie **nicht**
   als Zeugnis über die Rollen lesen darf: die Prüfungen sind aus dem Bestand abgeleitet,
   ihr Aufgehen ist zum Teil Bauart. Die Zahl, die zählt, fehlt noch — dafür brauchen wir
   eine Entscheidung von dir (siehe unten).
4. **✅ Links, die ins richtige Ticket führen.** Neun Stellen im Cockpit haben die Adresse
   eines Tickets **selbst zusammengebaut**, obwohl der Server sie fertig liefert.
   > **Der Text unter dem Link kam vom Server, das Ziel aus einer Bastelei daneben. Zwei
   > Aussagen über dasselbe Ticket — solange beide gleich sind, merkt es niemand.**

   Sie sind nicht immer gleich: **68 Ticketnummern gibt es bei uns mehrfach**, `T-0002`
   allein in **17** Projekten. Ab jetzt gibt es **eine** Stelle, und eine Nummer ohne
   Projekt wird gar nicht mehr verlinkt — ein Link ins falsche Projekt ist schlimmer als
   keiner, weil er richtig aussieht.
5. **⚠ Sprint 17 stand seit gestern Abend als „läuft" da, obwohl er fertig war.** Er hatte
   sich absichtlich nicht abgeschlossen, weil ein zweiter Lauf noch in denselben Ordnern
   arbeitete. Unser Werkzeug hätte ihn jetzt automatisch als **„abgebrochen"** eingetragen —
   und das wäre falsch gewesen, er hat vier Aufgaben erledigt. Wir haben ihn von Hand
   korrekt geschlossen und dazugeschrieben, woran wir gemessen haben.
6. **1061 Prüfungen für die Technik (1 rot, der alte Befund von vorgestern — unverändert),
   78 für die Oberfläche (von 73), 150 Anforderungen ohne Lücke.**

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **Eine neue Frage, und sie kostet möglicherweise Geld** | Um zu messen, wie gut eine KI-Rolle **heute wirklich** arbeitet, muss sie einmal über die 51 Beispiele laufen. Das braucht einen Anbieter. **Option A:** das lokale Ollama — kostenlos, sofort, misst aber nur die kleine Stufe. **Option B:** Claude mit Deckel — die Zahl, auf die es ankommt, kostet aber. **Option C:** warten. Wir empfehlen **A zuerst, B danach**; Default ist **A**. Steht in `promt-team/T-0009`, Frist 19.08. **Wir haben nichts vorbereitet, das ohne deine Antwort losläuft.** |
| ⚠ **Die Frage zu den Mail-Zugangsdaten steht weiter offen** | Aus Sprint 17, `team-mail/N-0003`: Sind `MAIL_IMAP_HOST/USER/PASS` in der Umgebung gesetzt, in der die **Routine** läuft? Davon hängt der Tages-Digest ab. Der für den 17.08. fehlt weiterhin. |
| ⚠ **Deine Zählung von vorgestern steht weiter aus** | Wie viele Kacheln siehst du im Reiter „Dashboard" **ohne Scrollen**? ⚠ Wir können es nicht selbst messen — dafür bräuchten wir einen echten Browser, und den hat unsere Prüfstrecke bewusst nicht. |
| ⚠ **Unsere Prüfung bleibt rot, und zwar zu Recht** | Die drei übersprungenen Aufgabenstände aus den Sprints 13 und 15 stehen unverändert in der Geschichte. Neu dazugekommen ist **keiner**. |
| ⚠ **`abschluss.cmd` prüfen (aus Sprint 1)** | Unverändert dein einziger Altpunkt. |
| ✅ **Zu pushen gibt es wieder etwas** | Zeile steht in `PUSH-ANFORDERUNG.txt`. Wir pushen nie selbst. |

---

## Was heute wichtig war — in Ruhe erklärt

### Ein Satz, der ehrlich klang, und niemand hat ihn je geprüft

In der Aufgabenbeschreibung des Goldsets stand seit drei Tagen: *„Real heißt: aus dem
Bestand belegt, nicht ausgedacht."* Ein guter Satz. Nur: **keine unserer Prüfungen liest
Sätze.** Sie lesen Felder.

Ein Lauf hätte 51 gut klingende, frei erfundene Beispiele schreiben, „erledigt" melden und
niemandem auffallen können. Der Satz hätte danebengestanden und ausgesehen, als hätte er
etwas verhindert.

Jetzt trägt jedes Beispiel ein **Feld** mit der Stelle, an der es im Bestand steht — Datei
**und** Textstelle darin. Beim Speichern wird nachgeschlagen, ob die Stelle wirklich dort
ist. Der Grund für „und Textstelle" statt nur „Datei":

> **Eine Datei existiert auch für ein erfundenes Beispiel.**

Das ist derselbe Merksatz, an dem wir dir gestern die falsche Auskunft zum IMAP gegeben
haben — was nur im Fließtext steht, prüft niemand. Diesmal an der Sache angewandt statt im
Rückblick zitiert.

### Warum wir eine 100 % nicht als Erfolg verkaufen

Unser Bericht sagt: von den entscheidbaren Fällen gehen alle auf. Das klingt hervorragend
und wäre irreführend. Die Prüfausdrücke sind **aus denselben Dateien abgeleitet**, gegen die
sie laufen — dass sie aufgehen, ist zu einem großen Teil Bauart und kein Befund.

Wir haben den Satz deshalb **über** die Tabelle gesetzt, nicht darunter. Eine Zahl mit einem
Vorbehalt dahinter wird ohne den Vorbehalt gelesen.

Was der Bericht wirklich belegt: dass jeder Fall **ausführbar** ist, dass jeder **belegt**
ist, und **welche sechs** sich gegen den Bestand gar nicht entscheiden lassen — die stehen
namentlich da, mit ihrer Belegstelle. Sie sind ausdrücklich **nicht** als durchgefallen
gezählt: das hätte die Quote schlechter gemacht, sie wegzulassen hätte sie besser gemacht,
und beides wäre eine erfundene Zahl.

### Eine Prüfung, die an ihrer eigenen Erklärung gescheitert ist

Wir haben eine Prüfung gebaut, die zählt, ob eine bestimmte Adresse im Code nur **einmal**
vorkommt. Sie meldete „zweimal". Der zweite Fund war das **Beispiel im Kommentar direkt
darüber**, das erklärt, wofür die erste da ist.

> **Eine Textsuche kann eine Erklärung nicht von ihrem Gegenstand unterscheiden — und die
> Erklärung steht nun einmal genau dort, wo der Gegenstand ist.**

Das ist uns in zwei Tagen jetzt **fünfmal** passiert. Gemessen wird ab hier der Code ohne
Kommentare.

### Was als Nächstes kommt

Sprint 19: die **Zusammenführung der beiden Textdarstellungen** (dafür liegt jetzt eine
vollständige Vorlage vor, samt einer Zahl, die auf null muss), die **Widget-Konfiguration
mit Speichern** und das **Mail-Widget hinter dem PIN**. Dazu deine Antwort auf die
Anbieter-Frage, sobald sie vorliegt.
