# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Sprint 36, 2026-08-22 — **die Shell ist zurück**)

1. **Sprint 36 läuft** (`s36-2026-08-22-1300`). Sprint 35 war vom Host bereits geschlossen,
   Schritt 0 (zehn Tickets auf `geplant_sprint: 36`) beim Start **schon erledigt** —
   `--beginne` lief ohne Befundlawine. Die Warnung der letzten drei Läufe hat getragen.
2. **⚠⚠ Der teuerste Fund: zwei fertige Nachweise lagen ungelesen im Haus.**
   Der Ollama-Tick (`status: ok`, `gemma3:27b`, 2 Artefakte) seit **21.08. 20:59**, die
   Entscheidung `pm/D030` = C seit **22.08. 00:23**. Beide zusammen haben **fünf** Tickets
   freigegeben, sobald sie jemand gelesen hat. **Gefunden hat beides nicht die Planung,
   sondern je eine Zusicherung.**
   > **Der Sprintanfang liest ab jetzt zuerst Run-Registry und Decision-Log — die Belege,
   > die seit dem letzten Lauf von allein entstanden sind** (`L-2026-08-22a`, `-c`;
   > `pl.md` Lehren 13/14).
3. **`team-termine/T-0001` hat zehn Tickets entsperrt.** Der Projektplan war ein Template
   mit Platzhaltern und damit der Engpass der ganzen Einheit. Jetzt v1.0 vollständig.
   ⚠ Status `in_review`, nicht `done` — das QM-Review steht aus. **Die Sperren fielen
   trotzdem**, weil sie am Werkstück hängen, nicht am Status.
4. **⚠ Ein Verstoß dieses Laufs steht in der Historie.** `platform/T-0068`
   `open -> in_review` ohne `in_progress` (Commit `04da965`): `board.py` meldete den
   Fehler, `git commit` lief mit `;` daneben trotzdem durch. `test_uebergang_historie`
   bleibt bis zum Sprintende rot. **Prüfen und Verbuchen gehören mit `&&` in dieselbe
   Kette** (`L-2026-08-22d`, `dev.md` Lehre 8).
5. **⚠ Der Wächter ist tot, die Bewachten leben.** Letzter Herzschlag **21.08. 23:25**
   (~14 h), während `abschluss-auto` und `ollama-schnelltakt` um 12:55/12:56 schrieben.
   Sein eingefrorener Status behauptet weiter „kein laufender Sprint". Steht in
   `platform/T-0055` (vierte Berührung → geschnitten).
6. **Zahlen (gemessen):** offen **38 → 37**, `wartet_auf_mensch` **1 → 0**, Briefkasten
   Start **0/69** → Ende **0/70** (ein Brief kam im Lauf an), Teststrecke **109 Module /
   1553 Zusicherungen**, **1 rot** (selbst verursacht), `trace_matrix` **213 SWR / 0
   Lücken**, `organigramm --check` **grün**. Ollama-Offload **0 / Ersparnis 0**.

### Erste Aufgaben des Folgelaufs

1. **Run-Registry und Decision-Log lesen, bevor geplant wird** — die neue Pflicht aus
   Punkt 2. Nicht als Kür, sondern als Schritt 1b nach dem Briefkasten.
2. **Den einen offenen Preflight-Befund identifizieren**, an dem der Schnelltakt des Hosts
   zuletzt abbrach (`PREFLIGHT: 1 Befund(e)`). Dieser Lauf hat ihn **nicht** gefunden —
   `preflight` lief in die Zeitgrenze der Sandbox.
3. **`team-dashboard/T-0007`** (Post-Widget, Brief des Auftraggebers) — Prio hoch, und der
   Auftraggeber wartet auf ein sichtbares Ergebnis.
4. **Die zehn entsperrten `team-termine`-Tickets** — die Rollen-Initialisierung von P16 ist
   seit heute arbeitsfähig und war es nie zuvor.
5. **`team-mail/T-0006` bauen** (vierte Berührung, Entscheidung **BAUEN**).

⚠ **Die zwei vom Ollama-Modell geschriebenen Artefakte** (`skills/sup9-problemmanagement/
SKILL.md`, `templates/issues/problem.md`) hat **niemand gelesen**. Das gehört zu
`promt-team/T-0012`, nicht in den Abschluss von `T-0060`.

---

<details><summary>Archiv: Sprint 35 und früher</summary>

# Session-Agenda (PM-Team, je Session gepflegt — SLA: immer aktuell)

## Das Wichtigste (Folgelauf 2026-08-21 — **wieder kein Sprint 36**)

1. **Die Shell ist zum zweiten Lauf in Folge ausgefallen** (vier identische Startfehler,
   `useradd`/ENOSPC-Familie). Kein `git`, kein `board.py`, kein `preflight`, keine Tests,
   kein Ollama-Tick, kein `sprint_register.py`. **Sprint 35 bleibt im Register offen**
   (`s35-2026-08-21-1450`) — nach `SWR-136` hätte `beginne()` einen Sprint 36 ohnehin
   verweigert. **Wieder bewusst nichts gebaut, geschlossen oder terminiert.**
2. **⚠⚠ Der Ertrag ist ein Blocker, den wir zum ersten Mal VOR seinem Einsatz sehen.**
   Der Abschluss von Sprint 35 hat **neun Tickets in Prosa nach Sprint 36 verschoben** —
   und **kein einziges Ticket trägt es**. Alle stehen auf `geplant_sprint: 35`, dazu
   `platform/T-0060` (`in_review`): **zehn**. Heute still, weil `sprint_vergangen`
   (SWR-112) gegen den **laufenden** Sprint vergleicht.
   > **Nach `--beende` und `--beginne` meldet die Prüfung alle zehn — und der Schnelltakt
   > bricht zum dritten Mal in Folge an unserem eigenen Abschluss ab. Diesmal wissen wir
   > es vorher.**
   ⚠ Vom Gegenlesen korrigiert: **ein** Befund mit zehn genannten Tickets, nicht zehn
   Befunde; für den Exit-Code gleichwertig, für jede Zählung nicht.
   **Behandlung:** in `sprint-aktuell.md` als **Schritt 0** vor `--beende` eingetragen —
   nicht angehängt, sondern **vor** die bestehende Liste gestellt.
3. **⚠ Zweiter Befund: neun von elf geräumt.** `team-termine/T-0011` und `T-0012` stehen
   auf `open` **und** tragen `blocked_by` — genau der Widerspruch, den Sprint 35 für
   `T-0002…T-0010` auflöste. Und **keine Prüfung** findet den Rest: `board.validiere`
   prüft nur `blocked` **ohne** `blocked_by`, nie die Gegenrichtung.
   > **Eine Regel, die von Hand auf neun Fälle angewandt und nicht als Prüfung gebaut
   > wird, ist beim zehnten wieder weg.**
4. **⚠⚠ Beides wurde NICHT repariert — und der Grund ist der wertvollste Teil des Laufs.**
   `preflight.ist_verifikationsquelle` nennt drei Sorten Datei, die eine Verifikation
   liest: `BOARD.md`, `software-requirements.md` und **jede** Datei unter `*/tickets/`.
   Eine geänderte, nicht committete Verifikationsquelle **ist** ein Preflight-Befund.
   > **Ohne `git` verwandelt jede Ticket-Änderung Arbeit in einen neuen Takt-Blocker.
   > Zehn Tickets richtigzustellen hieße, zehn Befunde anzulegen, um zehn zu vermeiden.**
   Damit hat `L-2026-08-21db` erstmals eine **nachlesbare Grenze** statt eines Gefühls
   (`L-2026-08-21dp` und `dq`, verankert mit `## L-`-Kopf in
   `process/knowledge/pl/lessons.md`, dazu `process/roles/pl.md` Punkte 11–12).
   ⚠ „Frei" heißt nicht „folgenlos": `sprint-aktuell.md` wird von `plandrift`,
   `statusdrift` und `test_berichtskennzahlen` gelesen — **Plantabelle und
   Kennzahlenblock blieben deshalb unangetastet**.
5. **⚠ Das Gegenlesen hat vier Fehler in dieser eigenen Arbeit gefunden, keinen davon der
   Autor** — fünfter Lauf in Folge. Darunter eine Zahl („zehn Befunde"), eine
   Reihenfolge (`--beginne` allein genügt nicht) und eine **richtige Antwort aus dem
   falschen Grund** (die zwei Wurzeldateien). Alle vier oben eingearbeitet statt
   stillschweigend geglättet.
   > **Und ein Befund über das Gegenlesen selbst: es meldete unsere neue Lehren-ID als
   > „bereits vergeben" — gelesen hatte es die Dateien, die derselbe Lauf gerade
   > geschrieben hatte. Eine Prüfung gegen die Arbeitskopie kann „vergeben" nicht von
   > „soeben von dir vergeben" unterscheiden.**
6. **Zahlen (gemessen):** Briefkasten **0 offen** (69 Briefe, beide Ebenen), offene
   Aufgaben **34** = **20 `open` + 13 `blocked` + 1 `in_review`** — ⚠ der Vorlauf nannte
   „22 + 12": **gleiche Summe, andere Aufteilung**, die 13 sind namentlich belegt.
   Ollama-Offload **0 delegiert / Ersparnis 0**. **Tests, Trace-Matrix, Organigramm,
   `board --check` und `preflight` sind nicht gelaufen und werden deshalb nicht als Zahl
   behauptet.**

### Erste Aufgabe des Folgelaufs

**Schritt 0 aus `sprint-aktuell.md` zuerst** — die zehn Tickets auf `geplant_sprint: 36`
nachziehen —, **dann** Sprint 35 schließen, die Reste aus `PUSH-ANFORDERUNG.txt`
verbuchen, `preflight` fahren und den Takt nachmessen. Die Reihenfolge ist der Punkt:
umgekehrt erzeugt Schritt 1 zehn Befunde, die Schritt 0 verhindert hätte.

---


</details>
<details><summary>Archiv: Lauf ~16:4x</summary>

## Das Wichtigste (Lauf 2026-08-21 ~16:4x — **kein Sprint 36**)

1. **Die Shell dieser Session war durchgehend ausgefallen** (fünf identische Startfehler).
   Ohne sie: kein `git`, kein `board.py`, kein `preflight`, keine Tests, kein Ollama-Tick,
   kein `sprint_register.py`. **Sprint 35 ist im Register weiterhin offen**
   (`s35-2026-08-21-1450`) — nach `SWR-136` hätte `beginne()` einen Sprint 36 ohnehin
   verweigert. **Bewusst nichts gebaut, geschlossen oder terminiert.**
2. **⚠⚠ Der Schnelltakt ist wieder blockiert, und wieder durch uns.** Gemessen aus
   `ollama-schnelltakt.log` (Lauf 21.08. 16:01:20): `PREFLIGHT: 3 Befund(e)` →
   `Tick abgebrochen`. **Alle drei stammen aus dem Abschluss von Sprint 35**: zwei
   unverbuchte Dateien (`p9/.../software-requirements.md`, `pm/tickets/T-0085.md`) und
   eine Planzeile, die `pm/T-0085` auf Sprint 35 führte, während das Ticket
   `geplant_sprint: 36` trägt.
   > **Zum zweiten Mal in Folge sperrt unser eigener Abschluss den Takt, den derselbe
   > Sprint entsperrt hat. Die Sperre trägt wieder den Namen der Sorgfalt.**
3. **✅ Behoben wurde genau der Befund, den `abschluss.cmd` NICHT gelöst hätte** — die
   Planzeile. Ein Commit der falschen Zeile hätte den Befund mitgenommen. Die anderen
   beiden brauchen `git` auf dem Host.
   > **`L-2026-08-21db`: Fällt ein Werkzeug aus, ist die nützlichste Arbeit die Teilmenge
   > der Blockade, die das Werkzeug ohnehin nicht gelöst hätte.** Verankert in
   > `process/roles/pl.md` (Lehren 8–10) und `pm/docs/historie.md`.
4. **⚠ Ehrliche Grenze:** die Korrektur ist **nicht nachgemessen** — `preflight` konnte
   nicht laufen. Dass der nächste Takt `STARTKLAR` meldet, ist eine **Erwartung, keine
   Messung**.
5. **Zahlen (gemessen):** Briefkasten **0 offen** (69 Briefe, kein `status: offen`),
   offene Aufgaben **34** (22 `open`, 12 `blocked`), Preflight **3 Befunde / 10
   fortgeschrieben**, Ollama-Offload **0 delegiert / Ersparnis 0** (`pm/T-0071` ohne Tick
   mit `status ok` + Artefakt). **Tests, Trace-Matrix und Organigramm sind nicht gelaufen
   und werden deshalb nicht als Zahl behauptet.**

### Erste Aufgabe des Folgelaufs

Vor jeder neuen Planung: **Sprint 35 im Register schließen**, die Reste aus
`PUSH-ANFORDERUNG.txt` verbuchen, `preflight` fahren und den Takt nachmessen.

⚠ **Vom Folgelauf korrigiert:** diese Reihenfolge war unvollständig — vor dem Schließen
müssen die zehn Tickets auf `geplant_sprint: 36` nachgezogen werden, sonst erzeugt der
Sprintstart zehn `sprint_vergangen`-Befunde (siehe oben, Punkt 2).

</details>

---

<details><summary>Archiv: Sprint 34</summary>

## Das Wichtigste (Sprint 34, 2026-08-21)

1. **✅ Sechs Aufgaben geschlossen, sechs verschoben, ein Projekt gegründet** — und der
   Ertrag steckt in zwei Funden, die niemand geplant hatte.
2. **⚠⚠⚠ 91 Lehren waren GELÖSCHT — und unser Wächter hat es als FORTSCHRITT gemeldet.**
   Der Abschluss-Commit von Sprint 32 trägt die Worte *„Lehren verankert"* im Betreff und
   hat dabei **91 Lehr-Abschnitte entfernt**: zwei Dateien wurden **geschrieben** statt
   **angehängt**. 90 davon hatten heute nirgends mehr einen Kopf.
   > **Ein Bestand kann verschwinden, während sein Wächter Erfolg meldet. Unsere Prüfung
   > konnte „Fortschritt" nicht von „Gegenstand weg" unterscheiden und nannte beides beim
   > Namen des angenehmeren Falls.**
   ⚠ Und **unsere Erklärung aus Sprint 33 war ebenfalls falsch**: wir hatten geschlossen,
   die Lehren hätten *„nie in einem Lehrbuch gelebt"*. Zwei Sprints hintereinander trug
   dieselbe Lücke eine falsche Erklärung — weil wir beide Male den **Bestand** gezählt
   haben und nie die **Geschichte der Datei**.
   **Alles wiederhergestellt.** Der Beweis ist eine Zahl, die niemand gewählt hat:
   `ohne_vertreter` liefert wieder **exakt die 91** aus Sprint 31, in beide Richtungen leer.
   > **Und gerettet hat sie die Zurückhaltung von Sprint 33 — dort steht wörtlich, die
   > Liste nachzuziehen hätte „die Zusicherung in einer Minute grün gemacht und den Befund
   > gelöscht". Genau das hätte 90 Lehren endgültig gekostet.**
3. **⚠⚠ Das Gegenlesen hat SIEBEN Fehler in unserer fertig gemeldeten Arbeit gefunden.
   Keinen davon wir selbst.** Dritter Sprint in Folge. Der bitterste: **derselbe Bau, der
   eine Doppelung BENENNT, hat eine neue angelegt** — mit einem Kommentar, der die
   Gleichheit zweier Listen *behauptet*.
   > **Ein Kommentar behauptet. `assertIs` stellt her.**
   Der teuerste: eine Anforderung verlangte drei Dinge und sicherte zwei —
   **der ungeprüfte Halbsatz war genau der, dessen Fehlen schon einmal Schaden angerichtet
   hatte.**
4. **⚠⚠ Beim Gründen deines Projekts `team-termine` ist aufgefallen, dass unser
   Gründungswerkzeug die Datenklasse nur BESCHRIFTET hat.** Es nahm „sensibel" entgegen,
   prüfte es — und legte das Projekt trotzdem in ein Repo **mit** GitHub-Remote, das wir
   bei jedem Lauf pushen. Der Kalender deiner Familie wäre mitgegangen.
   > **Eine Datenklasse, die nur beschriftet und nicht platziert, ist keine Schranke,
   > sondern eine Aufschrift — und sie stand in einem Kommentar, also an der einzigen
   > Stelle, die kein Werkzeug von uns liest.**
   ⚠ Nebenbefund am echten Bestand: `p13` war seit seiner Freigabe **ohne Mannschaft** —
   sein Steckbrief trug keinen Status, und unser Resolver überspringt Einheiten ohne
   Status stillschweigend. Repariert; `p13` hat jetzt seine 10 Rollen.
5. **⚠ Eine Abnahme, die du erteilt hast, war vier Tage lang ohne Gegenstand.** Du hast am
   17.08. um 21:57 die Baseline `p12-v1.0` abgenommen — der Tag wurde nie gesetzt.
   Nachgetragen, und zwar auf den Stand von damals und **nicht** auf heute.
6. **Zahlen:** Anforderungen **211 / 0 Lücken**, Tests **1529** in **107** Dateien — in
   Blöcken gefahren, **1496 grün**, ⚠ **zwei Module ungeprüft** (Zeitlimit der Sandbox),
   JS **114**, Organigramm grün (21 Dateien), Briefkasten **0 offen** (am **Ende** gemessen),
   offene Aufgaben **33** (davon 12 aus dem neuen Projekt), auf dich wartend **0**.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`abschluss.cmd` ausführen** | **Der wichtigste Punkt, und er wächst weiter: fünf Tage plus sieben komplette Sprints.** Wir pushen nie selbst. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Dein Projekt `team-termine` steht** | Gegründet als **P16**, mit Auftrag, Abgrenzung, Sprint-0-Plan und 12 Aufgaben. ⚠ **Es liegt bewusst NICHT in `projects/`**, sondern als eigenes Repo **ohne GitHub-Remote** — wie `team-mail`. Der Kalender deiner Familie geht nirgendwohin. **Die Zugangsdaten sind dein nächster Schritt**; sie blockieren das Widget nicht. |
| ✅ **Dein Brief zum Post-Widget ist umgesetzt** | Deine drei Antworten von 12:26 haben es entsperrt, gebaut ist es im selben Lauf. ⚠ **Eine Kachel deiner Vorlage können wir nicht füllen:** für **SPAM** führt dein Digest keine Rubrik. Wir haben dort **keine 0** hingeschrieben — eine 0 hieße „kein Spam". **Sag einmal Bescheid, wenn du die Zahl willst**, dann bekommt der Digest die Rubrik. ⚠ Das **Aufklappen** kommt in Sprint 35 (erster Punkt, an dem die Oberfläche das PIN-Gate benutzt). |
| ⚠ **Dein Ollama-Takt: die Diagnose ist wieder eine andere — und diesmal ehrlich zu Ende gemessen** | Sprint 33 sagte „kein Versuch seit der Reparatur". Jetzt gemessen: **wir können es aus unserer Umgebung gar nicht erreichen** (`localhost:11434` tot, `host.docker.internal` von der Netz-Allowlist gesperrt). Der Nachweis braucht **deinen** Rechner, nicht unsere Sandbox. Vier Aufgaben hängen daran — beim nächsten Anlauf **entscheiden** wir statt zu verschieben. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **12286 Dateien** (Stand 13:0x). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-**Versand**daten (`team-mail/N-0003`) — dein **ältester** offener Punkt, seit Sprint 21. Dazu deine Zählung der Kacheln im Reiter „Dashboard". |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens: wir haben denselben Fehler gemacht, den wir eine Stunde vorher aufgeschrieben
hatten.** Beim Fortschreiben eines Tickets haben wir die Datei **überschrieben** statt
angehängt — genau der Vorgang, der die 91 Lehren gekostet hat. Die Lehre zu kennen hat
nicht gereicht; sie hatte an dieser Stelle keine Prüfung.

**Zweitens: unser Werkzeug hat den Fehler gemeldet, und wir haben ihm die Stimme
genommen.** Unsere erste Erklärung lautete, `board.py` sehe ein kaputtes Ticket gar nicht.
Nachgemessen: es sah es und nannte den Dateinamen. Der Aufruf lief mit weggeworfener
Ausgabe.

> **Eine Prüfung, deren Ausgabe man wegwirft, ist teurer als keine — sie erzeugt den
> Eindruck, geprüft zu haben.**

**Drittens: unsere eigene Kennzahl hat deinen Brief nicht gesehen.** `briefe_im_lauf`
meldet **0**; eingegangen ist **1**. Sie liest nur, wann ein Brief **angelegt** wurde, und
du hast in einen **vorhandenen** geschrieben. Die Zahl steht im Bericht **falsch und
danebengestellt richtig** — sie stillschweigend zu korrigieren hätte den Befund gelöscht.

---

</details>

<details><summary>Archiv: Sprint 33</summary>

, 2026-08-21)

1. **✅ Drei Aufgaben erledigt, acht verschoben — und die Verschiebung hat einen Grund,
   der kein Wort für „keine Zeit" ist.**
2. **⚠⚠ Zum zweiten Mal in Folge ist der Ertrag das GEGENLESEN und nicht der Bau — und
   diesmal hat es eine ANFORDERUNG umgedreht.** Wir hatten drei Aufgaben gebaut,
   abgesichert und für fertig erklärt. Ein unabhängiger Leser hat darin **drei ernste
   Fehler** gefunden. Keinen davon haben wir selbst gefunden.
   Der schwerste: wir haben zwei Uhren verglichen, die verschieden ticken — die Briefe
   tragen Weltzeit, unser Sprintzähler die Uhr des Rechners. **Zwei Stunden Unterschied,
   länger als ein ganzer Sprint.**
   > **Eine Zeitzone ist keine Formatfrage, sondern eine Maßeinheit. Und eine falsche
   > Messung, die eine KORREKTUR behauptet, ist teurer als gar keine — sie überschreibt
   > die richtige Aussage und begründet das auch noch.**
   Wir hatten damit ein eigenes Ticket „korrigiert", das die ganze Zeit **recht** hatte,
   und diese falsche Behauptung stand bereits in einer Anforderung.
3. **⚠⚠ Sie haben WÄHREND des Laufs geantwortet — zum vierten Mal an einem Tag, diesmal
   nach 47 Minuten bei sieben Tagen Frist.** Und Ihre Antwort hat unsere Ausnahmeliste
   **leer** gemacht, vier Stunden nachdem sie entstand.
   > **Eine Ausnahmeliste, die man leer bekommt, war die richtige Bauform. Der vierte
   > Aufgaben-Zustand, den wir stattdessen hätten bauen können, wäre für immer geblieben.**
   ⚠ **Und Sie hatten inhaltlich recht:** unsere Ollama-Diagnose war fünf Sprints alt.
   Alle 11 Fehlschläge liegen **vor** der Reparatur vom 20.08. um 20:45 — seither hat es
   **keinen einzigen Versuch** gegeben, und der eine erfolgreiche Lauf trug `gemma3:27b`.
   > **Eine Fehlerliste ohne Zeitachse ist keine Diagnose, sondern ein Archiv, das sich
   > wie ein Befund liest.**
4. **⚠⚠ Beide Zählungen dieses Laufs haben ihr eigenes Ticket umgestellt.** Die Frage war
   „brauchen wir einen vierten Aufgaben-Zustand für drei Fälle?". Gezählt: **acht**
   Verweise — und **kein einziger** gesperrter Vorgang im ganzen Haus zeigte auf etwas
   Offenes, obwohl unsere Regel genau das verlangt.
   > **Der Befund war nicht „uns fehlt ein Zustand", sondern „eine Sperre wird nie
   > zurückgenommen, weil nichts danach fragt". Die Hälfte war Altpapier.**
5. **⚠ Eine Zusage von uns hatte keinen Leser.** Die Gründung Ihres Projekts
   `team-termine` stand als „nächster Schritt" im Schlussabsatz einer **geschlossenen**
   Aufgabe — mit Nummer, aber ohne Aufgabe dahinter. Jetzt angelegt (`pm/T-0083`).
6. **Zahlen:** Anforderungen **206 / 0 Lücken**, Tests **1480** in **101** Dateien,
   Organigramm grün (20 Dateien), Briefkasten **0 offen** (am **Ende** gemessen), offene
   Aufgaben **20**, auf Sie wartend **0**.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`abschluss.cmd` ausführen** | **Der wichtigste Punkt, und er wächst weiter: fünf Tage plus sechs komplette Sprints.** Wir pushen nie selbst. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Nichts wartet gerade auf dich** | Alle drei Entscheidungen von heute sind verbucht, der Briefkasten ist leer. **Frei zum Lesen statt zum Antworten.** |
| ⚠ **Dein Ollama-Takt: eine gute Nachricht und eine ehrliche** | Gut: dein Hinweis auf `gemma3:27b` stimmt, und das Modellproblem ist seit dem 20.08. abends repariert. Ehrlich: **wir haben es seitdem kein einziges Mal ausprobiert** und trotzdem fünf Sprints lang „Modell fehlt" berichtet. Der nächste Schritt ist **ein** echter Lauf (`platform/T-0060`) — der braucht deinen Rechner, nicht unsere Sandbox. ⚠ Der Takt bricht derzeit an **Preflight-Befunden** ab, nicht am Modell — zwei verschiedene Ursachen, die wir bisher vermischt haben. |
| ⚠ **Dein Projekt `team-termine` startet im nächsten Lauf** | `pm/T-0083`. Verschoben, weil dieser Lauf drei eigene Fehler reparieren musste — eine Projektgründung nebenbei wäre genau die Reihenfolge, die den Sprint teuer gemacht hat. Die **Zugangsdaten** für den Kalender bleiben dein Punkt. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11830 Dateien** (Stand 11:18). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-**Versand**daten (`team-mail/N-0003`) — ⚠ präzisiert: das **Lesen** läuft seit Sprint 21, offen ist nur der **Versand**. Dazu deine Zählung der Kacheln im Reiter „Dashboard". |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens: unsere Prüfung war durch ihren eigenen Erklärtext erfüllt.** Sie suchte einen
Namen im Quelltext — und der Name stand im Kommentar darüber. **Anwesenheit ist nicht
Verwendung.** Eine zweite verglich eine leere Liste mit einer leeren Liste und wäre auch
dann grün geblieben, wenn das ganze Haus unlesbar gewesen wäre.

**Zweitens: wir haben eine ganze Datei von einer Prüfung ausgenommen.** Deshalb konnten wir
den **fünften** Namen für denselben Begriff nicht finden — er stand ausgerechnet in der
ausgenommenen Datei. **Eine Ausnahme für eine ganze Datei ist keine Ausnahme, sondern ein
blinder Fleck an der teuersten Stelle.**

**Drittens: von 119 Lehren stehen 84 in keinem Lehrbuch.** Sie leben nur als Zitat in
Berichten — dort findet sie niemand, der nach Lehren sucht. Unsere Kennzahl „Lehren" zählt
die Zitate, unsere Prüfung zählt die Einträge im Buch: **zwei Zahlen unter einem Namen.**
Aufgeschrieben als `platform/T-0061` und ausdrücklich **nicht** stillgelegt — eine Zeile
Änderung hätte die Prüfung grün gemacht und den Befund gelöscht.

> **Eine Lehre, die nur im Abschlussbericht steht, ist eine Erinnerung an einen Sprint.
> Erst im Lehrbuch ist sie eine Regel für den nächsten.**

---

</details>

<details><summary>Archiv: Sprint 32</summary>


## Das Wichtigste (Sprint 32, 2026-08-21)

1. **✅ Zwei Aufgaben erledigt, keine verschoben** — beide waren letzten Sprint für
   „diesmal" angekündigt und sind diesmal gebaut.
2. **⚠⚠ Der eigentliche Ertrag dieses Laufs ist, dass unsere eigene Prüfung uns erwischt
   hat — vier Mal, und jedes Mal schwer.** Wir haben eine Reparatur gebaut, sie selbst
   für fertig gehalten, und **ein unabhängiges Gegenlesen** hat vier ernste Fehler darin
   gefunden. Der schlimmste: unsere Ausnahme galt immer dann, wenn *irgendein* Sprint
   läuft — und während gearbeitet wird, läuft immer einer.
   > **Eine Bedingung, die während der ganzen Arbeitszeit wahr ist, ist keine Bedingung.
   > Sie ist ein offenes Tor mit einer Aufschrift.**
   Dazu ein Schlupfloch: wer eine unbequeme Aufgabe **verwirft**, hätte damit die Meldung
   losgewerden können. Alles behoben und am echten Bestand gegengeprüft.
3. **⚠⚠ Sie haben während des Laufs beide offenen Fragen beantwortet — und das ist die
   dritte Messung derselben Sache.** `T-0077` stand **vier Sprints** in einer
   Empfehlungsliste und wurde nicht beantwortet. Als es zum ersten Mal als **Frage mit
   Optionen, Frist und Voreinstellung** dastand, war es in **sieben Minuten** entschieden
   — bei sieben Tagen Frist.
   > **Fragen ist billiger als Ausweichen. Und den Preis des Ausweichens zahlt nicht der,
   > der fragt.**
4. **⚠⚠ Sieben Briefe kamen WÄHREND des Laufs — und unser Haken „Briefkasten erfüllt"
   stand da schon.** Beim Start: 0 offen, richtig gemessen. Beim Abschluss: 7. Alle
   beantwortet und einsortiert, aber:
   > **„Briefkasten zuerst" ist eine Reihenfolge und keine Zusage. Was am Anfang gemessen
   > und am Ende berichtet wird, ist eine Momentaufnahme in der Aufmachung einer Garantie.**
   ⚠ **Und dieselbe Nachlässigkeit ein zweites Mal im selben Lauf:** unsere Sichtung der
   offenen Aufgaben hat die verschachtelten Projekte nicht mitgelesen — **Ihre p13-Freigabe
   ist uns dadurch in der Planung entgangen.** Gefunden hat es die Schlussrechnung, nicht
   die Planung.
5. **⚠ Ihre Antwort A hat eine Lage erzeugt, für die wir keinen Zustand haben.** Drei
   Aufgaben warteten auf `T-0077`. Jetzt ist entschieden — aber die Antwort war „alles
   bleibt", also besteht der Grund fort. „Gesperrt" passt nicht mehr, ein Termin wäre
   eine Zusage ohne Arbeit, und Schließen wäre Ihre Option C gewesen, die Sie nicht
   gewählt haben. **Zum dritten Mal in drei Sprints liegt der Fehler zwischen zwei
   richtigen Regeln.** Aufgeschrieben statt schnell übermalt.
6. **Zahlen:** Anforderungen **202 / 0 Lücken**, Organigramm grün (20 Dateien),
   Briefkasten **0 offen** (am **Ende** gemessen, nicht am Anfang), Workflows **6 / 0
   unabgedeckt**, Work Products **56 / 0 Lücken**, offene Aufgaben **21** — und diese Zahl
   sagen unsere Werkzeuge ab jetzt wieder **einstimmig** (letzten Sprint waren es 9
   gegen 12).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`abschluss.cmd` ausführen** | **Der wichtigste Punkt, und er ist gewachsen: fünf Tage plus fünf komplette Sprints.** Du hast selbst gefragt, ob der Auto-Commit klemmt — er klemmt nicht, er **darf** nicht: wir pushen nie selbst. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ⚠⚠ **Zwei neue Fragen an dich, Frist 28.08.** | **`pm/T-0078`** — dein Projekt `team-termine`: Gründung ist Klasse A, und du willst **in einen fremden Kalender schreiben** (`dimitri.john83@…`). Default **A** = Projekt startet, Kalender **nur lesend**. **`pm/T-0081`** — dein Digest-Brief nennt **zwei** Empfängeradressen, Guardrail 1 erlaubt **eine**. Default **A** = Guardrail bleibt. ⚠ In beiden Fällen genügt Schweigen, und **das Widget bzw. der Digest wird trotzdem gebaut** — nur der letzte Schritt wartet. |
| ✅ **Deine sieben Briefe sind alle beantwortet** | In derselben Datei, mit Einordnung. Umgesetzt wird ab Sprint 33 — Grund für die Verschiebung ist die **Ankunftszeit** (06:32–07:03, nach unserem Durchgang), nicht Kapazität. |
| ⚠ **Dein Ollama-Takt: entschieden ist A** | Er läuft weiter und meldet ehrlich Leerlauf. **Kein Ticket wurde an Ollama delegiert, Token-Ersparnis 0** — gemessen, nicht geschätzt: alle Ollama-Läufe stehen auf `fehler` (`model 'llama3.1:8b' not found`). ⚠ Falls du das ändern willst, wäre `ollama pull llama3.1:8b` oder ein Register-Eintrag der nächste Schritt — dein alter Punkt „`ollama list`" ist damit immer noch offen. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11612 Dateien** (Stand 09:07). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`) — dein **ältester** offener Punkt, seit Sprint 21, und er blockiert jetzt zusätzlich deinen Digest-Wunsch. Dazu deine Zählung der Kacheln im Reiter „Dashboard". |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens: unsere Reparatur war kaputt, und unsere eigenen Prüfungen haben es nicht
gemerkt.** Wir haben sechs Zusicherungen geschrieben, alle grün. Ein unabhängiges
Gegenlesen hat dann die komplette Verdrahtung **entfernt** — und alle sechs blieben grün,
weil sie die Funktion direkt aufriefen statt den Betrieb. **Eine Prüfung, die nur die
Funktion kennt, sagt nichts darüber, ob sie jemals aufgerufen wird.**

**Zweitens: zwei unserer Prüfer hatten genau den Fehler, den sie prüfen.** Der eine
prüfte, ob eine Regel *dasteht*, statt ob sie *benutzt* wird — und blieb grün, während
drei Zeilen darüber die alte Fassung weiterlief. Der andere schlug gegen seine **eigene
Erklärung** an, weil dort das schlechte Beispiel zitiert steht.

**Drittens: wir haben zweimal im selben Lauf zu eng gesucht.** Beim Briefkasten und bei
den offenen Aufgaben hat unser Handlauf die verschachtelten Projekte nicht mitgelesen,
während unser Werkzeug es tut. Beim Briefkasten ist nichts passiert; bei den Aufgaben ist
**deine p13-Freigabe** durchgerutscht. **Zwei Wege, dieselbe Frage, verschieden weit — und
der engere war der, den wir von Hand gegangen sind.**

---

</details>

<details><summary>Archiv: Sprint 31</summary>

## Das Wichtigste (Sprint 31, 2026-08-21)

1. **✅ Drei Aufgaben erledigt, keine verschoben.** Darunter beide, die letzter Sprint
   ausdrücklich für „diesmal" angekündigt hatte, und eine, die zum **vierten** Mal
   drankam und deshalb entschieden werden **musste**.
2. **⚠⚠ Dreimal an einem Tag lag der Fehler nicht in einer Prüfung, sondern zwischen
   zweien — und das ist der eigentliche Ertrag dieses Laufs.**
   Für eine **gesperrte** Aufgabe gab es bisher **keinen** zulässigen Termin: ein alter
   Termin war ein Fehler, kein Termin war ein Fehler, und ruhig blieb es nur mit einer
   Zusage, die das Team gar nicht halten kann.
   > **Eine Lage, in der die bequeme Handlung die einzige ist, die grün macht, ist genau
   > die Bauart, die uns 83 abgebrochene Läufe gekostet hat.**
   Die Ausnahme gab es längst — sie hing nur an der falschen Sorte Merkmal. **Repariert
   und am echten Bestand nachgemessen**, nicht im Test: drei Meldungen sind weg.
3. **⚠⚠ Unsere eigene Prüfung von letztem Sprint hat ihre Grundmenge nicht verdient.**
   Sie las eine **Schreibweise** und nannte sie eine Konvention. Nachgezählt: **111 von
   112** Lehren tragen eine Regel — als Auswahl ist das keine Auswahl. Und die
   Trefferquote ist innerhalb (24 %) und außerhalb (15 %) fast gleich.
   > **Die Prüfung hat nie Lehren getrennt, die eine Absicherung BRAUCHEN. Sie hat
   > Lehren getrennt, die jemand mit Doppelpunkt geschrieben hat.**
   Umgebaut, ohne einen einzigen Dauerbefund zu erzeugen: der Bestand ist **benannt** und
   bleibt still, rot wird nur Neues — ab jetzt in **jeder** Schreibweise.
4. **⚠⚠ Eine Frage, die dreimal weitergereicht wurde, war längst beantwortet.** Seit drei
   Sprints suchten wir einen „zweiten Schreibweg" ins Entscheidungslog. Gemessen: **es
   gibt ihn nicht als Programm** — es ist die **Hand**, und sie schreibt mit 103 von 158
   Zeilen die **Mehrheit**. Der Schaden, den ein Bau verhindert hätte, wird seit zwei
   Sprints ohnehin gefangen.
   > **Wir haben bei jeder Verschiebung den GRUND geprüft und nie die GÜLTIGKEIT der
   > Frage. Das ist ab jetzt Teil jeder Terminierung.**
5. **⚠⚠ Der unangenehmste Punkt betrifft wieder uns selbst: diese Session hat Ihren
   15-Minuten-Takt blockiert.** Um **06:15** lief er zweimal sauber durch. Ab **06:30**
   bis **07:01** brach er **sechsmal** ab — weil wir unsere Aufgaben geschlossen haben,
   bevor wir den Plan neu geschrieben hatten.
   > **Der Plan wird laut Beschluss am Sprint-ENDE geschrieben. Also ist der Bestand
   > während JEDES Sprints widersprüchlich — und genau dann kann Ihr Takt nie laufen.
   > Das ist kein Ausrutscher, das ist die Dauer eines Sprints.**
   ⚠ **Das stellt richtig, was hier letzten Sprint stand:** `pm/T-0077` ist **nicht** die
   einzige Sperre. Aufgeschrieben und terminiert, nicht schnell repariert.
6. **1429 Prüfungen für die Technik** über 95 Dateien (zweimal unabhängig gezählt),
   **200 Anforderungen ohne Lücke**. Briefkasten: **0 offen**, keiner eingegangen.
   Offene Aufgaben: **12** (drei geschlossen, zwei neu angelegt) — ⚠ oder **9**, je
   nachdem, welches unserer beiden Werkzeuge man fragt; siehe unten.

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt). **B** = dein 15-Minuten-Takt bekommt echte Aufgaben. **C** = der Ollama-Zweig wird beendet. ⚠ **Korrektur gegenüber letztem Sprint:** die Frage ist **nicht** die einzige Sperre — siehe Punkt 5. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus vier komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Dein Schnelltakt läuft grundsätzlich** | Um 06:15 zweimal `STARTKLAR`. Dass er danach wieder abbrach, war **unsere** Arbeit und nicht dein Rechner — repariert wird das im nächsten Sprint (`platform/T-0052`). |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11480 Dateien** (Stand 07:15). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Drei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Eine Zusicherung aus dem **letzten** Sprint hat diese Session aufgehalten —
und genau dafür war sie gebaut. Sie hielt einen **bekannten Mangel** fest und trug in
ihrem eigenen Text den Auftrag, beim Beheben umgedreht zu werden. Nach der Reparatur
wurde sie rot. **Hätten wir den Mangel nur in Prosa vermerkt, hätte die Datei nach dem
Fix schweigend weiter den alten Zustand beschrieben.** Sie hat dabei noch einen zweiten,
echten Fehler gefunden, den keine unserer neuen Prüfungen gesehen hätte.

**Zweitens:** Eine unserer eigenen Zahlen war zuerst falsch formuliert. Wir haben sie
**korrigiert und benannt**, statt sie stehen zu lassen — aufgefallen ist es, weil unsere
eigene Prüfung die Behauptung nicht hergab.

**Drittens:** Beim Zusammenstellen der Abschlusszahlen haben wir gemerkt, dass **zwei
unserer Werkzeuge „offene Aufgaben" verschieden zählen** (9 gegen 12; die Differenz sind
die drei gesperrten). Das war vor **vier** Sprints schon einmal entschieden worden — die
Festlegung stand in einem Kommentar und in keiner Prüfung, und das neuere Werkzeug hat sie
nicht übernommen. **Wir schreiben deshalb beide Zahlen mit ihrer Definition hin, statt
eine still zu wählen.**

---

</details>

<details><summary>Archiv: Sprint 30</summary>

## Das Wichtigste (Sprint 30, 2026-08-21)

1. **✅ Dein 15-Minuten-Takt bricht nicht mehr ab — und das ist jetzt gemessen statt
   vorhergesagt.** Letzter Sprint stand hier *„das ist eine Vorhersage, keine Messung"*.
   Um **04:15** steht im Log zum ersten Mal `STARTKLAR`. Davor: **65** Abbrüche.
2. **⚠⚠ Dahinter kam sofort der nächste Grund zum Vorschein, und der erste hatte ihn
   verdeckt: der Takt läuft jetzt — und findet nichts zu tun.**
   Er suchte sich die wichtigste offene Aufgabe, stellte dann fest, dass niemand sie in
   der lokalen Besetzung bearbeiten darf, und hörte auf. **Die zweitwichtigste hat er nie
   angesehen.**
   > **Eine Prüfung, die erst nach der Auswahl greift, ist kein Filter — sie legt gegen
   > genau einen Kandidaten ein Veto ein und lässt den Rest ungesehen.** Repariert.
3. **⚠⚠ Und die Meldung war zwar wahr, aber zu eng — genau das ist teuer.** Sie las sich
   wie ein Zufall (*„diese eine Aufgabe passt nicht"*). Tatsächlich ist es ein Zustand:
   **keine einzige** deiner 8 offenen Aufgaben kann von den beiden lokalen Besetzungen
   bearbeitet werden.
   > **Die enge Formulierung lädt dazu ein, es in 15 Minuten nochmal zu versuchen — und
   > genau das ist 90-mal passiert. Jetzt steht im Log, wie viele Aufgaben geprüft wurden
   > und dass ein weiterer Lauf daran nichts ändert.**
   ⚠ **Das ändert nichts daran, dass nichts gearbeitet wird.** Das kann nur deine Antwort
   auf `pm/T-0077`.
4. **✅ Die Frage nach den Entscheidungsnummern ist zu Ende gezählt — und die Zahl hat den
   Bau wieder verändert.** Von 1023 Nennungen ohne Ordnerangabe sind **nur 214 wirklich
   mehrdeutig** (21 %); der Rest steht dort, wo die Datei selbst sagt, welche gemeint ist.
   > **Und alle 214 nennen eine von **vierzehn** Nummern: `D000` bis `D013`. Ab `D014` ist
   > jede Nummer im ganzen Haus nur einmal vergeben.** Also haben wir nicht 1023
   > Fundstellen aufgeräumt, sondern eine Sperre eingebaut, die dafür sorgt, dass es bei
   > vierzehn bleibt.
5. **⚠⚠ Der unangenehmste Punkt betrifft unsere eigene Prüfung von letztem Sprint.** Sie
   soll melden, wenn eine neue Lehre ohne Absicherung bleibt. **Drei Lehren aus diesem
   Lauf hat sie nicht gesehen** — sie waren mit einem Punkt statt einem Doppelpunkt
   geschrieben.
   > **Schlimm ist nicht, dass drei durchgerutscht sind. Schlimm ist, dass die Prüfung
   > dabei grün blieb. Eine Sperre, die man mit einem anders gesetzten Satzzeichen umgeht,
   > ist keine.**
   Nachgezählt: von 111 Lehren erkennt sie **34**; **110** tragen tatsächlich eine Regel.
   Die drei sind nachgezogen, die Lücke ist aufgeschrieben und terminiert — **nicht**
   schnell repariert, weil die naheliegende Reparatur rund hundert Dauerwarnungen erzeugt
   hätte.
6. **1404 Prüfungen für die Technik** über 93 Dateien (gezählt, und durch eine zweite,
   unabhängige Rechnung bestätigt), **197 Anforderungen ohne Lücke**. Briefkasten: **0
   offen**, keiner eingegangen. Offene Aufgaben: **9** (zwei geschlossen, zwei neu
   angelegt).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt). **B** = dein 15-Minuten-Takt bekommt echte Aufgaben. **C** = der Ollama-Zweig wird beendet. ⚠ **Neu seit heute:** die Frage ist jetzt die *einzige* Sperre. Alles Technische davor ist repariert. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus drei komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Der Abbruch deines Schnelltakts hat aufgehört** | Wie letzten Sprint vorhergesagt — und diesmal **gemessen**: 04:15, `STARTKLAR`. Du musst dafür nichts tun. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11325 Dateien** (Stand 05:06). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Zwei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Unsere Prüfung aus dem letzten Sprint hätte drei Lehren dieses Laufs
stillschweigend übersehen. Wir haben es nur gemerkt, weil wir nachgesehen haben, ob die
Zahl sich bewegt — sie tat es nicht. **Eine Prüfung, die grün bleibt, sagt nicht dasselbe
wie eine Prüfung, die gesehen hat.**

**Zweitens:** Wir hatten geplant, die Nennungen der Entscheidungsnummern im Text zu
sichern. Beim Bauen ist aufgefallen, dass die Zahl allein dadurch stieg, dass wir
**über** das Problem geschrieben haben — 1023 wurden zu 1030. **Eine Prüfung auf diese
Zahl hätte jeden Bericht bestraft, der den Befund erklärt.** Deshalb sichern wir jetzt die
Nummernvergabe und nicht den Text.

</details>

---

<details><summary>Archiv: Sprint 29</summary>

## Das Wichtigste (Sprint 29, 2026-08-21)

1. **✅ Fünf Aufgaben abgeschlossen, keine einzige verschoben.** Darunter beide, die
   letzter Sprint ausdrücklich für „diesmal" angekündigt hatte, und eine, die zum vierten
   Mal drankam und deshalb gebaut werden **musste**.
2. **⚠⚠ Die Fehlermeldung, die deinen 15-Minuten-Takt bei jedem Lauf abgebrochen hat, ist
   weg — und sie war falsch, wie letzter Sprint vermutet hat.** Die Prüfung hat den
   **Zwischenspeicher** von Git angesehen statt die **Dateien**. Jetzt sieht sie die
   Dateien.
   > **Eine falsche Fehlermeldung ist teurer als gar keine: sie stoppt genauso wie eine
   > echte, und man kann nichts dagegen tun. Das bringt einem bei, Warnungen zu
   > überlesen.**
   Der Preis steht dabei: die Prüfung dauert jetzt **7,6 Sekunden länger** über alle 17
   Ordner. Nachgemessen, nicht geschätzt.
3. **✅ Dein Wunsch aus dem Brief vom 20.08. ist gebaut: Kommentare an Aufgaben.**
   *„ähnlich wie hier beim Team-Chat"* — und genau so: der Beitrag steht **in der Aufgabe
   selbst**, nicht in einem zweiten Speicher. **Auch an schon erledigten Aufgaben**, weil
   das der häufigste Anlass für eine Rückfrage ist.
   ⚠ Zwei Dinge, denen du widersprechen darfst, sind wie beantragt gebaut: die Kommentare
   gehen mit nach GitHub, und sie brauchen die PIN.
4. **⚠⚠ Drei Aufgaben stehen zum ersten Mal ehrlich als „blockiert" — nach vier
   Verschiebungen.** Wir konnten bisher nicht eintragen, dass eine Aufgabe auf eine
   Aufgabe in einem **anderen** Ordner wartet. Jetzt geht es.
   > **Und beim Eintragen ist etwas aufgefallen, das unangenehmer ist: eine der drei
   > wartet auf eine Aufgabe im SELBEN Ordner. Da wäre „blockiert" die ganze Zeit möglich
   > gewesen. Es hat nur nie jemand versucht.**
5. **⚠⚠ Unsere eigenen Prüfungen haben uns dreimal beim Fehler erwischt — und das ist die
   beste Nachricht des Laufs.** Zweimal war ein Speichervorgang stillschweigend
   fehlgeschlagen, und die Prüfung hat den daraus entstehenden falschen Zustand gemeldet.
   Einmal hat ein Zähler eine Nebenwirkung gefunden, die sonst durchgegangen wäre.
   > **Wir haben es jeweils repariert und danach eine Regel eingebaut, die verhindert,
   > dass es unbemerkt bleibt: jeder Speicherschritt prüft jetzt, ob er wirklich
   > gespeichert hat.**
6. **⚠⚠ Und eine neue Prüfung war zuerst wertlos, ohne dass man es gesehen hätte.** Sie
   sollte finden, welche Lehren nie in eine Prüfung überführt wurden — und hat sich dabei
   **selbst mitgelesen**. Ein Beispiel in einem Kommentar reichte, damit eine Lehre als
   „erledigt" galt.
   > **Eine Prüfung, die ihre eigene Frage beantworten kann, prüft nicht mehr.** Behoben,
   > und es gibt jetzt eine zweite Prüfung, die genau das nachweist.
7. **✅ Zweimal „erst zählen, dann bauen" — und beide Male hat die Zahl die Frage
   verändert.** Bei den Lehren: 108 insgesamt, 34 mit klarer Regel, **29 davon ohne jede
   Absicherung**. Bei den Entscheidungsnummern: **1003** Nennungen ohne Ordnerangabe gegen
   319 mit — aber die größten Posten stehen in den Entscheidungslisten selbst, wo die
   Angabe gar nicht mehrdeutig ist. **Also sind es nicht 1003 Probleme**, und den Rest
   trennen wir im nächsten Lauf.
8. **1367 Prüfungen für die Technik** über 90 Dateien (gezählt), **195 Anforderungen ohne
   Lücke**, 113 Oberflächen-Prüfungen grün. Briefkasten: **0 offen**, keiner eingegangen.
   Offene Aufgaben: **8** (vorher 15).

---

## Für dich (E. John)

| Was | Warum |
|---|---|
| ⚠⚠ **`pm/T-0077` beantworten** | Unverändert offen, **Frist 28.08.** — noch nicht abgelaufen. **A** = alles bleibt (Voreinstellung, Schweigen genügt); drei Aufgaben bleiben gesperrt, jetzt aber **ehrlich als gesperrt gebucht** statt weitergeschoben. **B** = dein 15-Minuten-Takt bekommt echte, mechanische Aufgaben. **C** = der Ollama-Zweig wird beendet und die drei Aufgaben geschlossen. |
| ⚠⚠ **`abschluss.cmd` ausführen** | Der Rückstand ist jetzt **fünf Tage plus zwei komplette Sprints**. **Stichprobe:** danach steht in `abschluss-auto.log` `OK - alles geprueft und gepusht` und `PUSH-ANFORDERUNG.txt` ist verschwunden. |
| ✅ **Der Abbruch deines Schnelltakts sollte aufhören** | Die falsche Fehlermeldung ist repariert. ⚠ **Das ist eine Vorhersage und keine Messung** — wir können deinen Takt von hier aus nicht auslösen. Wenn er weiter abbricht, sag Bescheid: dann ist es etwas anderes. |
| ⚠ **Server neu starten** (Mission Control) | Der Kommentar-Kasten an den Aufgaben lädt erst nach einem Neustart. |
| ⚠ **Die Sperr-Reste löschen, wenn du magst** | **11138 Dateien** (Stand 03:39). Wir können sie nicht löschen, du schon. |
| ⚠ **Die alten Punkte** | Mail-Zugangsdaten (`team-mail/N-0003`), deine Zählung der Kacheln im Reiter „Dashboard", `ollama list`. |

---

## ⚠ Zwei Dinge, die wir über uns selbst aufschreiben

**Erstens:** Wir haben in diesem Lauf **zweimal** einen Speichervorgang für gelungen
gehalten, der fehlgeschlagen war — weil wir die Ausgabe unterdrückt und das Ergebnis nicht
nachgesehen haben. Beide Male hat es eine Prüfung gefunden, nicht wir. Die Regel steht
jetzt im Ablauf: **jeder Speicherschritt prüft nach, ob er wirklich gespeichert hat.**

**Zweitens:** Wir haben eine Aufgabe gefunden, die vier Sprints lang „verschoben" wurde,
obwohl „blockiert" die ganze Zeit möglich war — im selben Ordner, ohne jede Werkzeuglücke.
Letzter Sprint hatten wir für einen ähnlichen Fall noch das Werkzeug verantwortlich
gemacht, und das war dort auch richtig. **Hier gibt es diese Entschuldigung nicht.**

---

## ⚠ Eine Zahl, die zuerst nicht aufging — und warum sie jetzt aufgeht

Ein erster Zwischenstand ergab **1342** Prüfungen, das Zählwerkzeug meldete **1367**.
Statt die schönere Zahl zu nehmen, haben wir nachgemessen: **die Suite war in Ordnung,
unsere Messung nicht.** Wir hatten die Blöcke zu verschiedenen Zeitpunkten gefahren, und
fünf der neuen Prüfdateien gab es beim frühen Block noch gar nicht.

Neu gemessen: 436 + 111 + 28 + 350 + 209 + 108 + 56 + 69 = **1367** — und das Zählwerkzeug
sagt ebenfalls 1367. **Zwei unabhängige Wege, dasselbe Ergebnis.**

> **Eine Summe aus Teilmessungen zu verschiedenen Ständen ist keine Summe.**


</details>