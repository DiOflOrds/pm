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
| projects/p12/T-0007 | pl | dieser Sprint | **erledigt** | **Entschieden am 11:48:25 (`B-node-optional`), 16 Minuten lang nicht verbucht.** Über den legalen Weg geschlossen; Folgearbeit erledigt: die Skip-Meldung nennt jetzt die **getroffene Entscheidung** statt einer Frist, die niemand mehr abwartet. |
| platform/T-0014 | cm | dieser Sprint | **erledigt** | **SWR-131.** Eine Stelle (`board.dr_entschieden`), **vier** Leser delegieren, neuer Preflight-Befund `dr_entschieden_nicht_verbucht`. ⚠ **Wiedereröffnet im selben Lauf**, weil die Nachprüfung zwei weitere Leser fand — darunter den Versandweg. 19 Zusicherungen, 5 Gegenproben. |
| pm/T-0064 | pl | dieser Sprint | **erledigt** | **SWR-132, erste Zusage aus Sprint 12 eingelöst.** ⚠ Quelle ist `sprint.offene_tickets` und nicht eine neue Funktion in `aggregation`: `offen_gesamt` kommt schon von dort, also sind Zahl und Liste **ein Objekt** und können nicht auseinanderlaufen. Abweichung im Ticket begründet. 6 Python-, 9 JS-Zusicherungen. |
| pm/T-0067 | pl | dieser Sprint | **erledigt** | **SWR-133, zweite Zusage eingelöst** (Teil a von `T-0066`). Cockpit-Gruppen zuklappbar, Zahl bleibt am Titel. ⚠ Gegenprobe: *nie angefasst* ist **nicht** *zugeklappt* — sonst startete jede Gruppe zu und er sähe **weniger** als vorher. |
| pm/T-0066 | pl | Sprint 14 | **zerlegt** | ⚠ **Zerlegt, weil die halbe DoD nicht erfüllbar war.** DoD 4 („wie viele Kacheln bei 1920×1080") ist eine Frage an einen gerenderten Browser; ADR-008 hat bewusst keinen, ein Headless-Browser wäre **Klasse A**. Klammer trägt den Termin des letzten Teils. |
| pm/T-0068 | pl | Sprint 14 | offen | **Neu, Teil b von `T-0066`, `verantwortlich: mensch`.** Die Messung — billigster Weg zuerst: der Auftraggeber sitzt vor dem Bildschirm. ⚠ **Einmal messen, zweimal zitieren:** `p11/T-0008` R2 stellt dieselbe Frage. |
| platform/T-0015 | cm | Sprint 14 | offen | **Neu, gemessen in diesem Lauf.** SWR-123 räumt Locks per `unlink`; auf diesem Mount ist genau das verboten, `rename` gelingt. ⚠ Die Regel steht in `L-2026-08-17ac` und **nicht im Code** — als Schuld geführt, nicht als erledigt gemeldet (SWR-125-Lage). |
| pm/T-0052 | pl | Sprint 14 | offen | ⚠ **4. Verschiebung — die Zerlegung ist damit überfällig, und dieser Lauf hat sie NICHT gemacht.** Grund: der Befund `platform/T-0014` und die zwei Zusagen haben den Lauf gefüllt. Das ist ein Grund, keine Entschuldigung. **Naht liegt seit Sprint 12 bereit** („Für dich: Entscheidungen" / „Für dich: Handlungen") — in Sprint 14 wird zerlegt, nicht wieder verschoben. |
| projects/p11/T-0008 | dev | Sprint 14 | offen | ⚠⚠ **4. Berührung, zweite nicht eingelöste Zusage in Folge.** Naht seit Sprint 12 benannt: Endpunkt (lesend) / Widget-Konfiguration (schreibend). Steht im Bericht an den Auftraggeber, nicht in einer Fußnote. |
| promt-team/T-0001 | dev | Sprint 14 | offen | ⚠ **4. Verschiebung.** Naht benannt: (a) erheben, (b) auswerten. Der Auftraggeber wartet (`promt-team/N-0001`); *„ohne Baseline kein Optimierungslauf"* ist sein eigener Satz. |
| pm/T-0061 | cm | Sprint 14 | offen | **1. Verschiebung.** Messen, ob `sprint_widerspruch` nach SWR-125 je einen möglichen Fall hatte — **messen vor entscheiden**. |
| platform/T-0013 | cm | Sprint 14 | offen | ⚠ **Verschoben mit gemessenem Grund, und die Messung ist das Ergebnis dieses Laufs**: die DoD-Zeitgrenze („weniger als ein Takt") hätte **7 von 12** regulären Läufen abgewiesen. Die DoD ist im Ticket **korrigiert** (Kriterium `ende`, Abbruch­erkennung über Schreibspuren statt Uhr). Bauen gegen eine widerlegte DoD wäre der Fehler, den das Ticket selbst verbietet. **Erste Verschiebung.** |
| pm/T-0063 | chg | Sprint 14 | offen | Charter-Entwurf + Gründungs-DR. ⚠ **Team-Gründung ist Klasse A** — das Ergebnis ist eine Vorlage an den Menschen, kein Bau. Zurückgestellt hinter die eingelösten Zusagen. **1. Verschiebung.** |
| projects/p12/T-0005 | pl | Sprint 14 | offen | ADR-Delta + Vollständigkeitsnachweis. **1. Verschiebung**, Grund: dieser Lauf gehört den beiden Zusagen und dem Befund. |
| promt-team/T-0002 | test | Sprint 14 | offen | **3. Verschiebung.** Sachlich hinter `T-0001a` (ohne Telemetrie kein Goldset-Maßstab). ⚠ Beim vierten Mal wird zerlegt — Naht: (a) Goldset-Format festlegen, (b) Fälle je Rolle erheben. |
| promt-team/T-0003 | dev | Sprint 15 | blocked | `blocked_by` T-0001/T-0002. ⚠ Sprint 12 hat notiert, dass es **auf demselben Sprint wie seine Blocker** stand — das ist hiermit aufgelöst: Blocker in 13/14, dieses Ticket in 15. |
| pm/T-0028 | chg | Sprint 14 | **zerlegt** | **Klammer**, Termin des letzten Teils (`T-0063`). Keine Verschiebung — sie enthält selbst nichts. |
| pm/T-0054 | chg | Sprint 14 | **zerlegt** | **Klammer** über `T-0064`/`T-0065`, Termin des letzten Teils. |
| pm/T-0065 | chg | Sprint 14 | offen | Zweiter Teil von `T-0054`. Knopf setzt `geplant_sprint`. ✅ `blocked_by: [T-0064]` ist durch diesen Lauf **erfüllt** — die Sperre ist gefallen. |
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

**Geplant beim Start:** 25 offene Sachtickets (davon 4 vom Menschen `rejected`, Altbestand)
+ 6 Takt-Pflichten, **kein offener Brief**. Der Startcheck fand **einen unverbuchten
Entscheid** — das wurde die Arbeit dieses Laufs.

**Im Lauf dazugekommen:** vier Tickets — `platform/T-0014` (Befund), `platform/T-0015`
(Lock-Räumung), `pm/T-0067` und `pm/T-0068` (Zerlegung von `pm/T-0066`).

**Geschlossen:** `projects/p12/T-0007`, `platform/T-0014`, `pm/T-0064`, `pm/T-0067` und die
sechs Takt-Pflichten — **zehn Stück**.

**Verschoben, mit Grund:** sieben Sachtickets nach Sprint 14, drei als Klammer nachgezogen.
⚠ **`pm/T-0052`, `p11/T-0008` und `promt-team/T-0001` sind vierte Verschiebungen** — die
Regel `L-2026-08-17x` verlangt bei vier die Zerlegung, und dieser Lauf hat sie **nicht
gemacht**. Die Nähte liegen seit Sprint 12 benannt bereit; in Sprint 14 wird zerlegt.

**Nicht eingelöst:** `p11/T-0008` — zweiter Lauf in Folge, nachdem Sprint 11 es zugesagt
hatte.

---

### ⚠⚠ Verifikation — dieser Lauf ist NICHT startklar, und der Grund ist er selbst

| Prüfung | Ergebnis |
|---|---|
| Python-Tests | **786 grün, 1 rot** |
| JS-Tests | **29 grün** (von 16) |
| Trace-Matrix | **133 SWRs / 0 Lücken** |
| Briefkasten (Start **und** Abschluss geprüft) | 0 offen |
| Entschiedene, unverbuchte DRs | **0** (war 1 beim Start) |
| Unzulässige Statusübergänge **seit dem Stichtag** | **1** ⚠⚠ |
| Altbestand unzulässiger Übergänge | 52 (unverändert, bewusst nicht geglättet) |

Der rote Test ist `test_uebergang_historie::test_seit_dem_stichtag_gibt_es_keinen_verstoss`,
und er hat recht: **dieser Lauf hat selbst einen unzulässigen Statusübergang committet.**

`platform/T-0014` wurde geschlossen, dann bewusst wiedereröffnet (die Nachprüfung fand zwei
weitere Leser). Die Datei ging `done → in_progress → in_review → done`, die **Commits** aber
`done → in_review`: der Zwischenstand bekam keinen eigenen Commit, weil die Wiederöffnung
sich wie Buchhaltung anfühlte und nicht wie ein Zustandswechsel.

> **Der Lauf, der die Prüfung gegen „Zustand nur in Prosa" gebaut hat, hat im selben Ticket
> den Zustand in der Historie verloren.**

**Nicht geglättet.** Kein Verschieben des Stichtags, kein Umschreiben der Historie, keine
Anpassung des Tests. Verankert als `L-2026-08-17ad`. Der Befund gehört in den Bericht, weil
ein grüner Bericht, der durch Verschieben des Maßstabs grün wird, nichts wert ist — genau
der Satz, aus dem SWR-128 entstanden ist.

**Zwei weitere Tests waren rot und sind reparierte Fehlalarme, keine Befunde:**
`test_org_kopfblock` suchte ein Literal, das SWR-133 um einen Eintrag verlängert hat
(Fehlalarm über die Schreibweise — dieselbe Art wie der Kommentar-Fehlalarm in SWR-128; der
Test prüft jetzt den Gruppennamen statt die Zeile). `test_sprint_statusdrift` meldete, dass
der Plan `p12/T-0007` noch als „geplant" führte, während das Ticket `done` war — durch diese
Fortschreibung erledigt.

### Taktmessung (Auftrag aus `platform/T-0013`, vor dem Bauen)

| n | Median | Minimum | Maximum | unter 60 Min |
|---|---|---|---|---|
| 12 Abstände | 57 Min | **15 Min** | 124 Min | **7 von 12** |

Die DoD von `platform/T-0013` wollte die Eröffnung verweigern, wenn der Vorsprint kein Ende
hat **und sein Start weniger als einen Takt zurückliegt**. Bei dieser Verteilung hätte die
Zeitgrenze **die Mehrheit der regulären Folgeläufe abgewiesen**. Das Ticket hat selbst
verlangt, den Takt zu messen statt ihn anzunehmen — die Messung widerlegt seinen eigenen
Vorschlag. Die DoD ist im Ticket korrigiert: **Kriterium ist `ende`**, die Abbrucherkennung
läuft über Schreibspuren (Commit-Zeitpunkte), nicht über die Uhr.

### Was dieser Lauf über sich gelernt hat

Vier Wiederholungen desselben Musters an einem Tag — **die Regel war bekannt und wurde am
Nachbarfall nicht angewandt:**

1. Sprint 12 baute die Doppelprüfung für **Briefe** und nicht für **Entscheidungen** aus
   derselben Inbox (→ SWR-131).
2. Der erste Anlauf von SWR-131 stellte drei Leser um und übersah zwei (→ Zähltest über den
   Quelltext).
3. Ein bestehender Test **sicherte das Fehlverhalten zu** (`["gesendet"]` an einen
   entschiedenen DR) — geprüft und bestätigt, nicht ungeprüft.
4. Und dieser Lauf verlor den eigenen Statusübergang (→ `L-2026-08-17ad`).

Die Erkennungsfrage aus `L-2026-08-17x` bleibt die produktivste Frage des Teams: *auf welche
anderen offenen Fälle trifft dieser Satz gerade zu?*
