# Sprint aktuell — Genesis-Gesamtsprint (Workflow-Sicht des PM, pm/D006)

## Das Wichtigste

1. **Wir sind in Sprint 13** (2026-08-17, Start 12:10, Kennung
   `2026-08-17T1210-cowork-s13`). Der Zähler steht in `pm/management/sprints.jsonl`.
2. **⚠⚠ Der Startcheck dieses Laufs hat einen Fehler von Sprint 12 gefunden: wir haben den
   Auftraggeber um eine Antwort gebeten, die er zwölf Minuten zuvor gegeben hatte.** Der DR
   `projects/p12/T-0007` (Node) wurde **11:48:25** über die Inbox mit `B-node-optional`
   entschieden und committet. Danach schrieb derselbe Sprint 12 drei Berichte — Sprintplan
   (11:50), Agenda (~12:00), Projektstatus (12:03) — die alle sagen, die Frage liege noch
   beim Menschen, Frist 24.08.
   > **Eine Entscheidung im Fließtext ist für jede Prüfung unsichtbar.**
3. **⚠ Die Ursache sind zwei Wahrheiten über ein Wort.** `inbox` liest „entschieden" am
   **Rumpfmarker** (`ENTSCHIEDEN`, SWR-039); `board.wartet_auf_mensch`, `aggregation` und
   der Preflight lesen ihn am **Status**. `inbox.entscheide` fasst `status` nie an. Der
   Docstring von `aggregation.wartet_auf_mensch` sagt seit SWR-120 wörtlich *„Ein
   entschiedener DR wartet auf niemanden"* — der Satz war **richtig und unwirksam**.
   Aufgenommen als **`platform/T-0014`**.
4. **⚠ Vierte Gestalt derselben Familie in vier Sprints.** SWR-122 (Prüfung ohne Leser),
   SWR-125 (Regel ohne Prüfung), SWR-128 (Fläche ohne Prüfung), jetzt **Entscheidung ohne
   Leser**. ⚠ Und Sprint 12 hatte die Lehre schon gezogen — nur nebenan: sein Punkt 16
   stellt fest, dass bei 60-Minuten-Takt ein **Brief mitten im Lauf der Regelfall** ist,
   und baute daraus die Doppelprüfung des Briefkastens. Für **Entscheidungen**, die über
   dieselbe Inbox zur selben beliebigen Zeit kommen, wurde sie nicht gebaut. Das ist die
   Erkennungsfrage aus `L-2026-08-17x`, unbeantwortet gelassen.
5. **⚠ Die Messung zu `platform/T-0013` widerlegt dessen eigene DoD — vor dem Bauen.** Das
   Ticket verlangt, `beginne()` solle verweigern, wenn der Vorsprint kein Ende hat **und
   sein Start weniger als einen Takt (60 Min) zurückliegt**. Gemessen über 12 Abstände:
   **Median 57 Min, Minimum 15, Maximum 124 — 7 von 12 liegen unter 60.** Die Zeitgrenze
   hätte also **die Mehrheit der regulären Folgeläufe abgewiesen**. Der Takt war eine
   Annahme; das Ticket hat selbst verlangt, sie zu messen. **Ergebnis: die Zeitgrenze
   trägt nicht, das Kriterium muss `ende` sein.** Die Neufassung steht im Ticket.
6. **Dieser Lauf löst zuerst zwei Zusagen aus Sprint 12 ein** (`pm/T-0064`, `pm/T-0066`) —
   die Agenda von gestern schrieb dem Auftraggeber wörtlich *„Beides kommt im nächsten
   Lauf"*, und **dieser Lauf ist der nächste**. Drei Zusagen in Folge nicht zu halten wäre
   die Wiederholung des Musters, das er zweimal gerügt hat (B025).

## Sprint-Plan

*Sprint 13 = dieser Lauf. Default nach `pm/D006`: in diesem Sprint schließen. Verschieben
nur mit Grund — Mensch nötig, zu groß (dann zerlegen) oder blockiert. **Fest geplant** ist
Sprint 14; ab Sprint 15 ist die Nummer eine **Reihenfolge**, keine Zusage.*

*Keine Kalenderdaten in der Fälligkeitsspalte (SWR-125). Ein Datum steht nur dort, wo ein
**Mensch** wartet.*

| Aufgabe | Rolle | Fällig | Status | Grund / nächster Schritt |
|---|---|---|---|---|
| projects/p12/T-0007 | pl | dieser Sprint | geplant | **Entschieden am 11:48:25 (`B-node-optional`), nie verbucht.** Verbuchen + Folgearbeit: die Skip-Meldung verweist heute auf einen *offenen* DR mit Frist — nach der Entscheidung schickt das den Leser ins Leere. |
| platform/T-0014 | cm | dieser Sprint | geplant | **Neu, Befund dieses Laufs.** Eine Stelle für „ist der DR entschieden?"; `wartet_auf_mensch` wird für entschiedene DRs falsch; **neuer Preflight-Befund** für „entschieden, nicht verbucht" — ⚠ ohne den zweiten Teil wäre die Reparatur nur ein Verstummen (wieder SWR-122). Drei Gegenproben. |
| pm/T-0064 | pl | dieser Sprint | geplant | **Zusage aus Sprint 12 an den Auftraggeber.** Projektübergreifende Liste aller offenen Aufgaben, lesend, aus `aggregation`; **nicht auf drei gekürzt**. Enthält die Rollen-Sicht aus `pm/N-0042` als Gruppierung **derselben** Liste (B033). |
| pm/T-0066 | pl | dieser Sprint | geplant | **Zusage aus Sprint 12.** Cockpit kompakter: **falten statt kürzen**. ⚠ Der Widerspruch zwischen `N-0038` (alles sehen) und `N-0042` (weniger Scrollen) ist im Ticket aufgelöst und dem Auftraggeber offengelegt. |
| pm/T-0052 | pl | dieser Sprint | geplant | **4. Verschiebung → Zerlegung fällig** (Regel `L-2026-08-17x`). Naht steht seit Sprint 12 im Ticket: „Für dich: Entscheidungen" / „Für dich: Handlungen". Erster Teil in diesen Sprint. |
| projects/p11/T-0008 | dev | dieser Sprint | geplant | **4. Berührung → Zerlegung fällig**, Naht seit Sprint 12 benannt: Endpunkt (lesend) / Widget-Konfiguration (schreibend). ⚠ Dem Auftraggeber in Sprint 11 zugesagt und in Sprint 12 nicht geliefert. |
| promt-team/T-0001 | dev | dieser Sprint | geplant | **4. Verschiebung → Zerlegung fällig**, Naht benannt: (a) erheben, (b) auswerten. Der Auftraggeber wartet (`promt-team/N-0001`); *„ohne Baseline kein Optimierungslauf"* ist sein eigener Satz. |
| pm/T-0061 | cm | dieser Sprint | geplant | Messen, ob `sprint_widerspruch` nach SWR-125 je einen möglichen Fall hatte — **messen vor entscheiden**. |
| platform/T-0013 | cm | Sprint 14 | offen | ⚠ **Verschoben mit gemessenem Grund, und die Messung ist das Ergebnis dieses Laufs**: die DoD-Zeitgrenze („weniger als ein Takt") hätte **7 von 12** regulären Läufen abgewiesen. Die DoD ist im Ticket **korrigiert** (Kriterium `ende`, Abbruch­erkennung über Schreibspuren statt Uhr). Bauen gegen eine widerlegte DoD wäre der Fehler, den das Ticket selbst verbietet. **Erste Verschiebung.** |
| pm/T-0063 | chg | Sprint 14 | offen | Charter-Entwurf + Gründungs-DR. ⚠ **Team-Gründung ist Klasse A** — das Ergebnis ist eine Vorlage an den Menschen, kein Bau. Zurückgestellt hinter die eingelösten Zusagen. **1. Verschiebung.** |
| projects/p12/T-0005 | pl | Sprint 14 | offen | ADR-Delta + Vollständigkeitsnachweis. **1. Verschiebung**, Grund: dieser Lauf gehört den beiden Zusagen und dem Befund. |
| promt-team/T-0002 | test | Sprint 14 | offen | **3. Verschiebung.** Sachlich hinter `T-0001a` (ohne Telemetrie kein Goldset-Maßstab). ⚠ Beim vierten Mal wird zerlegt — Naht: (a) Goldset-Format festlegen, (b) Fälle je Rolle erheben. |
| promt-team/T-0003 | dev | Sprint 15 | blocked | `blocked_by` T-0001/T-0002. ⚠ Sprint 12 hat notiert, dass es **auf demselben Sprint wie seine Blocker** stand — das ist hiermit aufgelöst: Blocker in 13/14, dieses Ticket in 15. |
| pm/T-0028 | chg | Sprint 14 | **zerlegt** | **Klammer**, Termin des letzten Teils (`T-0063`). Keine Verschiebung — sie enthält selbst nichts. |
| pm/T-0054 | chg | Sprint 14 | **zerlegt** | **Klammer** über `T-0064`/`T-0065`, Termin des letzten Teils. |
| pm/T-0065 | chg | Sprint 14 | offen | Zweiter Teil von `T-0054`. Knopf setzt `geplant_sprint`, `blocked_by: [T-0064]` — wird durch diesen Lauf erfüllt. |
| projects/p11/T-0009 | dev | Sprint 14 | offen | **3. Verschiebung.** Sachlich hinter `T-0008`. ⚠ Beim vierten Mal wird zerlegt — Naht: Deep-Link-Detailseiten / Mail-Widget hinter dem PIN-Leser. |
| projects/p11/T-0003 | pl | Sprint 14 | offen | **Klammer** über `T-0007`/`T-0008`/`T-0009`, nachgezogen auf `T-0009`. Keine Verschiebung. |
| projects/p12/T-0006 | pl | Sprint 14 | offen | Umstellung, Tests, G4, `blocked_by: [T-0005]`. |
| projects/p12/T-0003 | pl | Sprint 14 | **zerlegt** | **Klammer**, Termin des letzten Teils. |
| pm/T-0001 | pl | jeder Sprint | geplant | Takt: Session-Agenda fortschreiben. |
| pm/T-0002 | pl | jeder Sprint | geplant | Takt: Briefkasten qualifizieren — **zweimal**, beim Start und beim Abschluss (Regel aus Sprint 11/12). |
| pm/T-0003 | coach | jeder Sprint | geplant | Takt: Lessons sofort verankern (D005). |
| platform/T-0001 | cm | jeder Sprint | geplant | Takt: Preflight, Tests, Matrix, JS-Strecke. |
| team-mail/T-0001 | dev | jeder Sprint | geplant | Takt: Digest — fällig ab IMAP-Einrichtung, die weiterhin aussteht. |
| team-dashboard/T-0001 | pl | jeder Sprint | geplant | Takt: Widget-Vertrag — bei Änderung am Cockpit-Payload **prüfen**, nicht annehmen. |

**Warum sechs Zeilen keine Nummer tragen.** `pm/T-0001`, `pm/T-0002`, `pm/T-0003`,
`platform/T-0001`, `team-mail/T-0001` und `team-dashboard/T-0001` sind Takt-Dauerläufer
(`takt: je-session`) und laufen in **jedem** Sprint. Eine Nummer daneben wäre eine zweite
Aussage über dieselbe Sache (B033); genau deshalb nehmen `plan_drift`, `status_drift`,
`sprint_vergangen` und `unterminiert` sie aus.

**Rollenzuweisungen in diesem Sprint (D006).** `platform/T-0014` liegt bei `cm` — dieselbe
Prüfstrecken- und Werkzeugfläche wie `platform/T-0011`/`T-0012`/`T-0013`. Die Verbuchung
von `projects/p12/T-0007` liegt bei `pl` und **nicht** bei `mensch`: der Mensch hat seinen
Teil getan, ab hier ist es Teamarbeit — genau diese Übergabe hat gefehlt.

## Sprint-Abschluss (Sprint 13, 2026-08-17)

*wird beim Abschluss dieses Laufs fortgeschrieben*
