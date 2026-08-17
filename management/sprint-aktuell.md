# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 17** (2026-08-17, Start 16:49, Kennung
   `2026-08-17T1650-cowork-s17`). ⚠ **Dieser Lauf hat den Sprint nicht eröffnet, sondern
   übernommen.** Die Registerzeile stand um 16:49 in der Datei und war **nicht committet**;
   seit dem Ende von Sprint 16 (17:10) hatte **kein** Repo einen Commit. Der Lauf, der die
   Zeile schrieb, ist zwischen dem Schreiben und seinem ersten Commit abgebrochen.
   > **Ein Lauf, der zwischen Registerzeile und erstem Commit stirbt, hinterlässt einen
   > Sprint, der laufend aussieht und nichts hervorgebracht hat.**

   Gewählt ist der **idempotente Wiedereintritt**, den `beginne()` seit SWR-136
   ausdrücklich vorsieht („ein Lauf, der zweimal startet, erhöht den Zähler nicht") — keine
   Übernahme mit neuer Nummer, die eine Sprintnummer für einen Lauf ohne Ergebnis
   verbraucht hätte. Verankert als `L-2026-08-17ap`.
2. **✅ Die zwei Tickets bei der VIERTEN Berührung sind gebaut, nicht verschoben.**
   `pm/T-0065` (**SWR-144**, Terminierungsknopf) und `pm/T-0063` (**SWR-147**,
   Team-Gründung vorlegen). Beide sagten in ihrem eigenen Text, dass sie **keine Naht**
   haben und eine erfundene Zerlegung schlimmer wäre als der Bau.
3. **✅ `platform/T-0016` ist geschlossen — der benannte Altbestand ist von 3 auf 0**
   (**SWR-146**, Widget-Vertrag **v2.5**). Der Cockpit-Payload trägt den Zustand je Feld;
   die drei Inline-Formulierungen der Regel sind durch **eine** Stelle ersetzt.
   > **Ein Ticket gegen B033 zu lösen, indem man einen neuen B033-Fall anlegt, ist keine
   > Lösung, sondern eine Verschiebung mit besserer Presse.**
4. **⚠⚠ Und dieser Lauf hat einen Werkzeugfehler AUSGELÖST, nicht gelesen** (`platform/T-0019`,
   **SWR-145**): `trace_matrix.py` **ohne** `--alle-projekte` hat die kanonische Matrix mit
   **24 von 145** Anforderungen überschrieben — 121 Zeilen weg, Meldung „Matrix
   geschrieben", **Exit 0**.
   > **Ein Werkzeug, dessen unvollständiger Modus an den Ort des vollständigen schreibt,
   > macht aus einem Tippfehler einen Totalbefund.**

   Keine der beiden Voreinstellungen ist allein falsch — genau deshalb hat es keine
   bestehende Prüfung gefunden. Es ist die Bauart von **SWR-143** eine Etage höher: die
   Richtigkeit hing am Wissen des Aufrufers. Reparatur **im selben Lauf**: Discovery ist
   der Normalfall, beide Aufrufe liefern jetzt dasselbe.
5. **⚠⚠ Der Fingerprint-Schutz (SWR-080) durfte für den Knopf entfallen, und das Argument
   hängt an EINEM Feld.** SWR-080 schützt den Wert, den der Client **gesehen** hat; eine
   Terminierung bringt keinen mit. Deshalb steht die Feldmenge als Konstante da und wird
   **gezählt** — käme ein zweites Feld dazu, wäre das Argument still falsch.
6. **⚠ Der eigentliche Befund von SWR-144 saß nicht im Knopf, sondern in der
   Fehlerabbildung darunter.** `tickets.speichere` übersetzte **jeden** `ValueError` in
   HTTP 400 — auch „das Feld trägt den Wert schon".
   > **Ein Knopf, dessen „schon erledigt" von seinem „hat nicht funktioniert" nicht zu
   > unterscheiden ist, ist eine Anzeige ohne Aussage.**

   Gebaut ist ein **eigener Typ** und kein Textvergleich (`L-2026-08-17ak` angewandt statt
   zitiert), und die Unterscheidung ist bis in die Ansicht durchgehalten: drei Zustände,
   drei Gestalten.
7. **⚠ Vier Zusicherungen haben in diesem Lauf ihre eigenen Verfasser korrigiert.**
   (a) Der Rollback-Test schob `.git` weg und maß damit **404 statt 503** — die Rücknahme
   wurde nie erreicht. (b) Eine Zusicherung verlangte `BOARD.md` im Commit; das Board
   ändert sich bei einer Terminierung **nicht**. (c) `cockpitFeldText` fiel bei unbekanntem
   Zustand auf `"undefined"` durch — *wörtlich* der Fehler, den der Kommentar drei
   Funktionen weiter oben beschreibt. (d) Ein Test namens *„die Version wird gelesen und
   nicht eingetragen"* trug die Version selbst als Literal.
   > **Eine Warnung, die im Nachbarcode steht, verhindert den Fehler nicht — die
   > Zusicherung, die sie messbar macht, tut es.**
8. **⚠ Eine fünfte Zusicherung war auf eine ZEILENNUMMER geprüft** und wurde von einer
   Einfügung zwanzig Zeilen darüber rot. Der geprüfte Sachverhalt stand unverändert da.
   > **Eine Zeilennummer ist keine Eigenschaft des Bestands, sondern eine Eigenschaft des
   > Tages, an dem gemessen wurde.**

   Besonders teuer hier, weil dieser Test **gegen das Wegsehen** existiert (SWR-125) und
   ein Fehlalarm genau dazu erzieht.
9. **✅ Der Widget-Vertrag ist diesmal NICHT vom Wächter nachgezogen worden**, sondern im
   selben Lauf wie der Payload — die erste Ausnahme von `L-2026-08-17y` („wer Code ändert,
   sieht den Vertrag nicht"). Der Grund ist kein Vorsatz, sondern die **Reihenfolge**: DoD 1
   von `platform/T-0016` stand einen ganzen Sprint **vor** dem Code.
10. **⚠⚠ Der Auftraggeber hat uns MITTEN IM LAUF bei einer falschen Behauptung erwischt**
    (`team-mail/N-0003`, 17:54): *„team-mail/T-0001 -> IMAP ist schon längst
    eingerichtet."* Er hat recht. `team-mail/T-0002` steht auf **`done`**, und trotzdem
    stand in **diesem** Plan bis eben „wartet-auf-Mensch — fällig ab IMAP-Einrichtung".
    > **Eine Aufgabe, die fälschlich „wartet auf den Menschen" sagt, verschiebt die Schuld
    > an ihrem Liegenbleiben — das ist schlimmer als eine, die einfach offen dasteht.**

    Der Grund stand als **Satz im Plan** und nicht als **Feld am Ticket**; `blocked_by` war
    korrekt und längst erfüllt, und keine Prüfung liest den Plansatz. Das ist wörtlich
    `L-2026-08-17ag` — an einer anderen Stelle desselben Tages angewandt und hier nicht.
11. **⚠⚠ Und dieser Lauf war NICHT allein im Repo.** Ab etwa 18:10 arbeitet eine **zweite
    Session** in denselben Ordnern (`team-mail/T-0004`, `platform/tests/test_widget_post.py`,
    Widget-Vertrag **v2.6** / SWR-148). Gemessen an Dateizeiten, nicht vermutet.
    **Folge, und sie ist die wichtigste Entscheidung dieses Abschlusses: Sprint 17 wird
    NICHT beendet.** `beende()` würde den laufenden Sprint unter der anderen Session
    schließen und ihre Commits in einen abgeschlossenen Sprint fallen lassen — genau der
    Buchhaltungsschaden, gegen den SWR-136 gebaut wurde.
12. **⚠ Eine Zusicherung DIESES Laufs war binnen 30 Minuten falsch.** `test_vertragsversion_ist_25`
    schrieb die Vertragsversion fest; die parallele Session hat sie zu Recht auf v2.6
    gehoben. Es ist derselbe Fehler, den dieser Lauf eine Stunde vorher als
    `L-2026-08-17an` **aufgeschrieben** hat.
    > **Eine Versionsnummer festzuschreiben heißt, jeden künftigen Bump zum Fehler zu
    > erklären — und der Bump ist genau das, was der Vertrag verlangt.**

    Geprüft wird jetzt die Untergrenze und vor allem der **Sachverhalt** (steht `zustaende`
    in der Feldliste?). Die Nummer ist der Beleg, das Feld ist die Sache.
13. **1016 Python-Tests, davon 1 rot** (der Altbefund über drei unzulässige Statusübergänge
    aus den Sprints 13 und 15 — **keiner aus diesem Lauf**), **65 JS-Tests grün** (von 51),
    Matrix **147 SWRs / 0 Lücken** (Stand unserer Messung; der Bestand steht beim Abschluss bei **148 / 0** — SWR-148 kommt vom parallelen Lauf), Briefkasten **0 offen** (Start, mittendrin **1 neuer**,
    beantwortet, Abschluss wieder 0), entschiedene unverbuchte DRs **0**, Plan-Drift 0,
    Statusdrift 0.
    ⚠ **Nicht startklar**, und das bleibt die richtige Meldung. Kein Stichtag verschoben,
    keine Historie umgeschrieben, kein Test angepasst, um grün zu werden.

## Sprint-Plan (Abschlussstand)

*Sprint 17 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 18; ab Sprint 19 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier (`L-2026-08-17ag`).

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0065 | chg | dieser Sprint | **erledigt** | ✅ **SWR-144.** 4. Berührung, gebaut statt verschoben. Ein Klick, **ein** Feld, Wert aus dem Register; „unverändert" ist ein Erfolg mit eigenem Typ und **ohne** Commit. 15 Python- + 7 JS-Zusicherungen. |
| platform/T-0019 | cm | dieser Sprint | **erledigt** | ✅ **SWR-145, NEU aus einem Werkzeugfehler DIESES Laufs.** Discovery ist der Normalfall; der falsche Aufruf existiert nicht mehr. ⚠ Der Beleg ist die **Gleichheit** zweier Aufrufe. |
| platform/T-0016 | cm | dieser Sprint | **erledigt** | ✅ **SWR-146**, DoD 2–4. Payload trägt den Zustand (Schwesterschlüssel, v2.5), Altbestand **3 → 0**. ⚠ Die Zustandsmenge folgt dem **Vertrag**, nicht der Ansicht. |
| pm/T-0063 | chg | dieser Sprint | **erledigt** | ✅ **SWR-147.** 4. Berührung. **Klasse A gewahrt:** vorgelegt, nicht gegründet — am Dateisystem zugesichert. Auflagen aus SWR-127 als **Prosa** im DR. |
| pm/T-0028 | chg | Klammer | **erledigt** | ✅ Klammer geschlossen (`T-0062` + `T-0063`). Acht wortgleiche Verschiebungen in der Historie — die Zerlegung hat gewirkt. |
| pm/T-0054 | chg | Klammer | **erledigt** | ✅ Klammer geschlossen (`T-0064` + `T-0065`). |
| pm/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten **zweimal** geprüft, beide Male **0 offen** (55 Briefe). |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: **acht** Lessons SOFORT verankert (`L-2026-08-17al` bis `as`), verteilt auf cm/pl/test. |
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: 1013 Python-Tests (1 rot, Altbefund), 65 JS-Tests grün, Matrix 147/0. ⚠ Die Suite läuft in **Blöcken** — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag — Bump auf **v2.5** vollzogen, Übergangsdoppelung im selben Lauf zurückgebaut. |
| team-mail/T-0001 | dev | jeder Sprint | offen | ⚠⚠ **Korrigiert in diesem Lauf, auf Zuruf des Auftraggebers** (`team-mail/N-0003`): hier stand mehrere Sprints lang „wartet-auf-Mensch — fällig ab IMAP-Einrichtung". `T-0002` ist **`done`**. Der Digest für den 17.08. fehlt; diese Sandbox hat die Zugangsdaten nicht (Datenklasse `geheim`). Rückfrage im Brief gestellt. |
| promt-team/T-0007 | test | Sprint 18 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. Blocker erfüllt — terminiert, nicht blockiert. **Ab Sprint 18 das dringlichste Sachticket:** ohne die 20 Fälle läuft das Eval-Gate nicht. |
| projects/p11/T-0012 | dev | Sprint 18 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Spitze einer Kette von zwei. |
| projects/p11/T-0011 | dev | Sprint 18 | offen | ⚠ **2. Verschiebung**, Grund im Ticket. Es hat **keine** Naht, und das steht im Ticket — damit ein späterer Lauf nicht danach sucht. |
| projects/p12/T-0009 | pl | Sprint 18 | offen | ⚠ **1. Verschiebung**, Grund im Ticket. `blocked_by` erfüllt. |
| projects/p11/T-0013 | dev | Sprint 18 | offen | `blocked_by: [T-0012]` — **echt blockiert**, der Termin folgt dem Blocker. |
| projects/p12/T-0006 | pl | Sprint 18 | offen | `blocked_by` zieht auf `T-0009` nach — nicht erfüllt. |
| promt-team/T-0003 | dev | Sprint 18 | blocked | `blocked_by` T-0001 (erfüllt) / T-0002 (Klammer über `T-0007`). |
| platform/T-0020 | cm | Sprint 18 | offen | **Neu**, abgetrennt von `T-0019`. ⚠ **Nicht** dessen Reparatur: drei Fragen sind vor dem Bauen zu beantworten, sonst wird die Prüfung ein Dauerbefund. |
| promt-team/T-0002 | test | Klammer | **zerlegt** | Klammer über `T-0006` (erledigt) / `T-0007`. |
| projects/p11/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0007`–`T-0013`. |
| projects/p11/T-0008 | dev | Klammer | **zerlegt** | Klammer über `T-0010` (erledigt) / `T-0011`. |
| projects/p11/T-0009 | dev | Klammer | **zerlegt** | Klammer über `T-0012` / `T-0013`. |
| projects/p12/T-0003 | pl | Klammer | **zerlegt** | Klammer über `T-0004`–`T-0009`. |
| projects/p12/T-0005 | pl | Klammer | **zerlegt** | Klammer über `T-0008` (erledigt) / `T-0009`. |

### Endzustand, kein Plan (Vollständigkeit der Zählung)

`p0/T-0008` (API-Key), `p0/T-0047` (Hub-VM), `p0/T-0072` / `p1/T-0018` (Copilot-PoC) stehen
auf `rejected` und warten auf eine **Handlung des Menschen**. Sie erscheinen seit SWR-138
im Abschnitt „Für dich: Handlungen".

## Sprint-Abschluss (Sprint 17, 2026-08-17)

**Geschlossen:** `pm/T-0065`, `platform/T-0019`, `platform/T-0016`, `pm/T-0063` — **vier
Sachtickets**, dazu die **zwei** Klammern `pm/T-0028` und `pm/T-0054` und **fünf**
Takt-Pflichten.

**Im Lauf dazugekommen:** `platform/T-0019` (im selben Lauf gebaut und geschlossen) und
`platform/T-0020` (Naht benannt, drei Fragen offen).

**Neue Anforderungen:** **SWR-144** bis **SWR-147** — vier.

**Verifikation:** **1016 Python-Tests, 1015 grün / 1 rot** (der Altbefund über drei
unzulässige Übergänge — **keiner aus diesem Lauf**), **65 JS-Tests grün** (von 51) — beim Abschluss **73**, weil der parallele Lauf acht beigesteuert hat —, Matrix **147 SWRs / 0 Lücken** bei unserer Messung und **148 / 0** beim Abschluss, Briefkasten **0 offen** (Start; **1 neuer Brief mitten im Lauf**,
beantwortet; Abschluss wieder 0), entschiedene unverbuchte DRs **0**, Plan-Drift 0,
Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: zwei aus Sprint 13 (`platform/T-0014`, `pm/T-0064`) und
einer aus Sprint 15 (`pm/T-0052`), **alle unverändert**. Nichts geglättet.

### ⚠⚠ Sprint 17 bleibt OFFEN — bewusst, mit Grund

Ab etwa 18:10 arbeitet eine **zweite Session** in denselben Repos: `team-mail/T-0004`
(Dashboard-Widget), `platform/tests/test_widget_post.py`, Widget-Vertrag **v2.6** mit einer
**SWR-148**, die in `p9` noch nicht steht. Gemessen an Dateizeiten und am Inhalt der
Arbeitskopie, nicht vermutet.

`beende()` aufzurufen hieße, den laufenden Sprint **unter** dieser Session zu schließen —
ihre Commits fielen danach in einen abgeschlossenen Sprint, und das Register trüge eine
Lücke, die niemand mehr zuordnen kann. Genau dagegen ist SWR-136 gebaut.

> **Ein Sprint, der beendet wird, während noch jemand darin arbeitet, ist kein
> abgeschlossener Sprint, sondern eine falsche Buchung mit Zeitstempel.**

Diese Session hat deshalb **alles committet**, aber **nicht abgeschlossen**. Die
Registerzeile für Sprint 17 trägt weiterhin kein `ende` — das ist hier **kein** Befund,
sondern die Meldung. Der Lauf, der als letzter fertig wird, schließt ihn.

⚠ Und die Kehrseite ist benannt: bleibt die andere Session ebenfalls stehen, hat Sprint 17
am Ende **kein** `ende`, und `nicht_beendete()` wird ihn beim nächsten Lauf melden. Das ist
der richtige Ausgang — ein gemeldeter offener Sprint ist ein Befund, ein falsch
geschlossener ist eine Lüge in der Buchhaltung.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Sprint 16 hat einen Fehler **in Produktion während des Laufs** gefunden (SWR-143) und ihn
im selben Lauf repariert. Sprint 17 hat einen **ausgelöst** — und der Unterschied ist die
Pointe:

> **SWR-143 fand eine Funktion, die ihre Abhängigkeit nur fand, wenn der Aufrufer sie
> mitbrachte. SWR-145 ist dasselbe eine Etage höher: ein Werkzeug, das seine Quellen nur
> findet, wenn der Aufrufer ein Flag mitbringt — und beide Male ist das Ergebnis eines
> unwissenden Aufrufers nicht als falsch erkennbar.**

Dazu haben **fünf** Zusicherungen in diesem Lauf ihre eigenen Verfasser korrigiert, davon
vier beim **ersten** Lauf. Eine von ihnen fand einen Fehler, dessen Beschreibung drei
Funktionen weiter oben in derselben Datei stand — als Kommentar.

⚠ Die Erkennungsfrage aus Sprint 16 — *welche unserer inzwischen über 1000 Zusicherungen
prüfen etwas, das die Testdatei selbst eingerichtet hat?* — bleibt **unbeantwortet** und
steht weiter in `L-2026-08-17ai`. Dieser Lauf hat sie nicht angefasst und behauptet nicht,
sie beantwortet zu haben.

### Was in Sprint 18 zuerst kommt

1. **`promt-team/T-0007`** (Goldset-**Fälle**) — der Blocker ist seit Sprint 16 erfüllt, und
   ohne die 20 Fälle läuft das Eval-Gate `T-0003` nicht. Eine zweite Verschiebung hier
   verschiebt eine ganze Kette.
2. **`projects/p11/T-0012`** und **`p11/T-0011`** — beide bei der **dritten** Berührung; bei
   der vierten greift `L-2026-08-17x`, und `T-0011` sagt im Voraus, dass es keine Naht hat.
3. **`projects/p12/T-0009`** — Blocker erfüllt, und es entblockt `p12/T-0006`.
