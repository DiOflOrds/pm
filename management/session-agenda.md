# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

*Stand: 2026-08-16 15:35, Routine-Session (D004, alle 30 Min). Briefkasten: **leer** — zweimal
geprüft (Sessionanfang und -ende), alle 36 Briefe `beantwortet`. Inbox: **eine Entscheidung fiel
während der Session** (`pm/T-0031` → D006/TG-a, 15:21) und ist verbucht; danach steht dort **ein
neuer wartender Klasse-A-Entscheid**, den diese Session vorgelegt hat (`pm/T-0033`, G0 für P11).
Push: `PUSH-ANFORDERUNG.txt` aus der 14:50-Session war beim Start **noch unverarbeitet** (letzter
Wächter-Erfolg 14:30:22) — diese Session hängt eine weitere Zeile an. `pm/T-0010`, `pm/T-0013`,
`pm/T-0026` bleiben `in_review` (Grund unverändert: kein `gh`/Netzzugriff in dieser Sandbox —
bitte am Host/Browser gegenprüfen).*

**`pm/T-0030` ist ERLEDIGT (Teil 1, SWR-091) — das Ticket, das gegen das Liegenbleiben gebaut
wurde, war selbst der oberste liegengebliebene Punkt.** Die Session war frei (kein Brief, kein
entschiedener DR beim Start), und `T-0030` stand oben auf der Agenda; es ein sechstes Mal
weiterzureichen wäre die Wiederholung genau des Befunds gewesen, den es beschreibt (B043).
Geliefert: `frist` gilt für **jeden** Tickettyp und wird für jeden geprüft (bisher nur im
`decision-request`-Zweig — ein Tippfehler in der Frist eines CR fiel lautlos auf „keine Frist"
zurück); die Ampel-Regel liegt **einmal** in `board.frist_ampel` und wird von DR-Fristen und
Backlog-Fristen geteilt (sie stand inline im Cockpit; ein Test vergleicht alt und neu einen Monat
lang Tag für Tag); `board.ist_ueberfaellig` gilt nur für offene Tickets; die Cockpit-Kachel zeigt
überfällige Tickets **vollständig und vor den Statuszahlen** samt „n Tage über" plus einen Zähler
„n ohne Frist". Nebenbefund mitbehoben: `DATUM_MUSTER` prüfte nur die Form — „2026-13-01" kam
durch und hätte als **„grau" = keine Frist** gegolten, ein falsch terminiertes Ticket hätte wie
ein unterminiertes ausgesehen. **11 neue Tests, Gesamtsuite 329** (vorher 318), Matrix **91 SWRs /
0 Lücken**, Katalog- und Architektur-Gate grün, **Gegenprobe gegen den Altstand geführt** (3 Tests
scheitern dort nachweislich). **Das BOARD.md-Format blieb bewusst unangetastet** — eine neue
Spalte ist eine Formatänderung, und genau die hat heute früh alle board-check-Workflows rot
gemacht (`pm/T-0013`).

**Eskalationsregel festgelegt (B044) — das war die offene Frage in `T-0030`:** Ein überfälliges
Backlog-Ticket ist der **erste Arbeitspunkt der nächsten Routine-Session nach dem Briefkasten**,
vor jeder neuen Fläche. Nimmt eine Session es trotzdem nicht auf, **schreibt sie den Grund beim
Ticket in die Agenda** — nicht als Randnotiz. Ab dem **zweiten** übergangenen Mal geht ein Vermerk
an den Auftraggeber. Sofort angewandt statt nur gebaut: `pm/T-0028` (Frist 23.08.), `pm/T-0032`
(19.08.), `pm/T-0034` (17.08.).

**`team-dashboard` ist gegründet — D006/TG-a kam um 15:21 herein, mitten in dieser Session
(B045).** Der erste Inbox-Check um 15:11 hatte den DR noch als wartend gemeldet; gefunden hat die
Entscheidung die **Zweitprüfung aus B036** — der vierte Fund dieser Regel, diesmal an einem
Klasse-A-Entscheid, der sonst 30 Minuten unverbucht geblieben wäre. Vollzogen sind alle vier
Schritte aus `pm/T-0031`: Repo `team-dashboard` aus dem Template (Charter v1.0, `team.yaml`,
`steckbrief.yaml`, Decision-Log mit D000, board-check grün, **lokal ohne Remote** — bewusst **kein**
`.kein-remote`, denn `intern` erlaubt einen Remote, er fehlt nur, weil GitHub-Repo/Secret/PAT
Handlungen des Auftraggebers sind); Registry-Eintrag; erstes Takt-Ticket `team-dashboard/T-0001`
(**Widget-Vertrag entwerfen**, `takt: je-session`, Frist 23.08.) — die Voraussetzung aus dem
Kandidat-Text („Die Projekte haben eine Widget Kompatibilität") existiert nicht und ist damit die
eigentliche erste Arbeit; und der **getrennte G0-DR `pm/T-0033` für Projekt P11** (Dashboard-Bau,
Optionen G0a–G0c, Frist 23.08., Default G0a). **Die Mail-Widget-Auflage steht dreimal im
Klartext** — in `team.yaml`, im Charter und in der Registry: `team-mail` ist `sensibel`, gerendert
wird nur zur Laufzeit hinter dem PIN-Lesegate, und der erste committete Digest-Inhalt macht
`team-dashboard` `sensibel` und kostet den GitHub-Remote.

**Neuer Befund in eigener Sache: `pm/T-0034` — der team-mail-Wochendigest stand fünf Sessions
lang als unveränderte Randnotiz in Punkt 3.** `mail_digest.faellig(7)` meldet seit der
11:21-Session `True`, eine `-woche-`-Datei existiert bis heute nicht, und die Sessions 11:45,
12:16, 14:05, 14:50 haben jeweils „unverändert offen" notiert. Das ist wörtlich das Muster aus
B043 — deshalb ist es jetzt ein Ticket mit **Frist 17.08.** und Priorität hoch statt einer
Agendazeile. Lösen kann es nur der Host (kein IMAP/Ollama hier, Guardrail 2); der kürzeste Weg
steht im Ticket.

---


*Vorheriger Stand (14:50-Session, komprimiert): Ein neuer Brief `pm/N-0027` („starte mit der
initialiserung von team-dashboard aus dem projekt-pool") — angefangen, aber bewusst nicht
vollzogen: Team-Gründung ist Klasse A, deshalb Steckbrief formuliert und Gründungs-DR `pm/T-0031`
in die Inbox gestellt (Optionen TG-a–TG-d, Frist 23.08., Default TG-a) mit drei Befunden im
Antrag (Mail-Widget berührt Guardrail 2; Bauen ≠ Verwalten → Empfehlung eigenes Projekt P11;
„vom Handy aus dem Internet" kollidiert mit Runbook Kap. 10). **Der Auftraggeber hat am 16.08.
um 15:21 mit TG-a entschieden — vollzogen in der 15:35-Session, siehe oben.** `pm/T-0025`
ERLEDIGT (SWR-090, Sofort-Knopf sagt vorher womit er läuft und hinterher was entstanden ist;
8 Tests, Suite 318, Matrix 90/0, am echten System gelaufen).*

*Vorheriger Stand: 2026-08-16 14:05, Routine-Session (D004, alle 30 Min). Briefkasten: **drei neue
Briefe** seit der 12:16-Session — `pm/N-0024` (12:05) lag beim ersten Check bereits vor;
`pm/N-0025` (12:08) und `pm/N-0026` (12:10) gingen **während** der Session ein und wurden erst
bei der Zweitprüfung gefunden (Lesson B036, drittes Mal bestätigt). Alle drei beantwortet,
dritte Prüfung: leer. Inbox: unverändert leer (37 DRs, alle `done`) — kein neuer Kandidat
gestartet. Push: `PUSH-ANFORDERUNG.txt` aus der 12:16-Session war beim Start bereits
abgearbeitet — diese Session schreibt am Ende eine neue Zeile für ihre eigenen Commits.
`pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein
`gh`/Netzzugriff in dieser Sandbox — bitte am Host/Browser gegenprüfen).

**`pm/N-0024` sofort geliefert (`pm/T-0029`, SUP.9, zweite Korrektur an SWR-088):** „Quelle:
1-4000 Zeichen ... reicht auch nicht aus" — selbst die in `pm/T-0027` auf 4000 Zeichen
angehobene Grenze war für ein reales „Quelle"-Feld zu eng. Statt einer dritten geratenen Zahl
diesmal die Ursache behoben: `FELD_MAX` 4000 → 200 000 (technische Notbremse, keine
Inhaltsgrenze mehr) — hart verboten bleibt weiterhin nur `|`. HMI: „Nutzen"/„Voraussetzung"/
„Quelle" jetzt ebenfalls `<textarea>` statt einzeiliger Eingabe (alle drei laufen durch
dieselbe Prüfung, sonst wäre der nächste Brief zur nächsten Spalte fällig gewesen). 1 neuer
Test, Gesamtsuite **310** (vorher 309), Matrix weiterhin **89 SWRs / 0 Lücken**, Katalog-/
Architektur-Gate geprüft und grün. Klasse C — kein Decision-Log-Eintrag nötig (analog T-0027).

**`pm/N-0025` beantwortet — BEFUND in eigener Sache (B043, `pm/T-0030`):** Vorwurf „offene
Aufgaben werden nicht erledigt/terminiert" trifft zu, belegt an `pm/T-0025` (offen seit
10:40-Session, fünf Routine-Sessions nicht aufgegriffen). Zwei strukturelle Lücken: Backlog-
Tickets (CR/Problem) haben kein Fristfeld; „wiederkehrend" kennt keine feste Uhrzeit, nur „je
Sessionlauf". Nicht sofort gebaut (Entwurfsentscheidung mit Wirkung auf F14/alle Tickets —
B025/B038-Risiko eines zu schnell gebauten Werkzeugs) — als `pm/T-0030` für eine Design-Session
eingeplant. Sofort umgesetzt: `pm/T-0025` Priorität mittel → hoch.

**`pm/N-0026` beantwortet — einfache Statusfrage:** Ja, P9 ist abgeschlossen (G4a/D002,
Baseline `p9-v1.0`), kein offenes Ticket. Nur die drei Betriebs-Stichproben aus `p9/T-0004`
bleiben offen (Betriebsnachweis des Auftraggebers, kein Blocker).

*Vorheriger Stand (12:16-Session, komprimiert): Briefkasten hatte zwei neue Briefe
(`pm/N-0022`, `pm/N-0023`), beide beantwortet. `pm/N-0023` sofort geliefert als `pm/T-0027`
(SUP.9-Korrektur an SWR-088, `FELD_MAX` 200 → 4000). `pm/N-0022` (Team-Gründung im Pool) als
`pm/T-0028` (CR, `open`) für eine dafür vorgesehene Session eingeplant, bewusst nicht gebaut —
Klasse-A-Fläche mit Datenklassen-Wirkung. Inbox leer, 309 Tests, Matrix 89/0.*

---

*Vorvoriger Stand: 2026-08-16 12:16-Session, ausführlich. Briefkasten: **zwei neue Briefe**
seit der 11:45-Session — `pm/N-0022` (09:59, aber erst 11:59 committet) und `pm/N-0023` (10:05,
erst 12:05 committet) —, zweimal geprüft (Sessionanfang und -ende, Lesson B036), beide
beantwortet. Inbox: unverändert leer (37 DRs, alle `done`) — kein neuer Kandidat gestartet.
Push: `PUSH-ANFORDERUNG.txt` aus der 11:45-Session war beim Start bereits abgearbeitet
(Wächter-Erfolg 12:00:22) — diese Session schreibt am Ende eine neue Zeile für ihre eigenen
Commits. `pm/T-0010`, `pm/T-0013`, `pm/T-0026` bleiben `in_review` (Grund unverändert: kein
`gh`/Netzzugriff in dieser Sandbox — bitte am Host/Browser gegenprüfen).

**`pm/N-0023` sofort geliefert (`pm/T-0027`, SUP.9-Korrektur an SWR-088):** „Projekt-Pool:
1-200 Zeichen, keine Zeilenumbrüche" war zu eng für den Zweck des Feldes — bei
Technik-Kandidaten trägt der Kandidat-Text die ganze Aufgabe, bei Team-Kandidaten die
Kurzbeschreibung, beides sollte mehrsätzig (auch KI-formuliert) sein dürfen. `FELD_MAX`
200 → 4000, Zeilenumbrüche werden jetzt zu Leerzeichen normalisiert statt die Eingabe
abzulehnen (`pool._text_bereinigen`) — hart verboten bleibt nur `|` (sprengt die
Markdown-Tabellenzeile). HMI: Kurzbeschreibung/Kandidat-Text jetzt `<textarea>` statt
einzeiliger Eingabe. **Bewusst nicht angefasst:** `kandidat_starten` prüft weiter hart auf
`|`/`"`/Zeilenumbruch (Text landet dort im Ticket-YAML) — Bestandsverhalten aus `pm/T-0022`.
4 neue/geänderte Tests, Gesamtsuite **309** (vorher 305), Matrix weiterhin **89 SWRs / 0
Lücken** (kein neuer SWR), Katalog-/Architektur-Gate geprüft und grün.

**`pm/N-0022` — Team-Gründung im Pool beauftragt, aber bewusst nicht in dieser Session
gebaut (`pm/T-0028`, CR, `open`):** Der Brief nennt selbst den Unterschied zu „Projekt
starten" („bei team-steuer/team-trading hängt daran mehr als ein Ordner"). `intake.md`
verlangt für eine Team-Gründung einen vollen Steckbrief (Auftrag, Profil, Rollen,
**Datenklasse**, Zugänge, Grenzen), Repo aus Template statt Ordner-Skelett, bei `sensibel`
ausdrücklich keinen GitHub-Remote — Klasse A mit Datenklassen-Wirkung (Playbook Kap. 16).
Das als Formular in einer Routine-Session ohne Rückfrage zu entwerfen, ist genau das
Risiko aus B025/B038 (ein zu schnell gebautes Werkzeug täuscht Sicherheit vor, die es
nicht hält) — deshalb als eigenes, für eine dafür vorgesehene Session eingeplantes Ticket
angelegt statt durchgezogen. Zweiter Teil des Briefs („Löschen von Kandidaten bleibt
Session auf Zuruf") ist eine Festlegung, keine Anfrage — bestätigt, keine Code-Änderung.

*Vorheriger Stand (11:45-Session, komprimiert): Briefkasten/Inbox clean, `pm/T-0022` Teil 2
„Starten" geliefert (SWR-089, Variante A, nur Technik-Kandidaten, 20 Tests, Matrix 89/0) —
Ticket damit komplett (beide Teile `done`). Push-Wächter 11:00 erfolgreich. 305 Tests
(vorher 285). team-mail-Befund unverändert (siehe Punkt 3).*

---

*Vorheriger Stand: 2026-08-16 10:23, Routine-Session (D004, alle 30 Min). **BEFUND: Der Auto-Push stand seit 09:44 still — bemerkt hat es der Auftraggeber, nicht die Automatik (B038, `pm/T-0024`).** Sein Brief `pm/N-0021` fragte, warum ein paar pm-Tickets „seit längerem in review" stehen. Der Grund lag nicht bei den Tickets: `pm/T-0010` und `pm/T-0013` warten beide auf einen grünen GitHub-Actions-Lauf, und der Wächter brach dreimal in Folge ab (09:44, 09:59, 10:14); letzter erfolgreicher Push **08:30**. Liegengeblieben waren **21 Commits** und die Baseline-Tags `p10-v1.0` — die Abnahme des zehnten Projekts existierte auf GitHub nicht. Ursache: `git_prozess_aktiv()` las die `tasklist`-Ausgabe im falschen Codec und meldete ausgerechnet dann „Git läuft", wenn **keiner** lief (das `ü` in „ausgeführt" ist in CP850 das Byte 0x81); dazu ein nicht hermetischer Test, der den ganzen Rechner nach Git-Prozessen fragte, um ein Fake-Repo in %TEMP% zu prüfen. Beides behoben, 4 neue Tests, Gegenprobe gegen den alten Code (2 scheitern dort) und der Abbruch von 10:14 exakt nachgestellt. **267 Tests, Matrix 87/0, 0,00 € API.** `pm/T-0010` und `pm/T-0013` bleiben bewusst `in_review` mit Vermerk — ein Fremdnachweis wird nicht dadurch erbracht, dass jemand nachfragt (B025). Briefkasten: **zwei** Briefe beantwortet — `pm/N-0021` (Push-Befund) und `team-mail/N-0002`; letzterer kam um **10:17 herein, also nach dem Check am Sessionanfang**, und wurde nur durch die Zweitprüfung aus B036 gefunden — zweiter Fund in zwei Sessions. **Zu N-0002 ein echter Fehler (B040/B041, `team-mail/T-0003`): „Jetzt zusammenfassen" lief fest auf einen Tag, obwohl das Team auf `takte: [7]` (wöchentlich) steht** — jeder Klick erzeugte einen Tages- statt des konfigurierten Wochen-Digests, ohne Fehlermeldung, erkennbar nur am Dateinamen. Behoben (`jetzt_takte`), Regressionstest mit Gegenprobe (`[1] != [7]`). Der KI-Hinweis wirkte dort übrigens die ganze Zeit — er war nur nirgends sichtbar. **Dabei sind zwei Routine-Sessions kollidiert** (B041): Die parallele Session hatte denselben Befund gefunden und ihre Arbeit dann selbst zurückgezogen; ohne den Board-Check (2 statt 3 Tickets) wäre er verschwunden und die Brief-Antwort hätte auf ein nicht existierendes Ticket verwiesen. Sonst keine offenen Briefe (alle 28 geprüft). **268 Tests.** Inbox: leer — gegen die Rohdaten geprüft, alle 38 DR-Tickets stehen auf `done` (Lesson B025). team-mail-Takt: Tages-Digest 2026-08-16 liegt zugestellt vor, nichts fällig. **`pm/T-0022` blieb liegen (B039) — Reihenfolge, nicht Zeitmangel: solange nichts nach außen geht, erzeugt jede Feature-Session unsichtbare Arbeit.** Reihenfolge für die nächste Session:*

**⚠ Zweiter Befund derselben Session (B042, `pm/T-0026`) — und der erste hat ihn verdeckt gehalten:** Der Auftraggeber meldete um 10:36 einen **roten CI-Lauf** (`platform/N-0006`). Nachgestellt: mit `projects` **87 SWRs / 0 Lücken**, mit der Repo-Liste aus `ci.yml` **82 / 5 Lücken → exit 1**. `ci.yml` checkt `projects` **nicht** aus — seit `pm/D003` liegen Projekte aber als Ordner darin, P10 hat dort SWR-077–081. Rot ist der Workflow **seit der P10-Freigabe um 08:18**; sichtbar wurde es erst, als der Push um 10:30 wieder lief. Behoben (Checkout ergänzt), bleibt `in_review` bis ein grüner Lauf vorliegt. **Handlung des Auftraggebers nötig:** `P0_READ_TOKEN` muss `DiOflOrds/projects` einschließen, sonst scheitert künftig der Checkout statt des Matrix-Schritts.

**Zuerst nachsehen, ob der Push wieder läuft:** `PUSH-ANFORDERUNG.txt` verschwunden und in `abschluss-auto.log` `OK - alles geprueft und gepusht`? Wenn ja, sind damit auch `pm/T-0010` und `pm/T-0013` fällig zum Schließen (grüne board-check-Actions prüfen). Wenn nein: **nicht weiterbauen**, sondern die Abbruchstelle im Log lesen — der Grund steht dort immer, nur liest ihn ohne Anlass niemand.

*Erledigt (11:21-Session): Ja, der Push lief wieder — `PUSH-ANFORDERUNG.txt` war bereits weg, Log zeigt `OK - alles geprueft und gepusht` um 11:00:10. Die grünen board-check-Actions selbst kann diese Cowork-Sandbox nicht einsehen (kein `gh`, kein Netzzugriff auf github.com) — `pm/T-0010`/`pm/T-0013`/`pm/T-0026` bleiben deshalb bewusst `in_review`, bitte am Host/Browser gegenprüfen und dann schließen.*

---

*Vorheriger Stand: 2026-08-16 10:05, Routine-Session. **P10 Sprint 1 ist gebaut und liegt zur Abnahme (B033/B034).** Der Lock-Fallback aus `pm/T-0023` hat beim Start gearbeitet (Meldung „weggeräumt nach `.git/verwaiste-locks/`" in 15 Repos) — ohne ihn wäre auch diese Session blockiert gewesen. Geliefert: ADR-007 (zweiter Schreibpfad auf Tickets, Regeln bleiben in `board.py`, Fingerabdruck statt Sperre), `backend/tickets.py` als Fassade, `GET /api/ticket/editor` + `POST /api/ticket`, Editor-Ansicht, Label-Pillen und Label-Filter im HMI; SWR-077–081 **einzeln** auf `reviewed` mit ihrem jeweiligen Nachweis (B027 eingehalten). **263 Tests, Matrix 87/0, 0,00 € API.** Nebenbefund mitbehoben: die Zeitstempel-Formatierung (SWR-084) lag doppelt vor — `inbox.entscheidungszeitpunkt` delegiert jetzt an `board.zeitpunkt`. **G4 nicht selbst abgenommen:** `p10/T-0004` liegt als DR in der Inbox (Frist 23.08., Default G4a), Baseline `p10-v1.0` bleibt bis dahin ungesetzt. Briefkasten: keine offenen Briefe (alle 25 auf `beantwortet` geprüft). Inbox: **eine** wartende Entscheidung (`p10/T-0004`) — gegen die Rohdaten geprüft, nicht nur gegen die Werkzeugausgabe (Lesson B025). team-mail-Takt: Tages-Digest 2026-08-16 liegt zugestellt vor, nichts fällig. Reihenfolge für die nächste Session:*

**Für den Auftraggeber, eine Handlung (keine Entscheidung):** Der Cowork-Session fehlt auf `Downloads\aspice-team-repos-final` das Recht, Dateien zu **löschen**. Der neue Fallback macht das Team wieder arbeitsfähig, beseitigt die Ursache aber nicht — es sammeln sich weiter unlöschbare `.git\objects\**\tmp_obj_*` an. Sauber wird es erst mit erteiltem Lösch-Recht; bis dahin gelegentlich `.git\verwaiste-locks\` und die `tmp_obj_*` auf dem Host aufräumen (Runbook Kap. 5, R7).

0. **Briefkasten zuerst** — alle Projekte/Teams (Cockpit zeigt offene Briefe). *Aktuell keine offenen Briefe (alle 26 auf `beantwortet` geprüft; `platform/N-0004` kam **während** der Session um 10:04 herein und wurde in derselben Session beantwortet — B036).* **Merke für den Ablauf:** Der Briefkasten wird nicht nur am Anfang gelesen. Diese Session hätte den Brief sonst 30 Minuten liegen lassen, obwohl sie noch lief; aufgefallen ist er nur, weil beim Taggen ein fremder Commit im `platform`-Log stand. Ab jetzt: **vor dem Abschluss ein zweites Mal auf offene Briefe und entschiedene DRs prüfen** — dasselbe gilt für die Inbox (die G4a-Entscheidung kam 14 Sekunden nach dem Sprint-Commit).
0b. **Repo-Zustand vor dem ersten Schreiben** — `preflight.py` laufen lassen und die Ausgabe **lesen**. Steht dort „nicht löschbar … weggeräumt nach `.git/verwaiste-locks/`", hat der Fallback aus `pm/T-0023` gearbeitet und die Session wäre ohne ihn blockiert gewesen. Danach `git status` je Repo: **Liegt Arbeit einer Vorsession unverbucht da, zuerst verifizieren (Tests + Matrix + Gates), dann committen** — nie ungeprüft übernehmen (B025), nie doppelt verbuchen.
0c. **Überfällige Tickets zuerst (Eskalationsregel B044, seit SWR-091 maschinell sichtbar).** Die Cockpit-Kachel zeigt je Projekt/Team überfällige Aufgaben **über** den Statuszahlen, mit „n Tage über", dazu „n ohne Frist". Ein überfälliges Backlog-Ticket ist der **erste Arbeitspunkt nach dem Briefkasten**, vor jeder neuen Fläche. Wird es trotzdem nicht aufgegriffen, **steht der Grund hier beim Ticket** — nicht als Randnotiz. Ab dem zweiten übergangenen Mal geht ein Vermerk an den Auftraggeber. *(Erledigt in der 15:35-Session: `pm/T-0025` war bereits weg — 14:50, SWR-090.)*

*Erster Fund des neuen Zählers (SWR-091), noch in der Session seiner Einführung: Die pm-Kachel meldet **4 offene Tickets „ohne Frist"** — `T-0010`/`T-0013`/`T-0026` warten auf einen fremden Nachweis (grüner Actions-Lauf) und sind zu Recht unterminiert, aber **`pm/T-0003` heißt „Takt: LeLe je Sprint/Durchlauf konsolidieren" und trägt gar kein `takt`-Feld** — im Board steht es deshalb als „einmalig". Das war zur Zeit von B014 so gewollt, `pm/D005` hat es danach auf „kontinuierlich" umgestellt, ohne das Feld nachzuziehen. **Bewusst nicht auf Verdacht gesetzt:** `je-session` ist nicht dasselbe wie „je Sprint/Durchlauf", und TAKTE kennt letzteres nicht — das gehört zu `pm/T-0032` (Takt-Konzept), nicht in einen Nebensatz. Nächste Session: entweder Feld setzen oder begründen, warum keins.*

1. **Offene pm-Tickets, jetzt alle terminiert (SWR-091).** **`pm/T-0034` — Frist 17.08., Priorität hoch:** team-mail-Wochendigest seit Gründung fällig, nie erzeugt; fünf Sessions lang nur Randnotiz in Punkt 3, jetzt eigenes Ticket. Lösbar **nur am Host** (kein IMAP/Ollama hier) — kürzester Weg im Ticket. **`pm/T-0032` — Frist 19.08.:** Teil 2 aus `pm/N-0025`, echter Uhrzeit-Takt („jeden Tag um 14 Uhr"); berührt F14 und die zwei bestehenden Taktlogiken, Entwurf im Ticket, **erster Nutzer des Fristfeldes, das Teil 1 gebaut hat**. **`pm/T-0028` — Frist 23.08.:** Gründungs-Knopf im Pool; die von Hand vollzogene Gründung von `team-dashboard` ist jetzt seine reale Vorlage. **`team-dashboard/T-0001` — Frist 23.08.:** Widget-Vertrag entwerfen, Vorbedingung für P11. **ERLEDIGT:** `pm/T-0030` Teil 1 (SWR-091, 15:35-Session), `pm/T-0031` (Gründung vollzogen, D006/TG-a), `pm/T-0025` (14:50, SWR-090), `pm/T-0029` (14:05), `pm/T-0027` (12:16), `pm/T-0022` (beide Teile). **Wartend beim Auftraggeber:** `pm/T-0033` (G0 für **P11 „Widget-Dashboard"**, Optionen G0a–G0c, Frist 23.08., Default G0a) — nach G0a folgen Projektordner `projects/p11`, SWRs als `draft` bis G1, Sprint-0-Plan mit dem Widget-Vertrag als Eingangsbedingung.

2. **P10 ist abgeschlossen (G4a/D002, 10:02 via Inbox — B035)** — Baseline `p10-v1.0` auf `projects` und `platform`, Abschlussbericht liegt in `projects/p10/management/`. Offen bleibt nur der **Betriebsnachweis des Auftraggebers**: die sieben Stichproben aus `p10/T-0004` (siehe Punkt 5) — nur erinnern, nie selbst abhaken.
3. **team-mail-Takt (`team-mail/T-0001`): SLA erstmals seit Gründung erfüllt (B046).** Der **erste Wochendigest** liegt (`digest/2026-08-16-woche-digest.md`), `mail_digest.faellig(7)` meldet `False`. Zustandegekommen ist er allerdings von Hand: Ein Lauf des Auftraggebers um 15:28 holte 165 Mails über 7 Tage, fand **kein Ollama** und schrieb Rohdaten mit dem Vermerk *die naechste Session verdichtet* — das war diese (Fallback SWR-062). **Der Rest des Befunds steht als `pm/T-0034`, Frist 17.08.:** Warum lief Ollama nicht, und ist `ASPICE-MailAutopilot` überhaupt eingerichtet? Ein fälliger Wochendigest darf nicht auf einen Klick warten.
4. **Fällige pm-Takt-Tickets** — Intake-Queue, Agenda fortschreiben; PUSH-ANFORDERUNG.txt am Session-Ende schreiben (Runbook Kap. 11).
5. **Offene Stichproben des Auftraggebers nachhalten** (nur erinnern, nie selbst abhaken) — **alle brauchen vorher einen Serverneustart**:
   - **Neu (15:35-Session, SWR-091/pm/T-0030):** **Cockpit öffnen** — über den Statuszahlen einer Kachel steht bei überfälligen Aufgaben ein roter Block („n überfällig", je Ticket „Frist … (n Tage über)"), in der Statuszeile eine Pille „n ohne Frist". Gegenprobe: einem offenen Ticket im Ticket-Editor eine Frist von **gestern** geben → es erscheint sofort im roten Block; eine unsinnige Frist („2026-13-01") wird beim Speichern mit Klartext abgelehnt.
   - **Neu (15:35-Session, pm/T-0031/D006):** **Kopfbereich und Cockpit** zeigen `team-dashboard` als **Projekt-Team** mit Board und einer offenen Aufgabe (`T-0001`, wiederkehrend). **Inbox** zeigt den neuen G0-Antrag `pm/T-0033` (P11) mit drei Knöpfen G0a–G0c und Frist 23.08.
   - **Neu (14:50-Session, SWR-090/pm/T-0025):** **Team-Reiter `team-mail`** — unter „Jetzt zusammenfassen" steht die Klartextzeile **„Ein Klick startet: Woche · Modell: gemma3:27b · KI-Hinweis: kein Zusatz · Versand: zusätzlich per Mail"**. Im Konfigurator einen KI-Hinweis eintragen, speichern, Seite neu laden → die Zeile zitiert ihn. Takt auf „Täglich" umstellen, speichern, neu laden → die Zeile sagt „Tag". Nach einem echten Klick nennt die Erfolgsmeldung die geschriebene Datei beim Namen.
   - **Neu (14:50-Session, pm/T-0031):** **Inbox öffnen** — der Gründungs-Antrag `pm/T-0031` steht dort mit vier Knöpfen `TG-a` bis `TG-d` und Frist 23.08.
   - **Neu (14:05-Session, pm/T-0029):** Pool-Reiter → „Neuen Kandidaten anlegen" → Technik-Kandidat, in „Quelle" einen deutlich über 4000 Zeichen langen Text eintragen (z. B. einen längeren Gesprächsausschnitt) → anlegen → erscheint als eine Zeile im Pool, keine Ablehnung. Nutzen/Voraussetzung/Quelle sind jetzt Mehrzeilenfelder im Formular.
   - **Neu (12:16-Session, pm/T-0027):** Pool-Reiter → „Neuen Kandidaten anlegen" → Technik-Kandidat, mehrsätzigen Text mit Zeilenumbrüchen eintragen (z. B. aus einer KI-Antwort kopiert), anlegen → erscheint als eine Zeile ohne Zeilenumbrüche im Pool.
   - **Neu (11:45-Session, SWR-089):** **Pool-Reiter „Projekt starten"** — einen Technik-Kandidaten aus der Dropdown wählen (z. B. einen unwichtigen wie „JS-Frontend-Tests"), auf „G0-Antrag anlegen" klicken; Meldung zeigt die neue Projekt-Referenz (z. B. `p11/T-0001`), der Kandidat verschwindet ohne Neuladen aus der Pool-Tabelle, die Inbox zeigt den neuen G0-Antrag mit Frist. `git -C projects log --oneline -2` und `git -C pm log --oneline -2` zeigen je einen „Mensch via HMI"-Commit. Einen Team-Kandidaten wählen sollte mit einer Erklärung abgelehnt werden (Team-Gründung ist nicht Teil dieses Knopfs). Kopfzeile im Pool-Reiter sagt jetzt „Anlegen: da / Starten (Technik) per Knopf: da". **Danach entweder über die Inbox entscheiden (G0a/b/c) oder den Testordner wieder entfernen, wenn die Stichprobe nur die Funktion prüfen soll.**
   - **Neu (11:21-Session, SWR-088):** **Pool-Reiter „Neuen Kandidaten anlegen"** — einen Team- und einen Technik-Kandidaten anlegen (unterschiedliche Felder je Kategorie), beide erscheinen ohne Neuladen im richtigen Abschnitt; `git -C pm log --oneline -2` zeigt „Mensch via HMI"-Commits.
   - **Neu (B033/B034), die sieben Stichproben aus `p10/T-0004`:** Ticket bearbeiten und speichern · unerlaubten Status setzen → deutsche Ablehnung · zwei Labels vergeben und im Board danach filtern · `git -C projects log --oneline -3` zeigt „Änderung via HMI" mit BOARD.md im selben Commit · Konflikt erzwingen (Ticket am Handy offen, vom Rechner speichern, dann am Handy) → Klartextmeldung + „Ticket neu laden" · vom Handy ohne PIN speichern → Ablehnung, mit PIN → geht · erledigtes Ticket öffnen → nur „Wiedereröffnen", kein Formular.
   - **Neu (B028):** **Requirements-Reiter** — stehen ohne Projektwahl alle Dokumente da (22 aus 13 Projekten/Teams)? Filter „Projekt/Team: p10" und Volltext „SWR-085" prüfen. Auch auf dem Handy.
   - **Aus B029:** **Reiter „Projekt-Pool"** — beide Kategorien (5 Team-, 7 Technik-Kandidaten) sichtbar? *(Kopfzeilentext hat sich seither zweimal geändert, siehe die beiden neuen Stichproben oben — diese hier prüft nur noch die Sichtbarkeit der Kategorien.)*
   - **Neu (B030):** **Eindeutige Kennung** — Board von `pm` zeigt `pm/T-0019`, Board von `p10` zeigt `p10/T-0001`; Ticket-Detail und Cockpit genauso.
   - **Aus B024:** **Inbox öffnen** — sie ist jetzt leer (alle DRs entschieden); der Nachweis, dass Anträge aus dem Sammel-Repo dort ankommen, wurde durch die P10-Freigabe um 08:18 bereits praktisch erbracht.
   - **Aus B023:** **Server-Log** — Handy verbinden, Bildschirm sperren: nur noch `Verbindung zu … vorzeitig beendet … kein Fehler`, kein Traceback. Nachweis geht nur auf Windows (WinError 10054).
   - **Aus B021:** **Kopfbereich** — nur feste Teams, Projekt-Teams und aktive Projekte anklickbar; Deep-Link `#/board/p3` klappt „weitere" von allein auf. Auch auf dem Handy.
   - P9-Cockpit: 3 Stichproben aus `p9/T-0004` (Gruppen, Einklappen, Aufgaben-Links).
   - Aus B010: Konfigurator öffnen → **KI-Modell** auswählen und **KI-Hinweis** eintragen, speichern, „Jetzt zusammenfassen" laufen lassen und den Digest inhaltlich bewerten.
   - Aus B013: **Selbst-Neustart** — Mission Control über `mission-control.cmd` starten, dann prüfen, ob der Server nach einer Session von allein hochkommt und die Seite nachlädt.
   - Aus B014: **Takt-Kennzeichnung** — Board von `pm` öffnen: `pm/T-0001`/`pm/T-0002` „wiederkehrend: je Session", `pm/T-0003` einmalig.
6. **Drei Tickets warten auf denselben Nachweis — einen grünen GitHub-Actions-Lauf:** **`pm/T-0010`** (board-check-Flake), **`pm/T-0013`** (Push-Reihenfolge platform zuerst) und neu **`pm/T-0026`** (`projects`-Checkout in `ci.yml`). Alle drei bleiben `in_review`; lokal ist alles grün, und genau das war bei T-0026 der Fehler. **Reihenfolge beim Prüfen:** erst T-0026 — solange das Matrix-Gate rot ist, sagt ein roter Lauf nichts über T-0010/T-0013 aus.
7. **Pilotreview:** team-mail ab 2026-08-29 (B002) — Digest-Format-Feedback, B003 (Werkzeug-Promotion), CR-Kandidat Markdown-Renderer für Briefe/Reports.
8. **Betriebs-Backlog** — BB-5 PAT-Erneuerung ab 2026-09-05 (ab 1.9. aktiv erinnern). CR-Kandidaten: **neu (aus B038): der Auto-Push-Wächter meldet Fehlschläge nur nach `abschluss-auto.log`** — eine Warnmail nach dem n-ten Fehlversuch (die Mail-Strecke aus SWR-033 existiert bereits) hätte heute zwei Stunden Stillstand auf fünfzehn Minuten verkürzt. Bewusst nicht nebenbei gebaut: Mailversand ist Außenwirkung und gehört nicht in einen SUP.9-Fix; `abschluss.cmd`, `abschluss-auto.cmd` und die `mission-control*.cmd` liegen **unversioniert** im Wurzelordner (Vorschlag: nach `platform/infra/` versionieren, im Wurzelordner nur dünne Aufrufer); Projekt-Workflows checken `platform` auf einem **Tag** statt `main` aus; **neu:** Repo-Präfix auch im generierten `BOARD.md` (aus `pm/T-0021` zurückgestellt — Formatänderungen am Board haben heute schon einmal alle Prüf-Workflows rot gemacht, das gehört gebündelt mit `pm/T-0013`).

*Hinweis (D004): Diese Agenda wird automatisch alle 30 Min von der Cowork-Routine-Session abgearbeitet (solange die App offen ist) — Briefe genügen, Ankündigungen im Chat sind nicht mehr nötig.*

*Beobachtung 2026-08-16 (für die Retro/LeLe): Zwei Routine-Sessions können sich überlappen. Erkennungsmerkmal ist ein `.git/index.lock`, das die eigene Arbeit blockiert; Auflösung siehe Runbook Kap. 5 (Preflight erneut, ggf. Cowork-Löschrecht erteilen). Regel: erst Repo-Status prüfen, dann schreiben — nie doppelt verbuchen.*

*Lesson 2026-08-16 **verschärft** (aus B041): Die Überlappung ist eingetreten, und sie sah anders aus als erwartet — **nicht** als Lock, sondern als **fremde Änderung an einer Datei, die diese Session nur gelesen hatte** (`team-mail/tools/mail_digest.py`). Beide Sessions bearbeiteten denselben Brief; die parallele hatte den besseren Befund und zog ihre Arbeit dann selbst zurück, weil sie den Konflikt bemerkte. Übrig geblieben wäre eine Brief-Antwort, die auf ein Ticket verweist, das nicht mehr existiert (die Lesson aus B029), plus ein verschwundener, richtiger Befund. Gefunden wurde das nur, weil der Board-Check **2 statt 3 Tickets** meldete. **Neue Regeln: (1)** Vor dem Commit `git status` je Repo **lesen**, nicht nur auf sauber prüfen — eine Änderung an einer Datei, die man selbst nicht angefasst hat, ist ein Stoppsignal, kein Rauschen. **(2)** Wer fremde uncommittete Arbeit vorfindet, prüft sie gegen die Werkzeuge und benennt ihre Herkunft; übernehmen ohne Prüfung ist B025, verwerfen ohne Prüfung kostet den Befund. **(3)** Zahlen aus Werkzeugausgaben (Tickets, Tests) gegen die Erwartung lesen — „3 Tickets validiert" ist eine Aussage, „2" war hier der einzige Hinweis auf einen Verlust.*

*Lesson 2026-08-16 (aus pm/T-0023, B031): **Ein Werkzeug, das eine Blockade nur beschreibt, hat die halbe Arbeit getan.** Preflight erkannte den unlöschbaren `index.lock` vollständig richtig und verwies auf eine Handlung des Menschen am Host — währenddessen verlor eine fertige Session ihre komplette Verbuchung, obwohl der Ausweg (`rename` statt `remove`) auf demselben Mount die ganze Zeit offen war. DoD-Prüffrage für Diagnose-Ausgaben: **„Gibt es neben dem gesperrten Weg einen offenen, den das Werkzeug selbst gehen könnte?"** Verwandt zu B025: Dort log ein leeres Werkzeugergebnis über den Zustand, hier eine korrekte Meldung über die Handlungsmöglichkeiten.*

*Lesson 2026-08-16 (aus pm/T-0023, zweiter Befund): **Der Nachweis gehört ans Ende der Kette, nicht ans Ende der Änderung.** Der erste Lock-Fix war für sich richtig und mit 5 grünen Tests belegt — und ließ die Session trotzdem gesperrt zurück, weil Preflights eigene `git status`-Aufrufe neue Locks erzeugten, nachdem es aufgeräumt hatte. Geprüft war die Funktion, nicht der Zustand, in dem sie das System zurücklässt. DoD-Prüffrage: **„Ist der nächste echte Arbeitsschritt danach noch möglich?"** — einmal am echten System ausgeführt, nicht im Test nachgestellt.*

*Lesson 2026-08-16 (aus B031, für die Retro/LeLe): **Ein Statusbericht ist kein Beleg dafür, dass etwas in Git steht.** PROJEKTSTATUS-UPDATE.md und Agenda beschrieben B028/B029/B030 als geliefert — `git log` kannte nichts davon. Neue Pflicht am Session-Anfang (Punkt 0b) und am Session-Ende: Der Abschluss gilt erst als erreicht, wenn `git status` in **jedem** Repo sauber ist; „dokumentiert" und „verbucht" sind zwei verschiedene Zustände.*

*Lesson 2026-08-16 (aus p9/T-0007, für die Retro/LeLe): Wenn eine Anforderung „die Werkzeuge sollen X unterstützen" sagt, ist sie erst erfüllt, wenn jede Kopie der betroffenen Logik nachgezogen — besser: zu einer zusammengeführt — ist. DoD-Prüffrage: „Gibt es diese Auflösung noch ein zweites Mal im Repo?"*

*Lesson 2026-08-16 **verschärft** (aus pm/T-0017, B025): Die Prüffrage oben wurde am Vormittag nur auf die Skripte angewendet, in denen der Befund auftrat — im Backend blieben vier weitere Kopien stehen und machten am Nachmittag einen **Klasse-A-Entscheidungsantrag unsichtbar**. Ab sofort: Wer Discovery oder Pfadauflösung anfasst, sucht `grep "join(root," / "join(wurzel,"` über das **gesamte** Repo und zieht jede Fundstelle nach oder begründet sie. Zweite Lehre: **Ein leeres Werkzeugergebnis ist kein Beweis für „nichts zu tun."** Wo ein Statusdokument eine Erwartung formuliert, wird sie gegen die Werkzeugausgabe geprüft, nicht abgeschrieben.*

*Lesson 2026-08-16 (aus pm/N-0020, B029): **Eine Ticketnummer in einem Beschluss zu nennen, ist keine Beauftragung.** `pm/D005` kündigte den Pool-Knopf „als CR T-0011" an; die Nummer wurde danach von einem anderen Vorgang belegt, und die Zusage verschwand geräuschlos — bis der Auftraggeber zum zweiten Mal danach fragte. Ab sofort: Jeder Beschluss, der Arbeit ankündigt, wird in derselben Session mit einem **real angelegten** Ticket belegt; Nummern werden nie vorab vergeben. Verwandte Lehre zu B025: Auch hier meldete kein Werkzeug einen Fehler — es gab schlicht nichts Offenes, das hätte auffallen können.*

*Lesson 2026-08-16 (aus P10 Sprint 1, B033): **Ein zweiter Zugang ist noch kein zweites Regelwerk.** Beim Bau des HMI-Schreibpfads war der bequeme Weg, im Server „schnell" zu validieren — das hätte die Prüfregeln ein zweites Mal geführt (Risiko R2 des Sprint-0-Plans). Stattdessen liegt der Schreibpfad in `board.py`; das Backend ist Fassade. Beim Hinschauen fiel auf, dass dieselbe Falle schon zugeschnappt war: Die Zeitstempel-Formatierung (SWR-084) hätte für die Änderungshistorie ein zweites Mal entstehen müssen — jetzt delegiert `inbox` an `board.zeitpunkt`. DoD-Prüffrage beim Bau eines neuen Zugangs: **„Welche Regel wäre ich versucht, hier noch einmal zu schreiben — und wo steht sie schon?"***

*Lesson 2026-08-16 (aus pm/T-0024, B038): **Ein Fallback, der die Ursache verschweigt, ist eine Falschaussage mit Zeitverzögerung.** `except Exception: return True` war als Vorsicht gemeint und richtig gedacht — die Meldung, die daraus entstand („Git-Prozess aktiv"), war aber eine Behauptung über die Welt, die niemand mehr anzweifelte, weil sie wie eine Messung klang. Verwandt zu B025 (ein leeres Werkzeugergebnis ist kein Beweis) und pm/T-0023 (ein Werkzeug, das nur beschreibt, hat die halbe Arbeit getan) — diesmal war es kein leeres, sondern ein **plausibel klingendes falsches** Ergebnis. DoD-Prüffrage für Fallbacks: **„Wenn dieser Zweig greift — steht danach im Protokoll, dass geraten wurde, oder liest es sich wie eine Messung?"***

*Lesson 2026-08-16 (aus B038, zweiter Teil): **Der stille Ausfall einer Automatik ist teurer als ihr lauter.** Der Wächter brach zwei Stunden lang alle 15 Minuten ab und meldete das ausschließlich in eine Logdatei, die ohne Anlass niemand liest. Nach außen sah alles normal aus — Sessions liefen, committeten, meldeten STARTKLAR. Der einzige sichtbare Hinweis war, dass zwei Tickets nicht weiterkamen, und bemerkt hat ihn **der Auftraggeber**. DoD-Prüffrage für Automatiken: **„Wo wird ein Fehlschlag sichtbar für jemanden, der nicht danach sucht?"***

*Lesson 2026-08-16 (aus B038, dritter Teil): **Ein Test, der die Umgebung befragt, prüft die Umgebung.** `test_nur_locks_laesst_repos_unberuehrt` legte ein Fake-Repo in %TEMP% an und fragte über `git_prozess_aktiv()` den **gesamten Rechner** nach laufenden Git-Prozessen — ein Commit aus dem HMI oder der Wächter selbst genügten, um ihn rot zu machen und `abschluss.cmd` mitzureißen. Hermetik war am 15.08. schon einmal SUP.9-Befund. DoD-Prüffrage: **„Welche Aussage dieses Tests hängt an etwas, das außerhalb seines Temp-Ordners passiert?"***

*Einsprüche des Menschen gegen Agenda-Prioritäten: einfach im Briefkasten/Chat hinterlassen — wird als neue Log-Zeile verbucht.*
