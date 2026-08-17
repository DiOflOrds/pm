# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 15** (2026-08-17, Start 14:13, Kennung
   `2026-08-17T1410-cowork-s15`). **Ein** Lauf, kein Nebenlauf — erstmals seit Sprint 13.
2. **✅ Das dringlichste offene Ticket der Organisation ist gebaut: `platform/T-0013`
   (SWR-136).** Das Sprintregister kennt ab jetzt ein **Ende**; eine Zeile ohne `ende` ist
   ein laufender Sprint, und `beginne()` verweigert die Eröffnung, solange einer läuft.
   Zweimal verschoben und **beide Male vom eigenen Schadensfall überholt**.
3. **⚠ Die Zeitgrenze der ersten DoD ist vor dem Bauen gemessen und verworfen worden** —
   Median 57 Min, Minimum **15**, **7 von 12** Abständen unter dem Takt. Sie hätte die
   Mehrheit der regulären Folgeläufe abgewiesen. Gebaut wurde die Abbrucherkennung an
   **Schreibspuren**:
   > **Eine Uhr sieht bei 15 Minuten Abstand denselben Wert wie bei einem Absturz nach 15
   > Minuten. Nur die Schreibspur unterscheidet die beiden.**
4. **⚠ Zwei Entscheidungen, die die DoD nicht vorgab, stehen im Ticket statt im Bericht.**
   (a) Die Registerdatei bleibt **append-only**, ihre Zeilen sind ab jetzt **Ereignisse** —
   ein Umschreiben verliert Daten genau bei zwei Schreibern, also im Fall, für den das
   Modul existiert. (b) Die Messung ruft **kein `git`** auf: nach SWR-134 hinterlässt schon
   ein **lesendes** `git status` eine unlöschbare `index.lock`, und eine Prüfung gegen
   Nebenläufigkeit, die selbst Sperren erzeugt, wäre ihr eigener Schadensfall.
5. **⚠⚠ Drei bestehende Zusicherungen hatten das Fehlverhalten ZUGESICHERT.**
   `test_beginne_zaehlt_hoch` verlangte wörtlich `beginne("a") → 1`, `beginne("b") → 2`
   **ohne** dass „a" dazwischen endete — also genau den Schaden, den `platform/T-0013`
   beschreibt.
   > **Eine Prüfung, die den Fehler zusichert, ist schlimmer als keine: sie verteidigt ihn
   > gegen jede Änderung.** Sechste Gestalt der Familie SWR-122/125/128/131/136.
6. **✅ `promt-team/T-0001` nach der FÜNFTEN Berührung zerlegt und Teil a gebaut**
   (`T-0004`, SWR-137): der Feldvertrag der Lauftelemetrie. ⚠ Er liefert **keine Zahl** —
   er macht die Baseline **als leer erkennbar**, mit Namen je fehlender Eingabe, statt als
   siebenfache `0.0`, die wie ein Ergebnis aussieht.
7. **⚠⚠ Ein eigener roter Test hat den Hauptbefund von SWR-137 gefunden: Schlüssel sind
   keine Messungen.** Die erste Fassung wandte die Drei-Zustände-Regel auf alle
   Pflichtfelder an — damit war ein leerer `aufgaben_typ` eine „echte Null", und die Lücke,
   um deren Sichtbarkeit es geht (**6 von 7** Läufen ohne `aufgaben_typ`), wäre von der
   Prüfung durchgewinkt worden.
   > **Eine Regel über Messwerte auf einen Schlüssel anzuwenden ist eine
   > Kategorienverwechslung, und sie macht die Lücke unsichtbar, die sie zeigen soll.**
8. **✅ `pm/T-0052` nach der FÜNFTEN Berührung geschlossen** (SWR-138): „Für dich" hat zwei
   Abschnitte. Die Frage des Auftraggebers war präzise und die Ursache lag eine Etage
   tiefer — **es fehlte kein Filter, sondern der Kanal.**
9. **⚠ Die für `pm/T-0052` benannte Naht wurde beim Schneiden gemessen und war hinfällig.**
   Der Abschnitt „Entscheidungen" existiert seit SWR-042; eine Zerlegung hätte einen
   **leeren** Teil erzeugt. **Eine benannte Naht kann verfallen** — deshalb ganz
   geschlossen, und das steht im Ticket statt in einer stillen Ganzschließung.
10. **✅ `pm/T-0061` gemessen und entschieden (Klasse C) — und die Messung widerlegt die
    Prämisse des eigenen Tickets.** Über **966** Ticket-Blobs der ganzen Historie gezählt:
    **167** trugen `frist` **und** `geplant_sprint`, **81** verschiedene Kombinationen in
    **6** Repos. Die Prüfung hatte also einen großen Anwendungsbereich und hat ihn in
    Sprint 11 **verloren** — sie hatte ihn nicht „nie".
11. **⚠⚠ ZWEI selbstverschuldete Vorfälle desselben Typs in diesem Lauf, einer davon
    committet.** Ein Statuswechsel besteht aus zwei Vorgängen (Datei schreiben, dann
    buchen). Scheitert der zweite an einer Git-Sperre, ist der Zustand geschrieben und
    nicht gebucht. `platform/T-0013`: **vor** dem Commit bemerkt und die Reihenfolge
    wiederhergestellt. `pm/T-0052`: **committet** — `in_progress → done` steht in der
    Historie, dritter unzulässiger Übergang seit dem Stichtag.
    > **Beim ersten Mal ging es gut aus, weil jemand hingesehen hat — nicht, weil eine
    > Vorkehrung gegriffen hätte.**

    Nicht geglättet. Neu als `platform/T-0017`, Lesson `L-2026-08-17ah`.
12. **⚠ Nebenbefund an SWR-134, im selben Lauf gemessen:** der Rückfall von
    `git_schreiben` greift bei **selbstverursachten** Sperren nicht. `verbuche()` ruft `add`
    und dann `commit`; das eigene `add` hinterlässt die `index.lock`, an der das `commit`
    scheitert — und die Wiederholung läuft in dieselbe Folge. Drei Commits dieses Laufs
    quittierten `FEHLER | geraeumt: 19`. Als Punkt 6 in `platform/T-0017`.
13. **⚠⚠ Beim Terminieren gemessen: `blocked_by` kann einen repo-übergreifenden Blocker
    nicht ausdrücken.** Der Versuch, `platform/T-0016` gegen `team-dashboard/T-0001` zu
    sperren, wurde abgewiesen (*„verweist auf unbekanntes Ticket"*). Die Organisation führt
    **17 Repos**, und `ref()` (SWR-087) existiert genau deshalb — für Blocker gilt es nicht.
    > **Ein Abhängigkeitsfeld, das nur innerhalb eines Repos zeigen kann, kann die
    > häufigste Abhängigkeit dieser Organisation nicht ausdrücken: die zwischen zwei Teams.**

    Das Ticket bleibt `open` mit der Blockade **in Prosa** — für jede Prüfung unsichtbar,
    benannt statt geglättet.
14. **Drei Zerlegungen nach der fünften Berührung**, alle an der **im Ticket benannten**
    Naht: `promt-team/T-0001`, `promt-team/T-0002`, `projects/p11/T-0009`.
15. **879 Python-Tests, davon 1 rot** (der Übergangsbefund, selbstverschuldet und benannt),
    **45 JS-Tests grün** (von 40), Matrix **138 SWRs / 0 Lücken**, Briefkasten **0 offen**
    (zweimal geprüft), entschiedene unverbuchte DRs **0**.
    ⚠ **Nicht startklar:** drei unzulässige Statusübergänge seit dem Stichtag — die zwei
    aus Sprint 13 unverändert **plus einer aus diesem Lauf** (Punkt 11).
16. **⚠ Und eine Zahl aus dem Sprint-14-Bericht lässt sich nicht reproduzieren.** Dort
    stand *„826 Python-Tests (2 rot)"*; gemessen ist heute **genau ein** roter Test — und
    der listet **drei** Verstöße in einer Zusicherung. Entweder war damals ein zweiter Test
    rot, der heute grün ist, oder die **Verstöße** wurden als **Tests** gezählt. Welches von
    beiden, ist ohne den damaligen Stand nicht entscheidbar, und deshalb steht hier beides
    statt der bequemeren Vermutung.
    > **„2 rot" und „2 Befunde" sind zwei Aussagen, und eine Kennzahl, die zwischen ihnen
    > rutscht, ist keine Messung mehr.**

## Sprint-Plan

*Sprint 15 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 16; ab Sprint 17 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Jede Verschiebung trägt ihren Grund IM TICKET**, nicht hier. Diese Tabelle ist die
Sicht, das Ticket ist der Ort — die Lehre aus `L-2026-08-17ag` (*eine Korrektur, die nur im
Bericht steht, ist keine*), diesmal auf den eigenen Plan angewandt.

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0013 | cm | dieser Sprint | **erledigt** | ✅ **SWR-136.** Register mit `ende`, Verweigerung **ohne** Zeitgrenze, Abbruch an **Schreibspuren**, Preflight als Leser. 29 Zusicherungen, 9 Gegenproben. ⚠ Zwei Abweichungen von der DoD (append-only Ereigniszeilen, kein `subprocess`) **im Ticket** begründet. |
| promt-team/T-0004 | dev | dieser Sprint | **erledigt** | ✅ **SWR-137**, Teil a von `T-0001`. Feldvertrag, drei Zustände je Feld, Blocker **statt** Schätzung, am **einen** Schreibweg. 15 Zusicherungen. ⚠ Liefert keine Zahl — macht die Lücke sichtbar. |
| pm/T-0052 | pl | dieser Sprint | **erledigt** | ✅ **SWR-138.** Zwei Abschnitte „Für dich", Handlungen als **Teilmenge** derselben Quelle, ohne Knöpfe. 9 Python-, 5 JS-Zusicherungen. ⚠ Die benannte Naht war beim Schneiden **hinfällig**. |
| pm/T-0061 | cm | dieser Sprint | **erledigt** | ✅ Messung über **966** Blobs, Entscheidung **Weg 1** (stehen lassen), Klasse C. ⚠ Die Messung widerlegt die Prämisse des Tickets; der Preis der Entscheidung ist benannt. |
| pm/T-0066 | pl | dieser Sprint | **erledigt** | ✅ **Klammer geschlossen.** Beide Teile fertig; DoD 3 beantwortet: **kein** neuer CR, weil SWR-135 der Nachfolger der widerlegten Ursache ist. |
| promt-team/T-0001 | dev | Sprint 16 | **zerlegt** | ⚠ **5. Berührung, Naht geschnitten** statt ein sechstes Mal angekündigt. Klammer trägt den Termin des letzten Teils; die Verschiebungszählung läuft **hier** weiter. |
| promt-team/T-0002 | test | Sprint 17 | **zerlegt** | ⚠ **5. Berührung.** → `T-0006` (Format, S16) + `T-0007` (Fälle, S17). Die Naht trägt Substanz: **ohne Format sind 20 Fälle 20 Einzelmeinungen**, deshalb `blocked_by` und nicht nur Reihenfolge. |
| projects/p11/T-0009 | dev | Sprint 17 | **zerlegt** | ⚠ **5. Berührung.** → `T-0012` (Deep-Links, S16) + `T-0013` (Mail-Widget hinter dem PIN-Lesegate, S17). Naht = die Begründung des Tickets selbst: **eine Zugriffsentscheidung ist kein Layout**. |
| platform/T-0017 | cm | Sprint 16 | offen | ⚠⚠ **NEU, Befund dieses Laufs, zweimal eingetreten.** Statuswechsel und sein Commit sind zwei Vorgänge. **Dringlichkeit gemessen, nicht vermutet.** Enthält als Punkt 6 den Nebenbefund an SWR-134. |
| promt-team/T-0006 | test | Sprint 16 | offen | **Neu**, Teil a von `T-0002`. `fehlschlag_erkannt_an` als **Pflichtfeld**, Gegenprobe: ein Fall ohne es wird **abgelehnt**, nicht vorbelegt. |
| promt-team/T-0005 | dev | Sprint 16 | offen | **Neu**, Teil b von `T-0001`. Erhebung an der Quelle **und** Auswertung — erst dort wird messbar, ob die Zahl ankommt (SWR-122). |
| projects/p11/T-0012 | dev | Sprint 16 | offen | **Neu**, Teil a von `T-0009`. Deep-Links auf `<projekt>/T-xxxx`, Kennung **vom Server**; Gegenprobe mit doppelt vorkommender Nummer. |
| projects/p11/T-0011 | dev | Sprint 16 | offen | `blocked_by: [T-0010]` seit Sprint 14 **erfüllt** — terminiert, **nicht blockiert**. ⚠ Persistenz ist hier das **Gegenteil** von SWR-133; der Unterschied ist zu begründen, nicht zu behaupten. |
| pm/T-0065 | chg | Sprint 16 | offen | `blocked_by: [T-0064]` **erfüllt**. **2. Verschiebung.** ⚠ Im Ticket steht ausdrücklich, dass es **keine** Naht hat — damit ein späterer Lauf nicht nach einer sucht. |
| pm/T-0063 | chg | Sprint 16 | offen | **2. Verschiebung.** ⚠ **Klasse A** (Team-Gründung): das Ergebnis ist eine **Vorlage an den Menschen**, keine Gründung. `blocked_by` erfüllt. |
| pm/T-0028 | chg | Sprint 16 | **zerlegt** | **Klammer** über `T-0062` (erledigt) / `T-0063`. Kein eigener Arbeitsanteil. |
| pm/T-0054 | chg | Sprint 16 | **zerlegt** | **Klammer** über `T-0064` (erledigt) / `T-0065`. |
| projects/p11/T-0008 | dev | Sprint 16 | **zerlegt** | **Klammer** über `T-0010` (erledigt) / `T-0011`. |
| projects/p12/T-0005 | pl | Sprint 16 | offen | **3. Verschiebung.** `blocked_by: [T-0004]` seit Sprint 12 erfüllt. Der Vollständigkeitsnachweis (SWR-099) war ohne die Teststrecke nicht führbar und ist es jetzt. |
| platform/T-0016 | cm | Sprint 16 | offen | ⚠ **Blockiert, nicht verschoben** — und das Feld kann es nicht sagen (Punkt 13). **Zuerst die Vertragsfrage** an `team-dashboard/T-0001` (B066, Versions-Bump), **dann** Code. Bis dahin bei **3 eingefroren**. |
| promt-team/T-0007 | test | Sprint 17 | offen | **Neu**, Teil b von `T-0002`. `blocked_by: [T-0006]`. |
| projects/p11/T-0013 | dev | Sprint 17 | offen | **Neu**, Teil b von `T-0009`. PIN-Lesegate am **Endpunkt**, nicht in der Ansicht; Kachel sichtbar, Inhalt nicht. |
| projects/p11/T-0003 | pl | Sprint 17 | **zerlegt** | **Klammer** über `T-0007`–`T-0013`, nachgezogen auf den letzten Teil. |
| projects/p12/T-0003 | pl | Sprint 17 | **zerlegt** | **Klammer** über `T-0004`–`T-0006`. |
| projects/p12/T-0006 | pl | Sprint 17 | offen | `blocked_by: [T-0005]` **nicht erfüllt** — **echt blockiert**, deshalb auf den Sprint **nach** dem Blocker. |
| promt-team/T-0003 | dev | Sprint 18 | blocked | `blocked_by` T-0001/T-0002 — nachgezogen hinter die neuen letzten Teile. |
| pm/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten **zweimal** geprüft (Start und Abschluss), beide Male **0 offen**. |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: `L-2026-08-17ah` **sofort** verankert (Statuswechsel als ein Vorgang). |
| platform/T-0001 | cm | jeder Sprint | **erfüllt** | Takt: Preflight, 879 Python-Tests (1 rot, benannt), 45 JS-Tests, Matrix 138/0. ⚠ Der Lauf musste die Suite in Blöcken fahren — ein Durchlauf überschreitet das Zeitfenster des Werkzeugs. Als Beobachtung notiert, nicht als Ticket getarnt. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag — ⚠ **geprüft, nicht angenommen**: SWR-137 und SWR-138 fügen **kein** Kachelfeld hinzu, Vertrag bleibt v2.4. ⚠ **Neu offen bei diesem Takt**: die Vertragsfrage aus `platform/T-0016`. |
| team-mail/T-0001 | dev | jeder Sprint | geplant | Takt: Digest — fällig ab IMAP-Einrichtung, die aussteht. |

## Sprint-Abschluss (Sprint 15, 2026-08-17)

**Geschlossen:** `platform/T-0013`, `promt-team/T-0004`, `pm/T-0052`, `pm/T-0061`,
`pm/T-0066` (Klammer) — **fünf Sachtickets**, plus fünf Takt-Pflichten.

**Zerlegt:** `promt-team/T-0001`, `promt-team/T-0002`, `projects/p11/T-0009` — alle drei bei
der **fünften** Berührung, alle drei an der **im Ticket benannten** Naht.

**Im Lauf dazugekommen:** `promt-team/T-0004`, `promt-team/T-0005`, `promt-team/T-0006`,
`promt-team/T-0007`, `projects/p11/T-0012`, `projects/p11/T-0013`, `platform/T-0017`
(**sieben**, davon sechs aus Zerlegungen und eines aus einem Befund).

**Verifikation:** **879 Python-Tests, 878 grün / 1 rot** (der Übergangsbefund — eine
Zusicherung, die **drei** Verstöße listet), **45 JS-Tests grün** (von 40), Matrix **138
SWRs / 0 Lücken**, Briefkasten **0 offen** (Start und Abschluss), entschiedene unverbuchte
DRs **0**, Plan-Drift 0, Statusdrift 0.

⚠ **Der Lauf ist NICHT startklar, und das ist die richtige Meldung.** Drei unzulässige
Statusübergänge seit dem Stichtag: die zwei aus Sprint 13 (`platform/T-0014`,
`pm/T-0064`) **unverändert** und **einer aus diesem Lauf** (`pm/T-0052`,
`in_progress → done`). Kein Stichtag verschoben, keine Historie umgeschrieben, kein Test
angepasst.

### ⚠⚠ Der Befund dieses Laufs über sich selbst

Sprint 13 hat gelernt, jeden Statusübergang einzeln zu committen (`L-2026-08-17ad`), und
Sprint 14 hat die Regel gehalten. Sprint 15 hat sie **zweimal verloren** — nicht durch
Nachlässigkeit gegenüber der Regel, sondern weil zwischen dem Schreiben und dem Buchen eine
Git-Sperre entstand.

> **Eine Regel, deren Einhaltung von zwei Vorgängen abhängt, wird von jedem Fehler zwischen
> ihnen gebrochen.**

Der Unterschied zwischen dem geretteten und dem verlorenen Fall war die Aufmerksamkeit eines
Augenblicks — und darauf darf keine Regel bauen. Die Reparatur heißt `platform/T-0017`
(*ein Zustandswechsel ist ein Vorgang*), nicht „besser aufpassen".

### Was in Sprint 16 zuerst kommt

1. **`platform/T-0017`** — Statuswechsel und Commit als **ein** Vorgang, inklusive des
   Nebenbefunds an SWR-134 (Räumung **zwischen** `add` und `commit`).
2. **Die Vertragsfrage zu `platform/T-0016`** an `team-dashboard/T-0001` — sie blockiert
   ein Ticket, und das Feld kann die Blockade nicht ausdrücken.
3. **`promt-team/T-0005` und `T-0006`** — die Baseline, auf die der Auftraggeber seit
   `promt-team/N-0001` wartet.
