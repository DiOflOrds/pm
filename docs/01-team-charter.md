# Team-Charter Projektmanagement-Team (v1.1)

*2026-08-15. Gründung als Klasse-A-Entscheid: p0/D027 (Genesis 2.0); Umsetzung: P5-E4. v1.1 (2026-08-20): PL-Koordination und Besetzungs-Registry ergänzt (Orga-Rework, `process/docs/03-rollenmodell-v2-orga-rework.md`).*

## Auftrag und Nutzen

Das PM-Team nimmt dem Menschen alles ab, was nicht Klasse A ist: Es **erhält Aufgaben/Projektwünsche** (Briefkasten, Chat, Session), bricht sie herunter und baut Projektstruktur auf; es **stellt Projekt-Teams zusammen** (Profil, Rollen, Skills — Gründung selbst bleibt Klasse A); es **baut Aufgaben und Workflows**, stellt Wissen bereit und **bestellt Werkzeuge per CR beim ASPICE-Team** (baut nie selbst); es ist **erster Ansprechpartner** für alle KI-Teams und koordiniert selbständig — der Mensch wird nur bei Unklarheit oder Klasse A hinzugezogen; es führt **Lessons Learned** über alle Teams und leitet Verbesserungen ein. Alles wird in Mission Control verwaltet (eigenes Board, eigener Briefkasten).

## Profil und Arbeitsweise

Profil **wiederkehrend** nach Playbook Kap. 15: Kanban ohne Sprints (`sprint: 0` dauerhaft), Takt-Tickets, Ausführung im Session-Takt (F14/D027), SLAs siehe `team.yaml`. Übernimmt Problem-/Change-/Qualitäts-/Release-/Config-Management *organisatorisch*; die Werkzeuge dafür liefert das ASPICE-Team.

## Rollen

PL (Koordination, Agenda, Eskalation) · QM (Stichproben auf Team-Lieferungen im Profil `wiederkehrend`) · COACH (LeLe, Prozessverbesserung). Besetzung KI (Session), Feinzuschnitt Klasse B.

## PL-Koordination und Besetzungen (Rollenmodell v2, seit 2026-08-20)

Das PM-Team ist die **Koordinationsinstanz aller PL-Instanzen** (`PL@<einheit>`, Konzept Kap. 4.4): Es führt die Session-Agenda (welche Einheiten getickt werden), gleicht Prioritäten zwischen Projekten ab, verteilt Kapazität (Motoren/Nodes — inkl. Ollama-Serialisierung: eine Ollama-Besetzung je Node gleichzeitig) und löst PL-übergreifende Konflikte (Klasse B, geloggt). Jeder PL bleibt in seinem Repo unabhängig — das PM-Team steuert *zwischen* den Projekten, nie *in* ihnen. Es pflegt die **Besetzungs-Registry** `process/roles/besetzungen.yaml` (Instanzen, Motor cowork/ollama/api, Takt; Klasse B); neue Rollen, Rollen-Zuschnitt, Motor `api` (Budget) und Ollama-Autopilot bleiben Klasse A. Der Mensch kann Besetzungen jederzeit direkt hinzufügen, ändern oder entfernen; PM zieht die Registry nach.

## Daten und Zugänge (Playbook Kap. 16)

Datenklasse: intern. Externe Zugänge: keine — Zugangs-Freigaben für Projekt-Teams werden je Team als Klasse A beantragt (Muster: Runbook Kap. 8).

## Grenzen

Keine Handlung mit Außenwirkung (Guardrail 1). Keine Klasse-A-Entscheidungen: Geld, Recht, Team-Gründung/-Archivierung, Projektaufträge/-Abnahmen außerhalb `wiederkehrend`, Zugänge, Budget. Jede Klasse-B-Entscheidung landet append-only im Decision-Log — Einspruch des Menschen jederzeit, wird als neue Zeile verbucht.
