# Board (generiert von platform/scripts/board.py — nicht von Hand editieren)

Stand: 2026-08-16 · Tickets: 33 · davon wiederkehrend: 2


## open (7)

| ID | Titel | Typ | Takt | Rolle | Prio | Sprint | blockiert durch |
|---|---|---|---|---|---|---|---|
| [T-0001](tickets/T-0001.md) | Takt: Session-Agenda pflegen (jede Session) | task | je Session | pl | hoch | 0 | — |
| [T-0002](tickets/T-0002.md) | Takt: Intake-Queue — neue Wünsche/Briefe qualifizieren (jede Session) | task | je Session | pl | hoch | 0 | — |
| [T-0033](tickets/T-0033.md) | DR (Klasse A): G0 für Projekt P11 „Widget-Dashboard" — Auftrag, Abnahmekriterien, Abgrenzung | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0028](tickets/T-0028.md) | CR (pm/N-0022): Projekt-Pool — Team gründen im HMI (Steckbrief, Profil, Datenklasse, Zugänge) | change-request | einmalig | chg | mittel | 0 | — |
| [T-0030](tickets/T-0030.md) | CR (pm/N-0025): Offene Aufgaben terminieren — Fristen für Backlog-Tickets, echter Takt für wiederkehrende Aufgaben | change-request | einmalig | pl | mittel | 0 | — |
| [T-0032](tickets/T-0032.md) | CR (pm/N-0025, Teil 2): Echter Uhrzeit-Takt für wiederkehrende Aufgaben — Abgrenzung zu F14 und den team-mail-Takten | change-request | einmalig | pl | mittel | 0 | — |
| [T-0003](tickets/T-0003.md) | Takt: LeLe je Sprint/Durchlauf konsolidieren (D005 — kontinuierlich statt quartalsweise) | task | einmalig | coach | niedrig | 0 | — |

## in_review (4)

| ID | Titel | Typ | Takt | Rolle | Prio | Sprint | blockiert durch |
|---|---|---|---|---|---|---|---|
| [T-0013](tickets/T-0013.md) | Problem (platform/N-0001): board-check rot nach Board-Formatänderung — Push-Reihenfolge | problem | einmalig | prob | hoch | 0 | — |
| [T-0026](tickets/T-0026.md) | Problem (platform/N-0006): CI rot — das Matrix-Gate sah das Sammel-Repo `projects` nicht | problem | einmalig | cm | hoch | 0 | — |
| [T-0031](tickets/T-0031.md) | DR (Klasse A): Gründung Team „team-dashboard" (Pool-Kandidat #13) — Steckbrief, Profil, Datenklasse, Zuschnitt Bau/Betrieb | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0010](tickets/T-0010.md) | Problem (N-0007): board-check-Flake — Stand-Datum kippt um Mitternacht | problem | einmalig | prob | mittel | 0 | — |

## done (22)

| ID | Titel | Typ | Takt | Rolle | Prio | Sprint | blockiert durch |
|---|---|---|---|---|---|---|---|
| [T-0004](tickets/T-0004.md) | DR (Klasse A): Gründung Pilot-Team „team-mail" (Mail-Zusammenfassung) + IMAP-Lesezugriff | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0005](tickets/T-0005.md) | DR (Klasse A): P7 „Teams im HMI" beauftragen — Digest-Ansicht + Team-Konfiguration in Mission Control | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0006](tickets/T-0006.md) | CR (N-0004): Ollama-Modell anzeigen + im Konfigurator auswählbar | change-request | einmalig | chg | hoch | 0 | — |
| [T-0007](tickets/T-0007.md) | CR (N-0005): KI-Hinweisfeld im Konfigurator (Suchauftrag / eigene Digest-Kategorie) | change-request | einmalig | chg | hoch | 0 | — |
| [T-0008](tickets/T-0008.md) | DR (Klasse A): P9 „Org-Cockpit" beauftragen — Team-/Projekt-Dashboard mit Status & Beschreibung | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0009](tickets/T-0009.md) | Problem (N-0006): Auto-Push seit 15.08. 17:36 fehlgeschlagen — cmd-Klammern-Bug in :repo_push | problem | einmalig | prob | hoch | 0 | — |
| [T-0011](tickets/T-0011.md) | DR (Klasse A): P10 „Aufgaben bearbeiten im HMI" beauftragen — Tickets editieren, Labels, Typ | decision-request | einmalig | pl | hoch | 0 | — |
| [T-0012](tickets/T-0012.md) | CR (N-0015): Kopfbereich zeigt nur aktive Projekte/Teams — direkt anklickbar | change-request | einmalig | chg | hoch | 0 | — |
| [T-0017](tickets/T-0017.md) | Problem (Befund Routine-Session): Inbox und Frist-Warnmail sahen Projekte im Sammel-Repo nicht — G1-DR p10/T-0002 war unsichtbar | problem | einmalig | prob | hoch | 0 | — |
| [T-0019](tickets/T-0019.md) | CR (N-0019): Requirements aller Projekte/Teams sichtbar und filterbar | change-request | einmalig | chg | hoch | 0 | — |
| [T-0020](tickets/T-0020.md) | CR (N-0020): Projekt-Pool als Backlog-Bereich im HMI — Anzeigen | change-request | einmalig | chg | hoch | 0 | — |
| [T-0021](tickets/T-0021.md) | CR (platform/N-0003): Aufgaben tragen eine eindeutige Kennung <projekt>/T-xxxx | change-request | einmalig | chg | hoch | 0 | — |
| [T-0023](tickets/T-0023.md) | SUP.9: Verwaister index.lock machte eine ganze Session unverbuchbar — Preflight räumt jetzt auch ohne Lösch-Recht | problem | einmalig | cm | hoch | 0 | — |
| [T-0024](tickets/T-0024.md) | SUP.9: Auto-Push stand seit 09:44 still — die Prozess-Abfrage im Preflight scheiterte an einer Codepage | problem | einmalig | cm | hoch | 0 | — |
| [T-0025](tickets/T-0025.md) | CR (team-mail/N-0002, Rest): Sofort-Knopf zeigt im Klartext, womit er läuft (Modell, KI-Hinweis, Takte) | change-request | einmalig | chg | hoch | 0 | — |
| [T-0014](tickets/T-0014.md) | CR (N-0017): Cockpit zeigt wiederkehrende Aufgaben im Klartext statt als Symbol | change-request | einmalig | chg | mittel | 0 | — |
| [T-0015](tickets/T-0015.md) | CR (N-0018): Team-Chat zeigt die neuesten Nachrichten zuerst | change-request | einmalig | chg | mittel | 0 | — |
| [T-0016](tickets/T-0016.md) | Problem (platform/N-0002): ConnectionResetError-Traceback im Server-Log bei Verbindungsabbruch | problem | einmalig | prob | mittel | 0 | — |
| [T-0018](tickets/T-0018.md) | CR (Auftraggeber via Session): Entscheidungen mit Datum UND Uhrzeit festhalten | change-request | einmalig | chg | mittel | 0 | — |
| [T-0022](tickets/T-0022.md) | CR (N-0020, Teil 2): Projekt-Pool — Kandidat anlegen und starten im HMI (nach P10 Sprint 1) | change-request | einmalig | chg | mittel | 0 | — |
| [T-0027](tickets/T-0027.md) | Problem (pm/N-0023): Projekt-Pool — Kandidatentext auf 200 Zeichen/ohne Zeilenumbruch begrenzt | problem | einmalig | prob | mittel | 0 | — |
| [T-0029](tickets/T-0029.md) | Problem (pm/N-0024): Projekt-Pool — 'Quelle' auch bei 4000 Zeichen (T-0027) noch zu eng | problem | einmalig | prob | mittel | 0 | — |
