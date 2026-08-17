# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 10** (2026-08-17, Takt 60 Min). Der Zähler steht in
   `pm/management/sprints.jsonl`, eine Zeile je Lauf.
2. **⚠⚠ Der Startcheck meldete `PREFLIGHT: STARTKLAR` — und log dabei nicht, sondern
   schwieg an zwei Stellen.** Gegen denselben Bestand ergab `plan_drift` (SWR-109) **3**
   und `sprint_vergangen` (SWR-112) **3**. Beide Kennzahlen werden von `sprint.plan()`
   berechnet, in den Payload gelegt — und von **niemandem gelesen**. Sie standen einen
   Schlüssel neben `status_drift`, das der Preflight liest. Gebaut: **SWR-122**
   (`platform/T-0011`).
3. **⚠ Und der Abschlussbericht von Sprint 9 hat deshalb an drei Stellen eine falsche
   Zahl gemeldet:** „unterminiert 0, überfällig 0, **Plan-Drift 0**, Statusdrift 0" stand
   in `PROJEKTSTATUS-UPDATE.md`, `sprint-aktuell.md` **und** `session-agenda.md`.
   Gemessen am Bestand, den derselbe Lauf committet hat: Plan-Drift **3**, überfällig **1**.
4. **Wie die Null falsch wurde, ist der eigentliche Befund.** Sie war richtig, als sie
   gemessen wurde. Danach hat derselbe Lauf die **Plantabelle** umgeschrieben (`pm/T-0028`
   und `pm/T-0039` von „Sprint 9" auf „Sprint 10"), ohne die **Ticketfelder** nachzuziehen —
   und damit den Drift *erzeugt*, den die Zahl daneben bestritt.
   **Eine Messung, die vor der Änderung liegt, die sie abdecken soll, misst den
   Ausgangszustand.**
5. **⚠ `pm/T-0039` ist viermal um genau eins verschoben worden** — `geplant_sprint`
   6→7→8→9, in keinem Fall mit einem neuen Grund; der Abschnitt „Warum nicht in dieser
   Session gebaut" steht wörtlich seit der Erstanlage. Beim fünften Mal wurde nicht einmal
   mehr das Feld erhöht, sondern nur die Plantabelle — **daran ist es aufgefallen**.
   Zerlegt in `pm/T-0059` (Sprint 11, erste Sacharbeit) und `pm/T-0060`.
6. **⚠ Fünfter Sprint in Folge, in dem ein Verschiebungsgrund an der Messung scheitert.**
   `pm/T-0028` („Risiko einer Fehlannahme ohne Rückfrage") ist derselbe Bau wie
   `pm/T-0047` in Sprint 9: die Feldliste ist **Klasse C**, es gab **keinen** DR dazu, und
   die Felder stehen bereits in der eigenen DoD des Tickets. **Entschieden und
   ausgeschrieben** — der nächste Lauf baut statt zu überlegen.
7. **✅ Der Bug des Auftraggebers ist zu Ende repariert.** `pm/T-0055` Teil 2
   (**SWR-123**): die verwaiste `index.lock` wird über den **vorhandenen** Mechanismus
   geräumt und der Commit **einmal** wiederholt. Der Fall tritt für ihn nicht mehr auf.
8. **⚠ Der Bau hat drei Tests aus Sprint 9 umgeworfen — und sie hatten recht.** Sie
   erzeugten ihren Fehlerfall über genau die Sperre, die SWR-123 jetzt wegräumt.
   **Ein Test, der seinen Fehlerfall über einen Mechanismus erzeugt, den das System später
   repariert, prüft ab dann nicht mehr, was in seinem Namen steht.** Behoben, indem die
   **Provokation** ersetzt wurde, nicht die Erwartung.
9. **⚠ `pm/T-0057`: zwei von drei genannten Ursachen halten der Messung nicht stand.**
   Die Beschreibung **wird** geprüft (drei Prüfungen), und die Zeilenumbrüche gingen nicht
   „beim Einfügen" verloren, sondern werden **absichtlich** zusammengezogen — eingebaut auf
   Brief `pm/N-0023`, der genau darum bat. Gefehlt hat weder Prüfung noch Grenze, sondern
   ein **Zielort**. Gebaut: **SWR-124**.
10. **⚠ Und dabei fielen zwei weitere Alttests, die dasselbe falsch machten** — sie
    prüften den *Aufbewahrungsort* des Textes statt die Zusage „wird angenommen und nicht
    gekürzt". **Zweimal in einem Lauf stand in einem Test etwas anderes als in seinem
    Namen.**
11. **✅ `pm/T-0053` beantwortet, ohne eine Zeile Code:** die 21× `open -> in_review`
    zerfallen nach Datum in **drei Ereignisse** — 7 vor Existenz der Prüfung, 13 aus
    **einer** Sitzung binnen 56 Minuten, 1 Einzelfall neun Tage später. Kein Repo außer
    p0/p1 kommt vor. **`UEBERGAENGE` bleibt unverändert.**
    **Eine Zahl von Befunden zählt Artefakte, keine Entscheidungen.**
12. **Vier Sachtickets geschlossen** (`platform/T-0011`, `pm/T-0053`, `pm/T-0055`,
    `pm/T-0057`) plus sechs Takt-Pflichten. **Drei neue Tickets** aus Zerlegungen
    (`pm/T-0058`, `pm/T-0059`, `pm/T-0060`).
13. **Die sechs Planbefunde sind aufgelöst** — Plan-Drift 0, überfällig 0, und diesmal
    **nach** der Änderung gemessen.

## Sprint-Plan

*Sprint 10 = dieser Lauf (2026-08-17, Takt 60 Min). Default nach pm/D006: in diesem Sprint
schließen. Verschieben nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder
blockiert. **Fest geplant** ist Sprint 11; ab Sprint 12 ist die Nummer eine
**Reihenfolge**, keine Zusage.*

*Die Fälligkeitsspalte und das Feld `geplant_sprint` sagen dasselbe (SWR-109); die
**Statusspalte** wird gegen den Ticketstatus gehalten (SWR-115). **Ab Sprint 10 liest der
Preflight beide** (SWR-122) — bis dahin wurden sie berechnet und von niemandem gelesen.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| platform/T-0011 | cm | dieser Sprint | **erledigt** | **Neu, aus dem Startcheck.** Preflight meldete STARTKLAR über 3+3 Befunden. **SWR-122**: `plan_drift` und `sprint_vergangen` aus **derselben** Sprintsicht wie `status_drift`, mit Referenzen, auch bei 0, und als Befund zählend. Ein Aufruf je Lauf statt drei (B033). 13 Tests. |
| pm/T-0055 | dev | dieser Sprint | **erledigt** | **Teil 2 gebaut (SWR-123).** Verwaiste Sperre über den vorhandenen Mechanismus räumen, Commit **einmal** wiederholen. 8 Tests. ⚠ Drei SWR-121-Tests provozierten ihren Fehler über genau diese Sperre — Provokation ersetzt, nicht Erwartung. Teil 3 (Anzeige) → `pm/T-0058`. |
| pm/T-0057 | dev | dieser Sprint | **erledigt** | **Zwei von drei Ursachen widerlegt.** Nicht die fehlende Prüfung, sondern der fehlende **Zielort**. **SWR-124**: `ZELLE_MAX = 400` (gemessen: längste Zellen 229/153, Auslösefall 9.000), langer Text in eigene Datei + Verweis, gleicher Commit, Rücknahme nimmt ihn mit. 10 Tests. |
| pm/T-0053 | pl | dieser Sprint | **erledigt** | **Beantwortet ohne Bau.** 21× `open -> in_review` = drei Ereignisse, nicht eine Praxis; kein Repo außer p0/p1. `UEBERGAENGE` bleibt. Klasse C, mit Widerlegungskriterium bis Sprint 20. |
| pm/T-0028 | chg | Sprint 11 | offen | ⚠ **Verschiebungsgrund gemessen und leer** (5. Sprint in Folge): Klasse C statt A, kein DR, Felder stehen in der eigenen DoD. **Erster Teil in diesem Sprint erledigt** — Feldliste entschieden und ausgeschrieben. Rest = Umfang (3 Flächen). Frist 24.08. |
| pm/T-0039 | pl | Sprint 11 | **zerlegt** | ⚠ **Viermal um eins verschoben ohne neuen Grund.** Nach D006 zerlegt: `T-0059` (Datenmodell, Sprint 11) + `T-0060` (HMI, Sprint 12). Grund dieses Laufs — `briefkasten.py` schon für SWR-123 geändert (B025) — **gilt nur für Sprint 10** und darf nicht fortgeschrieben werden. |
| pm/T-0059 | dev | Sprint 11 | offen | **Neu, aus `T-0039`.** Beitragsformat, `sende(brief=…)`, Statusrücksetzung auf `offen`. ⚠ Ohne Punkt 3 wäre der CR schädlich statt nützlich. **Erste Sacharbeit in Sprint 11.** Frist 24.08. |
| pm/T-0060 | dev | Sprint 12 | blocked | **Neu, aus `T-0039`.** HMI-Teil, `blocked_by: [T-0059]` **im Feld**. Frist 31.08. |
| pm/T-0058 | dev | Sprint 11 | offen | **Neu, aus `T-0055` Teil 3.** Anzeige ohne Reload — und ⚠ auch dann, wenn der Commit scheitert. Andere Fläche als der Schreibpfad (B025). Frist 27.08. |
| pm/T-0054 | chg | Sprint 11 | offen | Knopf zum Priorisieren (Brief `pm/N-0038`). Feldfrage im Ticket entschieden (`geplant_sprint`, nicht `prio`). **Nicht in Sprint 10**, weil der Lauf drei Bauflächen hatte und dies eine vierte wäre (B025). Erste Verschiebung. Frist 24.08. |
| pm/T-0052 | pl | Sprint 11 | offen | HMI-Abschnitt „Für dich: Handlungen". Technisch bereit seit SWR-120. Frist 30.08. |
| projects/p11/T-0008 | dev | Sprint 11 | offen | Teil b): Backend-Endpunkt auf der Cockpit-Quelle + Widget-Konfiguration. **Nicht in Sprint 10** — der Lauf lag auf Prüfstrecke und Briefkasten. Frist 27.08. |
| projects/p11/T-0009 | dev | Sprint 11 | offen | Teil c): Deep-Links + Mail-Widget hinter dem PIN-Lesegate. Frist 03.09. |
| projects/p11/T-0003 | pl | Sprint 11 | offen | **Klammer über `T-0007`/`T-0008`/`T-0009`.** Feld von 8 auf **11** gezogen = Termin des letzten Teils; vorher wurde es als überfällig gemeldet, obwohl es nichts mehr selbst enthält. |
| projects/p12/T-0003 | pl | Sprint 11 | offen | Feld von 10 auf **11** — der Plan hatte recht, das Ticketfeld hing nach. Beim Anfassen zerlegen (D006), nicht schieben. Frist 30.08. |
| pm/T-0001 | pl | jeder Sprint | erfüllt | Takt: Session-Agenda fortgeschrieben. |
| pm/T-0002 | pl | jeder Sprint | erfüllt | Takt: Briefkasten qualifiziert — **kein** Brief offen, keiner eingegangen. |
| pm/T-0003 | coach | jeder Sprint | erfüllt | Takt: Lessons sofort verankert (L-2026-08-17s bis L-2026-08-17v). |
| platform/T-0001 | cm | jeder Sprint | erfüllt | Takt: Preflight, Tests, Matrix. |
| team-mail/T-0001 | dev | jeder Sprint | erfüllt | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. Keine Arbeit, kein Verzug. |
| team-dashboard/T-0001 | pl | jeder Sprint | erfüllt | Takt: Widget-Vertrag — in diesem Sprint **unverändert** (keine Payload-Änderung). |
| promt-team/T-0001 | dev | Sprint 11 | offen | Telemetrie je KI-Rolle. **Nicht in Sprint 10**: das Team ist einen Lauf alt, und der Erstauftrag ist Messgrundlage — dafür braucht es die Rollen-Schnittstelle, die dieser Lauf nicht angefasst hat. Frist 24.08. |
| promt-team/T-0002 | test | Sprint 11 | offen | Goldset je KI-Rolle. Frist 27.08. |
| promt-team/T-0003 | dev | Sprint 12 | blocked | Erstaudit — `blocked_by: [T-0001, T-0002]` **im Feld**. Ohne Baseline kein Optimierungslauf. Frist 03.09. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`): sie laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033) — und genau deshalb nehmen `plan_drift`,
`status_drift` und `sprint_vergangen` sie aus.

**Rollenzuweisungen in diesem Sprint (D006):** `platform/T-0011` liegt bei `cm`, weil es
die **Werkzeugfläche der Prüfstrecke** betrifft — dieselbe Begründung wie bei `pm/T-0048`
in Sprint 9. `pm/T-0053` blieb bei `pl`, weil die Frage am Statusmodell hängt und nicht am
Werkzeug. `pm/T-0039` wurde bei der Zerlegung von `pl` auf `dev` umgehängt (`T-0059`): der
Planungsanteil ist mit der Zerlegung erledigt, der Rest ist Bau.

## Sprint-Abschluss (Sprint 10, 2026-08-17)

**Geplant beim Start:** 20 nicht geschlossene Aufgaben (14 Sachtickets + 6 Takt-Pflichten).
Davon **in diesem Sprint**: 4 Sachtickets + 6 Takt-Pflichten. Im Lauf kamen **vier**
Tickets dazu: `platform/T-0011` aus dem Startcheck und drei aus Zerlegungen
(`pm/T-0058`, `pm/T-0059`, `pm/T-0060`).

**Geschlossen:** `platform/T-0011`, `pm/T-0053`, `pm/T-0055`, `pm/T-0057` und die sechs
Takt-Pflichten — **zehn Stück**. Alle vier Sachtickets über den legalen Weg
(`open → in_progress → in_review → done`) mit je drei Commits.

### ⚠⚠ Der Startcheck war grün und hat an zwei Stellen geschwiegen

Zum zweiten Mal in Folge meldete der Preflight `STARTKLAR`. In Sprint 9 war das die
Nachricht („die Zusage hat gehalten"). Diesmal war es **falsch**:

```
PREFLIGHT: STARTKLAR
$ sprint.plan(".")
plan_drift       -> 3     pm/T-0039, pm/T-0028, p12/T-0003
sprint_vergangen -> 3     p11/T-0003, pm/T-0028, pm/T-0039
```

Beide Kennzahlen existieren seit **SWR-109** bzw. **SWR-112**, werden bei jedem Aufruf von
`sprint.plan()` berechnet und in den Payload gelegt. Der Preflight liest aus demselben
Payload `status_drift` (SWR-115) und meldet es. **Die beiden Nachbarn stehen einen
Schlüssel daneben.**

Die Begründung, die SWR-115 in den Preflight gebracht hat, steht wörtlich in ihrem eigenen
Text: *sichtbar **vor** dem Push und vor dem Bericht an den Auftraggeber, statt einen
Sprint später.* Sie gilt für beide Nachbarn unverändert — und wurde bei beiden nicht
angewandt.

| Prüfung | Seit | Im Preflight? | Folge |
|---|---|---|---|
| `nicht_geplant` (SWR-106) | Sprint 4 | nein | — |
| `plan_drift` (SWR-109) | Sprint 6 | **nein → ab jetzt ja** | Sprint 9 meldete „0" bei 3 |
| `sprint_vergangen` (SWR-112) | Sprint 7 | **nein → ab jetzt ja** | `pm/T-0039` 4× unbemerkt verschoben |
| `status_drift` (SWR-115) | Sprint 8 | ja | greift seit Sprint 9 |

### ⚠ Die Null war richtig — eine Änderung zu früh

Der Abschlussbericht von Sprint 9 nennt an **drei** Stellen „Plan-Drift 0, überfällig 0".
Gemessen am Bestand, den derselbe Lauf committet hat: **3** und **1**.

Der Ablauf, rekonstruiert: Sprint 9 hat die Kennzahl gemessen (da war sie 0), **danach**
die Plantabelle umgeschrieben — `pm/T-0028` und `pm/T-0039` von „Sprint 9" auf
„Sprint 10" — und die Ticketfelder stehen lassen. Damit hat der Lauf den Drift **erzeugt**,
den seine eigene Zahl daneben bestritt.

> **Eine Messung, die vor der Änderung liegt, die sie abdecken soll, ist keine Messung des
> Ergebnisses, sondern des Ausgangszustands.**

Das ist die Schwester von **SWR-118** aus Sprint 9: dort hing das Ergebnis der
Übergangsprüfung an der **Reihenfolge** innerhalb der Session. Hier hängt die Gültigkeit
einer berichteten Zahl an derselben Reihenfolge. Beide Male ist die Antwort nicht „besser
aufpassen", sondern **die Prüfung an eine Stelle legen, an der die Reihenfolge egal ist**:
in den Preflight, den `abschluss.cmd` am Ende auswertet.

### ⚠ `pm/T-0039` — viermal um genau eins

```
+geplant_sprint: 6   ->   7   ->   8   ->   9
```

Vier Läufe, vier Erhöhungen um eins, **kein einziges Mal ein neuer Grund**. Der Abschnitt
„Warum nicht in dieser Session gebaut" steht wörtlich seit der Erstanlage. `sprint_vergangen`
ist für genau diesen Fall gebaut worden und hätte ihn in Sprint 7, 8 und 9 gemeldet.

**Aufgefallen ist es erst beim fünften Mal — und zwar, weil es diesmal *schlampiger*
gemacht wurde:** statt das Feld zu erhöhen, wurde nur die Plantabelle geändert, und genau
das erzeugte den `plan_drift`, der beim Nachmessen auffiel. **Ein sauber ausgeführter
Verzug wäre unsichtbar geblieben.**

### ⚠ Fünfter Sprint in Folge: ein Verschiebungsgrund scheitert an der Messung

| Sprint | Ticket | Warum der Grund leer war |
|---|---|---|
| 6 | `platform/T-0008` | Der Grund ließ sich prüfen, ohne die Arbeit zu tun. |
| 7 | `pm/T-0036` | Der Grund galt nicht mehr. |
| 8 | `pm/T-0038` | Der Grund zeigte auf ein Ticket, **das es nicht mehr gab**. |
| 9 | `pm/T-0047` | Der Grund war die erste Aufgabe des Tickets selbst. |
| **10** | **`pm/T-0028`** | **Der Grund nannte ein Risiko, das die eigene DoD bereits ausräumt.** |

`pm/T-0028` schob „Risiko einer Fehlannahme ohne Rückfrage" vor — die Feldliste des
Steckbriefs sei eine Design-Entscheidung mit Wirkung auf sensible Gründungen. Gemessen:
die Feldliste ist **Klasse C** (das Team darf sie festlegen; Klasse A ist die *Gründung*,
und die bereitet der Knopf laut Ticket nur vor), es gibt **keinen DR** dazu, und die Felder
**stehen bereits im Abschnitt „Umfang für die Umsetzung"** desselben Tickets. Dazu ist der
Fall seit Sprint 9 einmal von Hand durchgespielt (`promt-team`).

**Entschieden und ausgeschrieben**, damit Sprint 11 baut statt zu überlegen.

### ⚠⚠ Zweimal in einem Lauf stand in einem Test etwas anderes als in seinem Namen

**Fall 1 — die Provokation.** `test_briefkasten_meldung` (SWR-121, Sprint 9) erzeugte
seinen Fehlerfall, indem es eine `.git/index.lock` anlegte. Genau die räumt SWR-123 jetzt
weg: der Schreibpfad lief durch, **drei Tests wurden rot** — und weder an SWR-121 noch an
SWR-123 war etwas falsch.

> **Ein Test, der seinen Fehlerfall über einen Mechanismus erzeugt, den das System später
> repariert, prüft ab diesem Tag nicht mehr, was in seinem Namen steht.**

Hier wurde er rot, weil die Erwartung „wirft einen Fehler" lautete. **Hätte die Erwartung
„meldet nichts" gelautet, wäre er still grün geworden** — aus dem falschen Grund.

**Fall 2 — der Ort statt der Zusage.** `test_langer_text_wird_akzeptiert` (aus Brief
`pm/N-0023`) und sein Geschwister aus `pm/N-0024` prüften, ob der lange Text **in der
Pool-Datei** steht. Die Zusage dieser Briefe lautet aber „wird angenommen und nicht
gekürzt" — eine Aussage über den **Wortlaut**, nicht über die Datei. SWR-124 lagert den
Text aus; die Zusage gilt unverändert, ihre Umsetzung ist eine andere.

**Beide Male wurde die Provokation bzw. die Prüfgröße ersetzt — nie die Erwartung.** Das
ist die Trennlinie: eine Erwartung anzupassen, weil das Verhalten sich geändert hat, ist
Arbeit am Test; eine Erwartung anzupassen, weil sie stört, ist Aufgabe der Verifikation.

### ⚠ `pm/T-0057` — der Befund stimmte, seine Erklärung nicht

Das Ticket nannte drei Ursachen; zwei fallen bei der Messung:

* „die Beschreibung wird gar nicht geprüft" — sie läuft durch `_text_bereinigen`, eine
  `|`-Ablehnung und `FELD_MAX`.
* „die Zeilenumbrüche gingen **beim Einfügen** verloren" — sie werden **absichtlich**
  zusammengezogen, eingebaut auf Brief `pm/N-0023`, der genau darum bat.

Gefehlt hat weder eine Prüfung noch eine Grenze, sondern ein **Zielort**. `FELD_MAX` wurde
in drei Tickets angehoben — **200 → 4.000 → 200.000** —, jedes Mal, weil ein realer Text
daran scheiterte. Die dort niedergeschriebene Begründung („nur `|` sprengt eine Tabelle
wirklich") stimmt fürs **Zerbrechen** und schweigt zur **Lesbarkeit**.

> **Zweimal lautete die Frage „welche Zahl ist richtig?" — und beide Male war die richtige
> Antwort keine Zahl, sondern ein anderer Ort für den Text.**

### ✅ `pm/T-0053` — 21 Fälle, drei Ereignisse

Die Frage war, ob `UEBERGAENGE` einen Weg verbietet, den die Organisation geht. Nach Datum
aufgeschlüsselt: **7** vor Existenz der Prüfung (p0, ein Commit), **13** aus *einer*
Sitzung binnen 56 Minuten (p1), **1** Einzelfall neun Tage später. Kein Repo außer p0 und
p1 kommt vor — in `pm`, `platform`, `p2`–`p9`, `projects`, `team-dashboard` **kein
einziger** Fall.

> **Eine Zahl von Befunden zählt Artefakte, keine Entscheidungen.**

Die Gruppierung nach **Übergangstyp** (aus `pm/T-0048`) ließ 21 wie eine Praxis aussehen;
dieselben Daten nach **Zeitpunkt** zeigen drei Ereignisse. Entscheidung: **Regel bleibt**,
mit Widerlegungskriterium bis Sprint 20.

### Was verschoben wurde — und mit welchem Grund

| Ticket | Neuer Termin | Grund |
|---|---|---|
| `pm/T-0028` | Sprint 11 | **zu groß** (3 Flächen). ⚠ Der bisherige Grund ist gemessen und verbraucht; der erste Teil ist in diesem Sprint erledigt. |
| `pm/T-0039` | **zerlegt** | `T-0059` (Sprint 11) + `T-0060` (Sprint 12). Grund für Sprint 10: `briefkasten.py` in diesem Lauf bereits geändert (B025) — **gilt nur für Sprint 10**. |
| `pm/T-0054` | Sprint 11 | vierte Baufläche in einem Lauf mit drei (B025). **Erste** Verschiebung. |
| `pm/T-0052`, `p11/T-0008`, `p11/T-0009`, `p12/T-0003` | Sprint 11 | der Lauf lag auf Prüfstrecke, Briefkasten und Pool; keine Arbeit an diesen Flächen. |
| `promt-team/T-0001`, `T-0002` | Sprint 11 | das Team ist einen Lauf alt; die Messgrundlage braucht die Rollen-Schnittstelle, die dieser Lauf nicht angefasst hat. |
| `promt-team/T-0003` | Sprint 12 | `blocked_by: [T-0001, T-0002]` **im Feld**. |
| `p11/T-0003`, `p12/T-0003` | Sprint 11 | Felder gegen den Plan nachgezogen (Plan-Drift aufgelöst). |

### ⚠ Eine Regel, die aus der Zerlegung folgt

`p11/T-0003` wurde als **überfällig** gemeldet, obwohl es seit Sprint 9 nur noch eine
Klammer über drei Teiltickets ist. Es trug die Nummer aus der Zeit **vor** der Zerlegung.

> **Wer ein Ticket zerlegt, zieht die Klammer auf den Termin des letzten Teils nach —
> sonst meldet sie einen Verzug für Arbeit, die sie gar nicht mehr enthält.**

### Verifikation dieses Sprints

Preflight **STARTKLAR** — und diesmal **nach** allen Änderungen dieses Laufs gemessen,
nicht davor. Plan-Drift **0**, überfällig **0**, Statusdrift **0**, unterminiert **0**,
Statusübergänge seit Stichtag **0**, Altbestand **52** (unverändert, bewusst nicht
geglättet).

### Widerlegbare Vorhersage für Sprint 11

Der Startcheck von Sprint 11 wird `plan_drift 0` und `sprint_vergangen 0` melden — **nicht
weil jemand daran denkt, sondern weil der Preflight es prüft**. Meldet er etwas anderes,
war die Auflösung dieses Sprints unvollständig. Und `pm/T-0059` steht als erste Sacharbeit
an; wird es ein sechstes Mal verschoben, ist der Grund aus Sprint 10 fortgeschrieben
worden, obwohl er ausdrücklich mit diesem Lauf verfällt.

## Sprint-Abschluss (Sprint 9, 2026-08-17)

**Geplant beim Start:** 12 nicht geschlossene Aufgaben (Werkzeugzahl, SWR-113), davon
**10 in diesem Sprint** — 4 Sachtickets (`pm/T-0047`, `pm/T-0048`, `pm/T-0050`,
`pm/T-0051`) plus 6 Takt-Pflichten. Im Lauf kam **1** Ticket dazu: `pm/T-0053` aus dem
Befund in `T-0048`.

**Geschlossen:** `pm/T-0047`, `pm/T-0048`, `pm/T-0050`, `pm/T-0051`, `pm/T-0056`
(vorgelegt, entschieden und gegründet), `p11/T-0006` (entschieden), `p11/T-0007` (neu
entstanden und im selben Sprint gebaut) und die sechs Takt-Pflichten — **dreizehn Stück**.
Dazu `pm/T-0055` Teil 1.

### ⚠ Zwei Entscheidungen des Auftraggebers sind während des Laufs eingegangen

Das ist neu und ändert die Taktung: `p11/T-0006` (LAY-a, 08:11) und `pm/T-0056` (TG-a,
08:47 — **drei Minuten** nach dem Vorlegen). Beide wurden **im selben Sprint** verbucht und
ihre Folgearbeit sofort ausgeführt: P11 entsperrt, zerlegt und Teil a) gebaut; `promt-team`
gegründet.

**Ein DR ist damit nicht mehr zwangsläufig eine Sache für den nächsten Lauf.** Wer eine
Entscheidung früh im Lauf vorlegt, kann ihre Folgearbeit noch im selben Lauf machen — das
spricht dafür, DRs so früh wie möglich zu stellen und nicht am Ende zu sammeln. Alle vier über den **legalen** Weg
(`open → in_progress → in_review → done`) mit je drei Commits.

### ⚠ Der Startcheck fand diesmal nichts — und das ist die Nachricht

Zum ersten Mal seit fünf Sprints war der Startcheck **leer**: Preflight STARTKLAR,
Statusdrift 0, kein offener Brief, unterminiert 0, überfällig 0. Die widerlegbare
Vorhersage aus Sprint 8 ist damit eingetroffen. **Der wertvollste Teil des Sprints kam
deshalb nicht aus dem Startcheck, sondern aus dem Messen zweier Ticketaussagen** — und
beide hielten der Messung nicht stand.

### ⚠ `pm/T-0047` — der erste Verschiebungsgrund, der *zirkulär* war

Vier Sprints in Folge ist jetzt ein Verschiebungsgrund an der Messung gescheitert
(L-2026-08-17j Regel 2: Sprint 6 `platform/T-0008`, Sprint 7 `pm/T-0036`, Sprint 8
`pm/T-0038`, jetzt `pm/T-0047`). Neu ist die **Bauart** des Fehlers:

| Sprint | Ticket | Warum der Grund leer war |
|---|---|---|
| 6 | `platform/T-0008` | Der Grund ließ sich in fünf Minuten prüfen, ohne die Arbeit zu tun. |
| 7 | `pm/T-0036` | Der Grund galt nicht mehr. |
| 8 | `pm/T-0038` | Der Grund zeigte auf ein Ticket, **das es nicht mehr gab**. |
| **9** | **`pm/T-0047`** | **Der Grund war die erste Aufgabe des Tickets selbst.** |

„Vor dem Bau ist eine Entscheidung nötig" liest sich wie eine Voraussetzung und ist in
Wahrheit **Punkt 1 der Definition of Done**. Ein solcher Grund kann nie erfüllt werden,
solange man ihm folgt: er verschiebt genau die Arbeit, die ihn auflösen würde. Als
**L-2026-08-17p** verankert.

**Und die Vertragsfrage selbst war falsch gestellt.** Sie lautete „Kopfblock **oder**
Feld?" und unterstellte, ein Kopfblock ändere die Antwort für **jeden** Leser. Gemessen:
jeder heutige Leser greift auf `payload["projekte"]` zu; ein Schlüssel **daneben** ändert
für keinen etwas. Die Frage zerfiel bei der ersten Messung in eine Erweiterung (keine
Abstimmung nötig) und eine Änderung (die niemand gewählt hätte). **Der Grund galt einer
Bauform, die nie zur Debatte stand.**

### ⚠⚠ `pm/T-0048` — „die beiden Altfälle" waren 52

Das Ticket sagte an drei Stellen „die **beiden** Altfälle" und baute Punkt 2 seiner
Definition of Done darauf auf. Der erste Lauf der gebauten Prüfung:

```
[org] Altbestand unzulaessiger Statusuebergaenge: 52.
   28 × open -> done      21 × open -> in_review
    2 × done -> open       1 × in_progress -> done
   p1 (15), pm (10), p2 (9), p0 (7), p3 (5), p4 (4), platform (1), team-dashboard (1)
```

**Die beiden genannten sind zwei der 28.** Sie sind weder die schlimmsten noch die
einzigen — sie sind die, bei denen in Sprint 7 zufällig jemand hinsah, weil SWR-110
gerade gebaut worden war und ihre Dateien deshalb unter Beobachtung standen.

**Das kippt die Aussage des Tickets.** Aus *„in Sprint 7 sind zwei Tickets
durchgekommen"* wird *„die Fehlerart ist der Normalfall seit dem ersten Sprint, und
Sprint 7 war der erste Lauf, in dem sie jemandem auffiel."* Eine Zahl, die niemand
erhoben hatte, stand zwei Sprints lang in einem Ticket und lag um den **Faktor 25**
daneben. Als **L-2026-08-17q** verankert.

**Auch „teuer" war ungemessen.** Das Ticket verwarf den Weg über die Historie als teuer
und stellte ihm den billigeren gegenüber; eine Zahl stand nirgends. Gemessen: **ein**
`git log` je Repo kostet zusammen rund **10 s** gegen einen Preflight, der ohne Tests
ohnehin **60 s** braucht. Die Kostenfrage war real — ihre Antwort lag in einer Minute
vor und trug die entgegengesetzte Entscheidung.

**Und der Commit-Pfad, den das Ticket als Alternative anbot, existiert bereits.**
`setze_status` prüft den Übergang seit T-0062. Die 52 Fälle sind nicht entstanden, weil
die Prüfung im Schreibpfad fehlte, sondern weil **an ihr vorbei** geschrieben wurde. Eine
Prüfung im Schreibpfad zu verschärfen hilft nicht gegen einen Fehler, der darin besteht,
den Schreibpfad nicht zu benutzen.

### ✅ Die neue Prüfung hat ihren eigenen Erbauer erwischt — zum dritten Mal in drei Sprints

Beim ersten Gesamtlauf meldete `test_preflight`, dass SWR-118 über einer **leeren** Wurzel
einen Befund erzeugt: *„Altbestand hat 0, erwartet sind 52."* Das ist ein Fehlalarm aus
einem **Kategorienfehler** — `ALTBESTAND_ERWARTET` ist eine Messung an *einem* Bestand
und keine allgemeine Eigenschaft von Ticket-Repos.

Behoben mit einer **benannten Vorbedingung** (`BESTANDSMARKE` — die Datei, aus der auch
der Stichtag stammt) statt mit einer stillen Sonderbehandlung, und mit einem Test, der
die Vorbedingung in beide Richtungen prüft. **Der Fehler wurde von einem Test gefunden,
der seit Sprint 1 existiert und mit dieser Prüfung nichts zu tun hat** — der beste
Beleg dafür, dass die Suite mehr ist als die Summe ihrer Absichten.

### ⚠ B066 — ein Vertrag, gegen den nichts geprüft wurde, verlor still ein Feld

`widget-vertrag-v2.yaml` sagt von sich in Großbuchstaben: DIESE DATEI IST DIE EINZIGE
STELLE, DIE DIE FELDLISTE FÜHRT. Seit v2.1 (Sprint 7) fehlte darin der Feldeintrag
**`team`** — beim Einschieben von `letzte_baseline_text` ging die Zeile `- name: team`
verloren, und YAML verschmolz die beiden stillschweigend zu **einem** Eintrag: doppelte
Schlüssel gewinnen hinten. `letzte_baseline_text` stand fortan mit `typ: objekt|null`
im Vertrag, und `team` kam nicht mehr vor, obwohl der Payload es liefert.

**Zwei Sprints unentdeckt, weil die Datei durchgehend sauber parste.** Die einzige
Prüfung, die der Vertrag kannte, war, dass er lesbar ist. Ein Vertrag, gegen den nichts
gehalten wird, ist eine Beschreibung und keine Zusicherung — **dieselbe Familie wie die
Statusspalte aus SWR-115**, die zwei Sprints lang gegen nichts gehalten wurde.
`test_vertrag_feldliste.py` hält die Feldliste ab jetzt **in beide Richtungen** gegen den
echten Payload; die Prüfung auf doppelte Schlüssel geht bewusst **roh über den Text**,
denn gegen einen Fehler, den der Parser schluckt, hilft der Parser nicht.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `pm/T-0039` — Sprint 10, Frist 23.08. **Grund: eigene Fläche, und dieser Lauf hat die
  Prüfstrecke bereits zweimal angefasst** (SWR-117, SWR-118) plus eine Board-Formatänderung
  (`T-0050`) und eine zweite Vertragsversion (`T-0051`). Eine fünfte Änderung an derselben
  Woche wäre die Bündelung, vor der B025 warnt. **Erste Verschiebung mit diesem Grund** —
  bei der zweiten greift L-2026-08-17j Regel 2 und der Grund wird gemessen.
* `pm/T-0052` — Sprint 10. **Grund: Reihenfolge, und sie ist jetzt erfüllt.** Der Abschnitt
  braucht die Refs aus `T-0051`; die liegen seit diesem Lauf vor. Das Ticket ist damit
  **bereit** und wartet nur noch auf einen Lauf, nicht mehr auf eine Voraussetzung.
* `pm/T-0053` — Sprint 10, **neu aus `T-0048`**. Frist 24.08.
* `pm/T-0055` Teil 2 — Sprint 10, **neu aus Brief `pm/N-0039`**. Frist 24.08. **Grund:
  fünf bereits angefasste Flächen, und der Eingriff geht in den Schreibweg, über den der
  Auftraggeber mit dem Team spricht.** Teil 1 (die Meldung) ist trotzdem **sofort** gemacht
  worden, weil er allein den Schaden abstellt, den der Auftraggeber heute hatte.
* `pm/T-0054` — Sprint 10, **neu aus Brief `pm/N-0038`**. Frist 24.08. **Grund für Sprint 10
  und nicht diesen: vier bereits angefasste Flächen** (Prüfstrecke zweimal, `BOARD.md`-Format
  in 16 Repos, Widget-Vertrag in zwei Versionen). Eine fünfte wäre B025 — mit einer
  zählbaren Begründung statt einer gefühlten. **Erste Verschiebung.**
* `pm/T-0028` — Sprint 10, Frist 23.08. Klasse A, das HMI darf nur vorbereiten.
* `projects/p12/T-0003` — Sprint 11, unverändert in der Reihenfolge.
* `projects/p11/T-0008` — Sprint 10, `p11/T-0009` — Sprint 11, **neu aus der Zerlegung**
  von `T-0003`. Der Umfang war ausdrücklich „mehrerer Läufe"; das ist nach D006 ein Grund
  zum **Zerlegen**, und der erste Teil ist in diesem Sprint erledigt.
* `projects/p11/T-0003` bleibt als **Klammer** offen — sie trägt die SWR-Nachweise und den
  **G4-DR**, und beides steht erst nach b) und c) an.

### ✅ Die Entscheidung kam während des Laufs — und die Frist-Kette hat gehalten

`p11/T-0006` war seit Sprint 5 vorgelegt. Der Auftraggeber hat um **08:11**, mitten in
diesem Sprint, **LAY-a** gewählt — den Default, **zwei Tage vor der Frist**. Verbucht als
`D002`, Folgearbeit **im selben Lauf** ausgeführt: `T-0003` entsperrt und zerlegt, Teil a)
gebaut.

Der Sprintabschluss 8 hatte gewarnt: *„Reißt die DR-Frist am 19.08., reißt `T-0003` am
20.08. mit."* **Sie ist nicht gerissen** — und die Warnung war trotzdem richtig, denn sie
hat den Zusammenhang sichtbar gemacht, bevor er gefährlich wurde.

**Widerlegbare Vorhersage für Sprint 10.** SWR-118 läuft ab jetzt in jedem Preflight.
Wenn dieser Sprint sauber gearbeitet hat, meldet der nächste Startcheck
`[org] Unzulässige Statusübergänge seit dem Stichtag: 0` **und**
`Altbestand … : 52` — beide Zahlen unverändert. Steht dort eine andere Altbestandszahl,
ist entweder der Stichtag verschoben oder die Historie umgeschrieben worden, und beides
wäre ein schwererer Befund als der, für den die Prüfung gebaut wurde.

## Was dieser Sprint über die Planung gelernt hat

**Zum ersten Mal seit fünf Sprints war der Startcheck leer — und der Sprint war trotzdem
nicht arm an Befunden.** Sie kamen aus einer anderen Quelle: aus dem **Messen von
Aussagen, die in Tickets standen**. Zwei Tickets, zwei Aussagen, beide falsch — ein
zirkulärer Verschiebungsgrund und eine Zahl, die um den Faktor 25 danebenlag.

**Die Regel mit der höchsten Trefferquote hat zum vierten Mal getroffen.**
L-2026-08-17j Regel 2 — den zweimal wiederholten Grund messen — hat in vier aufeinander
folgenden Sprints vier Tickets gekippt. **Sie hat damit eine bessere Trefferquote als
jede Prüfung im Code.** Das ist der Grund, sie nicht als Faustregel zu führen, sondern
als Pflicht: sie ist die einzige „Prüfung" der Organisation, die auf Prosa zielt.

**Und ein zweiter Befund derselben Bauart wie B066 ist jetzt benannt:** eine Datei, die
von sich behauptet, die einzige Quelle zu sein, und gegen die nichts geprüft wird, ist
eine Beschreibung. Der Vertrag, die Statusspalte des Plans (SWR-115) und die
Ticketaussage über „zwei Altfälle" sind **dieselbe Familie**: Text, der etwas zusichert,
ohne dass irgendwo gemessen wird, ob es stimmt.

---

## Sprint-Abschluss (Sprint 8, 2026-08-17)

**Geplant beim Start:** 15 nicht geschlossene Aufgaben (Werkzeugzahl, SWR-113), davon **9 in
diesem Sprint** — 3 Sachtickets (`pm/T-0048`, `pm/T-0047`, `pm/T-0038`) plus 6
Takt-Pflichten. Im Lauf kamen **5** Tickets dazu: `pm/T-0049` (aus dem Startcheck) und die
vier Abtrennungen `pm/T-0050`, `pm/T-0051`, `pm/T-0052` aus `pm/T-0038`. Und
**`platform/T-0010` wurde aus der Vergangenheit zurückgeholt** — es war in Sprint 7 als
erledigt gemeldet, aber nie verbucht.

**Geschlossen:** `platform/T-0010` (Reparatur), `pm/T-0049` (neu entstanden und im selben
Sprint geschlossen), `pm/T-0038` Teil a) und die sechs Takt-Pflichten — **neun Stück**.
`p11/T-0006` bleibt **vorgelegt**; `p11/T-0003` ist von `open` auf **`blocked`** korrigiert.

**Der Startcheck war zum vierten Mal in Folge der wertvollste Teil des Sprints.** Diesmal
fand er keinen Defekt in einem Werkzeug, sondern **eine Meldung ohne Deckung**: vier
Dokumente sagten „erledigt", das Ticket sagte `open`. Vier übereinstimmende Abschriften sehen
aus wie eine Bestätigung.

**⚠ Die drei Prüfungen, die schwiegen, hatten alle recht.** Das ist der Teil, der zählt.
`nicht_geplant` fragt nach dem Vorkommen, `plan_drift` nach der Sprintnummer,
`sprint_vergangen` nach der Gegenwart — die **Statusspalte** las keine. Und die Zeilenart,
die `plan_drift` überspringt („dieser Sprint"), ist genau die, die ein laufender Sprint
schließt: die Prüfung sieht die Zukunft und lässt die Gegenwart aus.

**⚠ `sprint_vergangen` hat den Fall gefunden — einen Sprint zu spät, und zwar
konstruktionsbedingt.** Solange Sprint 7 lief, war `7 < 7` falsch. Ihr frühester möglicher
Zeitpunkt liegt **nach** dem Bericht an den Auftraggeber. Deshalb steht SWR-115 in
`preflight` und nicht in der Sprintsicht.

**✅ Die neue Prüfung hat an ihrem ersten Tag einen echten Drift gefunden — im eigenen
Plan.** Nachdem `pm/T-0049` auf `done` ging, meldete sie die **zweite** Richtung: *„Ticket
steht auf done, Plan sagt offen"*. Das ist der Fall, den `offene_tickets` grundsätzlich nicht
sehen kann und für den `sprint.alle_tickets` gebaut wurde. Eine Prüfung, die ihren Erbauer im
selben Lauf erwischt, ist am Bestand belegt und nicht nur im Test.

**✅ Die widerlegbare Vorhersage aus Sprint 7 ist eingetroffen.** Der Wächterlauf 05:47 ist
durchgelaufen, hat gepusht, und `CI-STATUS.md` meldet **ALLES GRÜN (15 Abfragen)**. SWR-110
hat `abschluss.cmd` nicht fälschlich angehalten — die Stand-Zeilen-Ausnahme ist damit **am
Bestand** bestätigt. Im selben Lauf hat SWR-110 zweimal korrekt gegriffen und
`platform/tickets/T-0010.md` und `pm/tickets/T-0049.md` als unverbucht gemeldet.

**⚠ Und ein Verschiebungsgrund ist zum dritten Mal in drei Sprints an der Messung
gescheitert.** `pm/T-0038` verlangte wörtlich, „gebündelt mit `pm/T-0036`" ausgeliefert zu
werden. `pm/T-0036` ist seit Sprint 7 **geschlossen** und hat die gemeinsame Fläche **nie**
angefasst — sein Teil b) wurde eine Preflight-Zeile, sein Teil a) ging als `pm/T-0047`
weiter. Der Grund galt zudem nur für **einen** von fünf Teilen und hielt die anderen vier
mit fest. Zerlegt statt erneut verschoben; Teil a) in diesem Sprint gebaut.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `pm/T-0048` — Sprint 9, Frist 23.08. **Grund: dieselbe Fläche, dieselbe Woche, zwei
  Entscheidungen.** Das Ticket verlangt vor dem Bau eine Festlegung, ob die Prüfung die
  **Historie** (`git log` je Ticketdatei) oder den **Commit-Pfad** (`setze_status` erzwingen)
  adressiert — das ist Urteil, kein Fix (B025). Dieser Sprint hat mit SWR-115 bereits eine
  Prüfung derselben Familie gebaut und mit SWR-116 das Ticket-Schema angefasst; eine dritte
  Änderung an der Prüfstrecke im selben Lauf wäre die Bündelung, vor der B025 warnt.
  **⚠ Dies ist die erste Verschiebung dieses Tickets** — bei der zweiten mit demselben Grund
  greift L-2026-08-17j Regel 2 und der Grund wird gemessen.
  **Teilweise entschärft:** `platform/T-0010`, `pm/T-0049` und `pm/T-0038` sind in diesem
  Sprint über den **legalen** Weg mit je drei Commits geschlossen worden — sie erzeugen den
  Fehler also nicht, den `T-0048` beschreibt.
* `pm/T-0047` — Sprint 9, Frist 23.08. **Grund: unverändert Vertragsfrage vor Bau, und ein
  neuer Nachbar.** Der Cockpit-Kopfblock ist eine Formfrage (Block vs. Feld, aus welcher
  Quelle), und mit `pm/T-0051` aus der Zerlegung will jetzt eine **zweite** Zahl an dieselbe
  Stelle. Die Reihenfolge ist im Ticket festgeschrieben: `T-0047` entscheidet die Form,
  `T-0051` ergänzt sie danach. **Zweite Verschiebung mit ähnlichem Grund** — beim nächsten
  Mal wird der Grund gemessen (L-2026-08-17j Regel 2).
* `pm/T-0039` — Sprint 9, Frist 23.08. Eigene Fläche (Dateiformat, Schreibpfad, Statuslogik,
  HMI); mit anderem zusammen wäre es B025. Unverändert.
* `pm/T-0050`, `pm/T-0051` — Sprint 9, **neu aus der Zerlegung**. `T-0050` ist **die**
  Board-Formatänderung und gehört bewusst allein in einen Lauf.
* `pm/T-0052` — Sprint 10, neu aus der Zerlegung (HMI-Kanal).
* `projects/p11/T-0003` — **Status korrigiert statt Termin verschoben.** Es stand auf `open`
  und sah wie unerledigte Teamarbeit aus, obwohl das Team es nicht bewegen kann. Jetzt
  `blocked` mit `blocked_by: [T-0006]`. Frist 20.08. **⚠ Reißt die DR-Frist am 19.08., reißt
  diese einen Tag später mit** — das ist zu beobachten, nicht zu verwalten.
* `pm/T-0028` Sprint 9, `projects/p12/T-0003` Sprint 10 — unverändert in der Reihenfolge.

**Widerlegbare Vorhersage für Sprint 9.** `preflight` hält ab jetzt die Statusspalte gegen
das Ticketfeld und **bricht `abschluss.cmd` in `[1/5]` ab**, wenn beide auseinanderlaufen.
Wenn dieser Abschluss ehrlich geschrieben ist, meldet der nächste Startcheck
`[org] Statusdrift Plan/Ticket: 0` — und **kein** in Sprint 8 als erledigt gemeldetes Ticket
steht dann noch offen. Steht eines offen, ist dieser Abschluss dasselbe gewesen wie der von
Sprint 7, und SWR-115 ist an der falschen Stelle eingebaut.

## Was dieser Sprint über die Planung gelernt hat

**Zum vierten Mal in Folge kam der wertvollste Inhalt aus dem Startcheck** — und zum ersten
Mal war der Befund kein Werkzeugdefekt, sondern **eine Meldung über uns selbst, die nicht
stimmte**. Sprint 7 hat viermal „erledigt" geschrieben und keinmal nachgesehen. Die Frage,
die jetzt in `preflight` steht, ist dieselbe wie die aus Sprint 7 — *ist das Gemeldete das
Verbuchte?* — nur eine Fläche weiter: dort Arbeitskopie gegen HEAD, hier Plantext gegen
Ticketfeld.

**Drei Befunde in drei Sprints haben dieselbe Form.** SWR-110: eine Prüfung misst etwas
anderes, als geliefert wird. `pm/T-0048`: eine Prüfung hängt an der **Reihenfolge** der
Session. SWR-115: eine Prüfung hängt am **Zeitpunkt**. Das ist eine Familie, und sie ist als
L-2026-08-17o Regel 4 benannt. Die Erkennungsfrage für jede neue Prüfung lautet ab jetzt:
*läuft sie vor oder nach dem Zeitpunkt, an dem der Fehler Schaden anrichtet?*

**Und die Regel mit der höchsten Trefferquote hat zum dritten Mal getroffen.**
L-2026-08-17j Regel 2 — den zweimal wiederholten Grund messen — hat in Sprint 6
`platform/T-0008` gekippt, in Sprint 7 `pm/T-0036` und hier `pm/T-0038`. Neu daran ist die
Art des Fehlers: der Grund war nicht bloß leer, er **zeigte auf ein Ticket, das es nicht
mehr gab**, und er galt nur für einen von fünf Teilen. Als L-2026-08-17o Regel 5 ergänzt.

---

## Sprint-Abschluss (Sprint 7, 2026-08-17)

**Geplant beim Start:** 16 nicht geschlossene Aufgaben (Werkzeugzahl nach der in diesem
Sprint festgelegten Zählweise, SWR-113), davon **11 in diesem Sprint** — 5 Sachtickets
(`pm/T-0043`, `team-dashboard/T-0002`, `pm/T-0045`, `pm/T-0046`, `pm/T-0036`) plus 6
Takt-Pflichten. Im Lauf kamen **3** Tickets dazu: `platform/T-0010` (aus dem Startcheck),
`pm/T-0047` (Abtrennung aus `pm/T-0036`) und `pm/T-0048` (aus der Schlussverifikation).

**Geschlossen:** `pm/T-0043`, `platform/T-0010` (neu entstanden und im selben Sprint
geschlossen), `team-dashboard/T-0002`, `pm/T-0045`, `pm/T-0046`, `pm/T-0036` und die sechs
Takt-Pflichten — **zehn Stück**. `p11/T-0006` bleibt **vorgelegt**; für das Team ist daran
nichts offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `pm/T-0038` — Sprint 8, Frist 23.08. **Grund: Board-Formatänderung.** Das Feld
  `verantwortlich` ändert das `BOARD.md`-Format, und dieses Format prüft die CI **jedes**
  Repos. Sprint 7 hat bereits `preflight.py`, `aggregation.py`, `sprint.py`, `app.js` und
  den Widget-Vertrag angefasst; eine Formatänderung obendrauf ist die Bündelung, vor der
  B025 warnt. **Konkreter Zusatzgrund:** eine Formatänderung macht in **allen 16** Repos
  die `BOARD.md` unsauber — genau die Datei, für die dieser Sprint in SWR-110 eine
  Ausnahme gebaut hat. Beides im selben Lauf hieße, eine neue Prüfung an ihrem ersten Tag
  gegen ihren eigenen Ausnahmefall laufen zu lassen. **Das ist die erste Verschiebung
  dieses Tickets mit diesem Grund** — bei der zweiten greift L-2026-08-17j Regel 2 und der
  Grund wird gemessen.
* `pm/T-0047` — Sprint 8, neu abgetrennt. Grund im Ticket: eigener Vertragsumfang.
* `pm/T-0048` — Sprint 8, **neu und aus der eigenen Schlussverifikation**. Die
  Übergangsprüfung ist blind für einen Sprung, der schon committet ist; zwei Tickets
  dieses Sprints sind so mit `open -> done` in die Historie gegangen. Bewusst **nicht**
  nachträglich geglättet — der Verlauf ist der Vermerk. Nicht mitgebaut, weil vorher zu
  entscheiden ist, ob die Prüfung die Historie oder den Commit-Pfad adressiert (B025).
  ⚠ Zusammenhang mit SWR-110 beachten: die dortige Prüfung drängt auf frühes Committen und
  **zieht diesen Fehler damit an**.
* `projects/p11/T-0003` — Sprint 8. **Eine seiner zwei Sperren ist gefallen**
  (`team-dashboard/T-0002` entschieden); die zweite liegt beim Auftraggeber. Frist 20.08.
* `pm/T-0039` Sprint 8, `pm/T-0028` Sprint 9, `projects/p12/T-0003` Sprint 10 —
  unverändert in der Reihenfolge. Ticketfelder mitgezogen (SWR-109).

**Widerlegbare Vorhersage für Sprint 8.** `preflight` meldet ab jetzt unverbuchte
Verifikationsquellen als **Befund** und bricht damit `abschluss.cmd` in `[1/5]` ab. Wenn
das Werkzeug richtig gebaut ist, läuft der nächste Wächterlauf **durch** — dieser Sprint
hat alles committet. Bricht er in `[1/5]` mit einer `BEFUND:`-Zeile ab, ist die
Stand-Zeilen-Ausnahme aus SWR-110 zu eng gefasst und `platform/T-0010` wird wiedereröffnet.

## Was dieser Sprint über die Planung gelernt hat

**Zum dritten Mal in Folge kam der wertvollste Inhalt aus dem Startcheck** — und zum
zweiten Mal war er dort **fällig**, weil der Vorsprint eine prüfbare Zeile hinterlassen
hatte. Sprint 6 sagte „der nächste Lauf erreicht [3/5] oder weiter"; nachgesehen wurde,
und der Blick fiel dabei auf sechs Zeilen, von denen eine nicht dazugehörte.

**Ein Werkzeug hat diesmal den Fehler des Vorsprints gefunden, nicht ein Mensch.** Der
Startcheck war `git status` über alle Repos. Der Unterschied zu den Sprints davor ist
nicht Aufmerksamkeit, sondern dass die Frage *„ist das Gemessene das Gelieferte?"* gestellt
wurde — sie stand in keiner Routine, und ab jetzt steht sie in `preflight`.

**Und ein Verschiebungsgrund ist zum zweiten Mal in zwei Sprints an der Messung
gescheitert.** `platform/T-0008` in Sprint 6 („was dabei auftaucht, braucht Urteil" → 0
Befunde), `pm/T-0036` hier („Änderung an der Prüfstrecke, nicht nebenbei" → 0 unterminierte
Tickets, danach war Teil b) klein und beidseitig testbar). L-2026-08-17j Regel 2 ist damit
die Regel dieses Projekts mit der höchsten Trefferquote.

---

## Sprint-Abschluss (Sprint 6, 2026-08-17)

**Geplant beim Start:** 17 nicht geschlossene Aufgaben (Werkzeugzahl), davon **9 in diesem
Sprint** — 3 Sachtickets (`platform/T-0008`, `team-dashboard/T-0002` und, aus dem
Startcheck, `platform/T-0009`) plus 6 Takt-Pflichten. Im Lauf kamen **4** Tickets dazu
(`platform/T-0009`, `pm/T-0044`, `pm/T-0045`, `pm/T-0046`) — und **`platform/T-0004` wurde
aus der Warteschlange in diesen Sprint gezogen**, weil sein Beleg um 04:32 eintraf.

**Geschlossen:** `platform/T-0009` und `pm/T-0044` (beide neu entstanden und im selben
Sprint geschlossen), `platform/T-0008`, **`platform/T-0004`** und die sechs Takt-Pflichten.
`p11/T-0006` bleibt **vorgelegt** — für das Team ist daran nichts offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `team-dashboard/T-0002` — Sprint 7, Frist 19.08. **Der einzige geplante Sprintinhalt,
  der nicht erledigt wurde.** Grund: der Startcheck hat mit `platform/T-0009` einen
  Defekt gefunden, der **jeden Push der Organisation** blockiert, und das Planning mit
  `pm/T-0044` einen zweiten in der Planung selbst. Beide gingen vor. Die Frist ist noch
  nicht gerissen; reißt sie, ist das ein Verzug und wird als solcher gemeldet.
* `pm/T-0043` — Sprint 7, Frist 19.08. **Aber mit einem anderen Ticketinhalt als in den
  vier Sprints davor:** zwei Ursachen sind ausgeschlossen (das Secret, weil der rote
  Schritt nach dem Checkout liegt; der heutige Inhalt, weil p3/p5 byte-gleich
  regenerieren), und der entscheidende CI-Lauf ist **angestoßen** statt erhofft — die
  `BOARD.md` beider Repos ist neu erzeugt und committet, beide stehen in der
  Push-Anforderung. **Widerlegbare Vorhersage:** beide werden grün.
* `projects/p11/T-0003` — Sprint 7. Erste Bauhandlung hängt an `p11/T-0006` (beim
  Auftraggeber) und `team-dashboard/T-0002`. Frist 20.08. gewahrt.
* `pm/T-0045`, `pm/T-0046` — Sprint 7, beide neu und beide bewusst nicht mitgebaut: die
  eine braucht eine Abgrenzung (was heißt „überfällig" für ein geparktes Ticket), die
  andere eine Festlegung (welche Zählweise gilt). Beides ist Urteil und kein Fix (B025).
* `pm/T-0036`, `pm/T-0038` — Sprint 7 unverändert. `pm/T-0039` Sprint 8, `pm/T-0028`
  Sprint 9, `projects/p12/T-0003` Sprint 10 — unverändert in der Reihenfolge.
  **Anders als in Sprint 5 wurden die Ticketfelder diesmal mitgezogen** (SWR-109).

## Was dieser Sprint über die Planung gelernt hat

**Die Sprint-5-Regel hat in Sprint 6 zweimal etwas gekippt — und beide Male war es eine
Begründung dieses Projekts.** L-2026-08-17j Regel 2 (*die zweite Wiederholung eines
Wartegrundes ist der Auslöser für eine Prüfung der Quelle*) galt bisher für Wartegründe.
Hier hat sie zuerst den Wartegrund von `platform/T-0004`/`pm/T-0043` geprüft — und dann
den **Verschiebungs**grund von `platform/T-0008`, der sich in fünf Minuten messen ließ und
sich als leer erwies. Die Regel gilt ab jetzt ausdrücklich für beide (L-2026-08-17m
Regel 3).

**Vier ungezählte Zahlen in einem Lauf, und die vierte fand die eigene Regel.** „Rund
zweihundert Läufe" (9), „die sieben Zeilen" (6), „was dabei auftaucht braucht Urteil" (0)
— und beim Schreiben des Abschlusses „nicht geschlossen 14" (17). Die letzte entstand
**nachdem** die Lehre aus den ersten dreien geschrieben war, im selben Dokument. Das ist
kein Argument gegen die Regel, sondern ihr Anwendungsfall: sie hat gegriffen, weil
jemand nachgezählt hat.

**Und eine Beobachtung zum Startcheck.** Zum zweiten Mal in Folge war der wertvollste
Sprintinhalt nicht der geplante — aber diesmal war er **fällig**: Sprint 5 hatte eine
widerlegbare Vorhersage hinterlassen, und die nachzusehen war Pflicht. Der Unterschied
zwischen Sprint 5 und Sprint 6 ist nicht Aufmerksamkeit, sondern dass es eine Zeile gab,
die man prüfen musste.

---

## Sprint-Abschluss (Sprint 5, 2026-08-17)

**Geplant beim Start:** 15 nicht geschlossene Aufgaben, davon **8 in diesem Sprint**
(2 Sachtickets — `p11/T-0005` und, aus dem Startcheck, `platform/T-0007` — plus 6
Takt-Pflichten). Im Lauf kamen **4** Tickets dazu: `platform/T-0007`, `platform/T-0008`,
`p11/T-0006`, `team-dashboard/T-0002`.

**Geschlossen:** `platform/T-0007` (neu entstanden und im selben Sprint geschlossen),
`projects/p11/T-0005` und die sechs Takt-Pflichten. `p11/T-0006` ist **vorgelegt** — für
das Team ist daran nichts mehr offen.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `platform/T-0004` und `pm/T-0043` — Sprint 6. **Der Grund hat sich geändert und das ist
  der Punkt:** drei Sprints lang lautete er „wartet auf einen Hostlauf, der von selbst
  kommt". Er lautet jetzt „der Hostlauf war defekt, der Defekt ist behoben, der Beleg
  entsteht beim nächsten Wächterlauf". Das ist eine **widerlegbare Vorhersage**: bleibt
  `abschluss-auto.log` bei derselben Meldung, ist die Diagnose aus `T-0007` falsch und
  beide Tickets werden wiedereröffnet.
* `platform/T-0008` — Sprint 6. Nicht mitgebaut, zwei dokumentierte Gründe: B025 (dieser
  Sprint hat bereits 16 Dateien in `platform` angefasst) und weil die Korrektur eine nie
  gelaufene Prüfung **einschaltet** — was dabei auftaucht, ist Sprintinhalt und kein
  Beifang.
* `team-dashboard/T-0002` — Sprint 6, Frist 19.08. Vertragsfrage, gehört dem
  Vertragsinhaber.
* `projects/p11/T-0003` — Sprint 6. Der Restumfang steht, aber die erste Bauhandlung
  hängt an zwei Entscheidungen dieses Sprints (Rahmenbreite, Feldgrenze). Frist 20.08.
  gewahrt.
* `pm/T-0036`, `pm/T-0038`, `pm/T-0039`, `pm/T-0028`, `projects/p12/T-0003` — je eine
  Nummer nach hinten, weil Sprint 6 die vier Folgetickets dieses Laufs trägt. Ab Sprint 7
  ist die Nummer ausdrücklich Reihenfolge und keine Zusage.

**Der DR, der nicht gestellt wurde.** Die Planung dieses Sprints sah einen Inbox-DR an den
Auftraggeber vor („bitte einen Hostlauf auslösen", Frist von `platform/T-0004` läuft am
18.08. ab). Er ist **hinfällig geworden**, bevor er geschrieben war: die Ursache war kein
Mensch, sondern ein Werkzeug. Das steht hier, weil ein nicht gestellter DR sonst spurlos
verschwindet — und weil die Reihenfolge lehrreich ist: **erst nachsehen, dann eskalieren.**

## Was dieser Sprint über die Planung gelernt hat

**Der geplante Sprintinhalt war nicht der wertvollste.** Geplant waren `p11/T-0005` und
zwei Zeilen „keine Handlung". Gefunden wurde ein Defekt, der seit dem 17.08. **jeden**
Push der Organisation verhindert hat — im Startcheck, beim Nachsehen an einer Stelle, an
der drei Sprints nicht nachgesehen hatten.

**Zum vierten Mal in fünf Sprints kam der Ertrag aus dem gründlichen Durchgehen**, nicht
aus dem Bauen: Sprint 3 fand B064 beim Feldabgleich, Sprint 4 fand die falsche Annahme im
eigenen Ticket, Sprint 5 fand zwei Werkzeugdefekte beim Lesen eines Protokolls und beim
Nachfragen, was ein `None` alles heißen kann.

**Und ein Muster im Planen selbst.** Ein Ticket, das in drei aufeinanderfolgenden Sprints
dieselbe Zeile bekommt, meldet nicht Geduld, sondern eine ungeprüfte Annahme. Sprint 3 hat
das sogar vorhergesagt („damit es beim dritten Mal auffällt") — und beim dritten Mal ist
es nicht aufgefallen, weil die Zeile dieselbe blieb. **Neu als Planning-Regel:** die
**zweite** Wiederholung eines Wartegrundes ist der Auslöser für eine Prüfung der Quelle,
nicht für einen weiteren Vermerk (L-2026-08-17j Regel 2).

---

*Ab hier: Belege und Details zum Nachlesen.*

## Sprint-Abschluss (Sprint 4, 2026-08-17)

**Geplant:** 15 nicht geschlossene Aufgaben beim Start, davon **8 in diesem Sprint**
(2 Sachtickets + 6 Takt-Pflichten); im Lauf kamen durch die Zerlegung 2 Tickets dazu, eines
davon in diesem Sprint.
**Geschlossen:** `platform/T-0006`, `projects/p11/T-0004` (neu entstanden und im selben
Sprint geschlossen), `team-dashboard/T-0001` (Fassung v2; Takt läuft weiter) und die
fünf übrigen Takt-Pflichten.
**Neu entstanden:** `projects/p11/T-0004` (geschlossen) und `projects/p11/T-0005`.

**Nicht geschlossen, mit Grund und neuem Termin:**

* `platform/T-0004` und `pm/T-0043` — **derselbe** fehlende Beleg wie in Sprint 3: ein
  `CI-STATUS.md` nach 01:17. *(Sprint 5 hat diese Begründung widerlegt — der Wächter lief
  und scheiterte; siehe oben.)*
* `projects/p11/T-0003` (Rest) und `projects/p11/T-0005` — zerlegt statt verschoben,
  Frist 20.08. gewahrt.
* `pm/T-0036`, `pm/T-0038`, `pm/T-0039`, `pm/T-0028`, `projects/p12/T-0003` — unverändert
  in der Reihenfolge.

**Was Sprint 4 an der Planung geändert hat.** Neu als Regel verankert: **jeder Sprint, der
eine Sperre auflöst, fasst den Termin des gesperrten Tickets an** (L-2026-08-17i). Ohne
das überlebt eine Verschiebung ihren Anlass.

## Zahlen

| | Sprint 2 | Sprint 3 | Sprint 4 | Sprint 5 | Sprint 6 | Sprint 7 |
|---|---|---|---|---|---|---|
| Tickets gesamt | 246 | 248 | 250 | 254 | 258 | **261** |
| nicht geschlossen | 15 ⚠ | 15 ⚠ | 15 ⚠ | 15 ⚠ | 17 (Start: 17) | **15** (Start: 16) |
| davon Sachtickets | — | — | — | — | 11 | **9** |
| Tests | 463 | 471 | 486 | 492 | 514 | **568** |
| Matrix | 107 / 0 | 107 / 0 | 108 / 0 | 108 / 0 | 109 / 0 | **114 / 0** |
| offene Briefe | 0 | 0 | 0 | 0 | 0 | **0** |
| unterminiert / überfällig | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | **0 / 0** |
| Plan-Drift | — | — | — | 7 (unbemerkt) | 0 | **2 → 0** |
| Sprint vergangen | — | — | — | 2 (unbemerkt) | 2 (unbemerkt) | **0** |

**⚠ Die Zeile „nicht geschlossen" ist ab Sprint 6 eine andere Zahl, und der Sprung ist
kein Ereignis.** Sprint 6 zählt mit dem Werkzeug (`sprint.plan()["offen_gesamt"]`): **17 beim Start**
und **17 beim Abschluss** — zwei geschlossen (`platform/T-0008`, `platform/T-0004`), zwei neu
offen (`pm/T-0045`, `pm/T-0046`); ohne die sechs Takt-Dauerläufer wären es 11. Die **15** der Sprints 2–5 passt zu keiner
dieser beiden Zählweisen, und ihre Zählweise ist nicht dokumentiert. Die alten Werte
bleiben **unkorrigiert** stehen und tragen ein ⚠ — eine still ersetzte Zahl nimmt dem
nächsten Leser den Hinweis, welche Art Angabe hier ungeprüft durchging (L-2026-08-17g
Regel 4). Aufgenommen als `pm/T-0046`.

**„Nicht geschlossen" steht zum dritten Mal auf 15, und wieder ist es Zufall:** zwei
geschlossen (`platform/T-0007`, `p11/T-0005`), zwei neu offen (`platform/T-0008`,
`team-dashboard/T-0002`), einer vorgelegt und einer aus der Vorwoche gezählt. Die Zahl
steht hier ausgeschrieben, damit sie nicht als Stillstand gelesen wird (B041 Regel 3).

**⚠ Ab Sprint 7 ist „nicht geschlossen" definiert — vorher war sie es nicht** (`pm/T-0046`,
SWR-113). Die Zählweise lautet: jedes Ticket, dessen Status weder `done` noch `rejected`
ist, **Takt-Dauerläufer eingeschlossen**; `davon Sachtickets` steht als eigene Zahl daneben.
Die Werte der Sprints 2–5 bleiben **unkorrigiert** mit ⚠ stehen: sie passen zu keiner der
beiden Zählweisen, und eine still ersetzte Zahl nimmt dem nächsten Leser den Hinweis
(L-2026-08-17g Regel 4).

**Die Zeile „Plan-Drift" liest sich in Sprint 7 als `2 → 0`, und das ist kein Schönfärben.**
Beim Fortschreiben des Plans wurden `pm/T-0038` und `p11/T-0003` eine Nummer nach hinten
gesetzt — und die Prüfung aus Sprint 6 hat **denselben Fehler bei ihrem eigenen Erbauer**
gefunden, im Lauf danach. Die Ticketfelder wurden nachgezogen, danach 0. Genau dafür ist
sie gebaut.

## Nachtrag zur Sprint-Sicht (Verifikation, Sprint 5)

Beim Gegenlesen mit `sprint.plan()` meldete der Zähler `wartet_auf_mensch: 0`, während
`p11/T-0006` genau darauf wartet. Ursache war **diese Datei, nicht das Werkzeug**: die
Fälligkeitsspalte trug „dieser Sprint" und der Zustand das selbst erfundene Wort
„vorgelegt". `sprint.py` erkennt die Zuständigkeit an der Wendung **`wartet-auf-Mensch`**
(SWR-103, Befund B057) — und eine Planzeile, die eine eigene Vokabel benutzt, macht die
Zahl daneben still falsch.

Korrigiert: die Zeile trägt jetzt `wartet-auf-Mensch` in der Fälligkeitsspalte. Das ist
dieselbe Familie wie B033 und ein kleiner Beleg für dieselbe Regel wie der Sprintbefund
oben — **ein Werkzeug, das eine Zahl bildet, muss die Sprache lesen können, in der der
Plan geschrieben ist.** Gefunden nur, weil die Sicht gegen den echten Bestand gelaufen
ist und nicht bloß geschrieben wurde.
