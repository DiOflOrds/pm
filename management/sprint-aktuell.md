# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 14** (2026-08-17, Start 13:31, Kennung
   `2026-08-17T1330-cowork-s14`).
2. **⚠⚠ ZWEI Läufe halten diesen Sprint gleichzeitig — und diesmal haben BEIDE
   geschrieben.** Der eine baute `platform/T-0015` (Git-Schreibweg, **SWR-134**), der andere
   `p11/T-0010` (Dashboard-Endpunkt, **SWR-135**) und `pm/T-0068`. Am 11:05 hat der zweite
   Lauf noch verzichtet; hier ist der Fall eingetreten, vor dem `platform/T-0013` warnt.
3. **⚠⚠ Die Kollision ist eingetreten — bei der SWR-Nummer, nicht bei der Ticket-ID.**
   Beide Läufe nannten ihre Anforderung **`SWR-134`**. Entdeckt wurde es **nicht von einer
   Prüfung**, sondern beim Lesen des fremden Commits.
   > **Eine Kollisionsregel schützt die Kennungen, die sie nennt — und keine anderen.**

   Die Regel vom 2026-08-16 verlangt die Prüfung der nächsten freien **Ticket-ID** gegen
   HEAD; für `SWR-xxx`, `D0xx`, `N-xxxx`, `L-…`, `ADR-…` gab es sie nicht. Aufgelöst: der
   **committete** SWR-134 gewinnt, das Dashboard wurde auf **SWR-135** umgenummert.
   Verankert als `L-2026-08-17ae`.
4. **⚠ Und die Prüfung wäre auch mit Regel wirkungslos gewesen.** Der Nebenlauf hat die 134
   *unmittelbar vor* seinem Commit gegen HEAD geprüft. Gegen einen bewegten HEAD ist das ein
   Wettlauf. Die Reparatur heißt `platform/T-0013` (Sprintregister mit **Ende**), nicht
   „gründlicher prüfen".
5. **✅ Der Auftraggeber hat die Messung geliefert, die dem Team fehlte** — zwei Aufnahmen
   seines 4K-Bildschirms (`pm/T-0068`, verbucht). Ergebnis: **3 Projektkacheln** ohne
   Scrollen sichtbar, links und rechts je rund ein Fünftel der Breite **leer**.
6. **⚠⚠ Die Messung hat die Annahme hinter `pm/T-0066` widerlegt.** Wir hatten die *Menge*
   der Kacheln für die Ursache des Scrollens gehalten und deshalb das Falten gebaut
   (`pm/T-0067`, SWR-133). Die Ursache ist das **Layout**: eine Kachel pro Zeile in einer
   62rem-Spalte. Dazu die Sprint-Plan-Tabelle, die mit ~25 Zeilen **über** den Gruppen steht.
   > **Wir haben das Richtige gebaut und die falsche Ursache behandelt.** Beides gleichzeitig
   > wahr. Das Falten bleibt richtig — es war nur nicht die Antwort auf seine Frage.
7. **✅ `p11/T-0008` zerlegt — vierte Berührung, Naht lag seit Sprint 12 bereit.** Neu:
   `p11/T-0010` (Endpunkt, lesend, **erledigt**) und `p11/T-0011` (Konfiguration,
   schreibend, Sprint 15).
8. **✅ Zwei Festlegungen aus Sprint 9 sind nach fünf Sprints eingelöst** — DR `p11/T-0006`
   (LAY-a, entschieden 2026-08-17 08:11) und `ADR-P11-002`. Das Dashboard verlässt den
   62rem-Korridor, **und die Ausnahme sitzt an der Ansicht**, nicht am Korridor.
   ⚠ Fünfte Gestalt der SWR-131-Familie: **eine Entscheidung, die vorlag und nicht wirkte** —
   diesmal nicht, weil niemand sie las, sondern weil ihr Ticket viermal verschoben wurde.
9. **⚠ SWR-135 hat einen Altbestand gefunden, den niemand gesucht hat.** Die Prüfung, dass
   die neue Ansicht die Drei-Zustände-Regel aus `regeln.js` liest, wurde rot — an **drei
   Inline-Kopien in `cockpitKarte`**. Alle drei sind **sachlich richtig**; das ist der Punkt.
   Aufgenommen als `platform/T-0016`, **benannt und bei 3 eingefroren** statt geglättet —
   und ausdrücklich **nicht** mitmigriert, weil `/api/cockpit` kein `zustand`-Feld führt und
   eine zweite Herleitung in JavaScript ein *neuer* B033-Fall wäre.
10. **826 Python-Tests, 2 rot** (beide aus Sprint 13, unverändert und benannt), **40
    JS-Tests grün** (von 29), Matrix **135 SWRs / 0 Lücken**.

## Sprint-Plan

*Sprint 14 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. **Fest
geplant** ist Sprint 15; ab Sprint 16 ist die Nummer eine Reihenfolge, keine Zusage.*

⚠ **Diese Tabelle bildet die Arbeit BEIDER Läufe ab**, nicht nur die eines. Der Nebenlauf
hat `platform/T-0015` gebaut; das steht hier, weil ein Plan, der die Hälfte der Wahrheit
zeigt, schlechter ist als keiner.

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| pm/T-0068 | pl | dieser Sprint | **erledigt** | ✅ **Der Auftraggeber hat gemessen.** 3 Kacheln sichtbar, ein Fünftel der Breite je Seite leer. ⚠ Widerlegt die Annahme hinter `pm/T-0066`: das Scrollen kam vom **Layout**. Zahlen stehen an **einer** Stelle, `p11` zitiert von dort (B033). |
| projects/p11/T-0010 | dev | dieser Sprint | **erledigt** | **SWR-135.** `/api/dashboard` **ausschließlich** auf `cockpit_alle` — der Test ersetzt die Quelle durch eine Attrappe und verlangt, dass **nichts** übrig bleibt. Drei Zustände je Feld, `nicht_geliefert` auch **sichtbar** anders als `0`. Kacheln als Raster, Korridor-Ausnahme an der Ansicht. 21 Python-, 12 JS-Zusicherungen. |
| projects/p11/T-0008 | dev | Sprint 15 | **zerlegt** | ⚠ **Vierte Berührung, Naht geschnitten** statt ein fünftes Mal angekündigt. Klammer trägt den Termin des letzten Teils. DoD 3 (die Messung) ist über `pm/T-0068` beantwortet. |
| platform/T-0015 | cm | dieser Sprint | **in_review** (Nebenlauf) | **SWR-134**, gebaut vom parallelen Lauf: **ein** Schreibweg nach Git, gehalten von einem Zähltest über den Syntaxbaum. ⚠ Dessen eigene Messung hat die Ursachenaussage **meines** Tickets widerlegt: der `rename`-Rückfall existierte seit `pm/T-0023`, der Befund war die **Reichweite** (7 von 8 Commit-Stellen ohne Räumung). |
| platform/T-0016 | cm | Sprint 15 | offen | **Neu, Nebenbefund von SWR-135.** Drei Inline-Kopien der Vertragsregel in `cockpitKarte`. ⚠ **Zuerst die Vertragsfrage** (trägt der Cockpit-Payload künftig den Zustand? Eigentümer `team-dashboard`, B066, Versions-Bump), **dann** Code. Bis dahin bei 3 eingefroren. |
| projects/p11/T-0011 | dev | Sprint 15 | offen | Zweiter Teil von `T-0008`, `blocked_by: [T-0010]` — ab jetzt **erfüllt**. ⚠ Persistenz hier ist das **Gegenteil** von SWR-133 (Faltzustand bewusst flüchtig); der Unterschied ist im Ticket zu begründen, nicht zu behaupten. |
| platform/T-0013 | cm | dieser Sprint | offen | ⚠⚠ **Dringlichkeit gemessen, nicht vermutet:** dieser Sprint ist der Fall, vor dem das Ticket warnt, **und die Kollision ist eingetreten**. DoD in Sprint 13 korrigiert (Kriterium `ende`, nicht die Uhr). Nach `L-2026-08-17ae` zusätzlich: die Prüfung gilt für **alle** fortlaufenden Kennungen. |
| pm/T-0052 | pl | dieser Sprint | offen | ⚠ **5. Verschiebung, wenn dieser Lauf sie nicht anfasst.** Naht liegt seit Sprint 12 bereit. |
| projects/p11/T-0009 | dev | Sprint 15 | offen | **4. Verschiebung.** Sachlich hinter `T-0008`/`T-0010`. ⚠ Naht benannt: Deep-Link-Detailseiten / Mail-Widget hinter dem PIN-Leser — bei der nächsten Berührung schneiden. |
| projects/p11/T-0003 | pl | Sprint 15 | offen | **Klammer** über `T-0007`–`T-0011`, nachgezogen auf den letzten Teil. |
| pm/T-0066 | pl | Sprint 15 | **zerlegt** | **Klammer** über `T-0067` (erledigt) und `T-0068` (erledigt). ⚠ Beide Teile sind fertig — die Klammer kann in Sprint 15 geschlossen werden, **sobald** entschieden ist, ob aus der widerlegten Ursache ein neuer CR folgt (DoD 3 des Tickets: *„erst wenn die Zahlen zeigen, dass das Falten nicht reicht"* — sie zeigen es). |
| pm/T-0061 | cm | Sprint 15 | offen | **2. Verschiebung.** Messen, ob `sprint_widerspruch` je einen möglichen Fall hatte. |
| pm/T-0063 | chg | Sprint 15 | offen | **2. Verschiebung.** Charter + Gründungs-DR — ⚠ Team-Gründung ist **Klasse A**, Ergebnis ist eine Vorlage an den Menschen. |
| pm/T-0028 | chg | Sprint 15 | **zerlegt** | **Klammer**, Termin des letzten Teils (`T-0063`). |
| pm/T-0054 | chg | Sprint 15 | **zerlegt** | **Klammer** über `T-0064` (erledigt) / `T-0065`. |
| pm/T-0065 | chg | Sprint 15 | offen | Knopf setzt `geplant_sprint`. `blocked_by: [T-0064]` seit Sprint 13 **erfüllt**. |
| projects/p12/T-0005 | pl | Sprint 15 | offen | **2. Verschiebung.** ADR-Delta + Vollständigkeitsnachweis. |
| projects/p12/T-0006 | pl | Sprint 15 | offen | `blocked_by: [T-0005]`. |
| projects/p12/T-0003 | pl | Sprint 15 | **zerlegt** | **Klammer**, Termin des letzten Teils. |
| promt-team/T-0001 | dev | Sprint 15 | offen | ⚠ **5. Verschiebung.** Der Auftraggeber wartet (`promt-team/N-0001`). Naht benannt: (a) erheben, (b) auswerten. **Kandidat Nr. 1 für Sprint 15.** |
| promt-team/T-0002 | test | Sprint 15 | offen | **4. Verschiebung → Zerlegung fällig.** Naht: (a) Goldset-Format, (b) Fälle je Rolle. |
| promt-team/T-0003 | dev | Sprint 16 | blocked | `blocked_by` T-0001/T-0002 — nachgezogen, damit es nicht auf demselben Sprint wie seine Blocker steht. |
| pm/T-0001 | pl | jeder Sprint | geplant | Takt: Session-Agenda. |
| pm/T-0002 | pl | jeder Sprint | **erfüllt** | Takt: Briefkasten **zweimal** geprüft (Start und Abschluss), beide Male 0 offen. |
| pm/T-0003 | coach | jeder Sprint | **erfüllt** | Takt: `L-2026-08-17ae` sofort verankert. |
| platform/T-0001 | cm | jeder Sprint | geplant | Takt: Preflight, Tests, Matrix, JS-Strecke. |
| team-mail/T-0001 | dev | jeder Sprint | geplant | Takt: Digest — fällig ab IMAP-Einrichtung, die aussteht. |
| team-dashboard/T-0001 | pl | jeder Sprint | **erfüllt** | Takt: Widget-Vertrag — ⚠ **geprüft, nicht angenommen**: SWR-135 fügt **kein** Feld hinzu, ein Test hält `KACHEL_FELDER` gegen die Vertragsdatei. Vertrag bleibt v2.4. |

## Sprint-Abschluss (Sprint 14, 2026-08-17 — Stand dieses Laufs)

**Geschlossen:** `pm/T-0068`, `projects/p11/T-0010`, Zerlegung `p11/T-0008`, plus drei
Takt-Pflichten. Vom **Nebenlauf**: `platform/T-0015` (in_review).

**Im Lauf dazugekommen:** `projects/p11/T-0010`, `p11/T-0011`, `platform/T-0016`.

**Verifikation:** **826 Python-Tests** (2 rot, beide aus Sprint 13 — unverändert, benannt,
nicht geglättet), **40 JS-Tests** grün, Matrix **135 SWRs / 0 Lücken**, Briefkasten 0 offen
(zweimal geprüft), entschiedene unverbuchte DRs **0**.

⚠ **Der Lauf ist nicht startklar**, und der Grund ist unverändert der aus Sprint 13: zwei
unzulässige Statusübergänge (`platform/T-0014` `done → in_review`, `pm/T-0064`
`open → in_review`). **Dieser Lauf hat keinen neuen erzeugt** — alle Übergänge sind einzeln
committet. Die Regel aus `L-2026-08-17ad` hat gehalten.

### ⚠⚠ Der offene Punkt, der bleibt: zwei Läufe im selben Takt

Sprint 13 hat `platform/T-0013` mit gemessener DoD verschoben. Sprint 14 hat den Schaden
**erlebt**: eine doppelt vergebene Anforderungsnummer, gefunden durch Zufall beim Lesen
eines fremden Commits. Es ist gut ausgegangen, weil beide Läufe verschiedene Dateien
angefasst haben — das war **Glück, keine Vorkehrung**.

`platform/T-0013` ist damit das dringlichste offene Ticket der Organisation. Nicht weil es
neu ist, sondern weil sein Schadensfall zum zweiten Mal eingetreten ist und beim zweiten Mal
Spuren hinterlassen hat.
