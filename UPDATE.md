# Template-Update — Agentenprotokoll

> **Hinweis:** Diese Datei enthält ausschließlich technische Ablaufanweisungen für den Agenten zum Befehl `update agentic-project-template`. Sie wird nur gelesen, wenn dieser Befehl ausgeführt wird. Für Informationen zur Nutzung dieses Projekts siehe [README.md](README.md); für alle übrigen Arbeitsregeln siehe [AGENTS.md](AGENTS.md).

## `update agentic-project-template`

Beispiele:

```text
update agentic-project-template
Update project template
Gibt es ein Update für das Projekt-Template?
```

Dieser Befehl prüft, ob für das öffentliche Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) eine neuere Version vorliegt als die, mit der dieses Projekt zuletzt synchronisiert wurde, und hilft bei der Übernahme relevanter Änderungen. Siehe `.template-version` unter `Verzeichnisstruktur` in [AGENTS.md](AGENTS.md) zur Bedeutung der Versionsdatei.

Ablauf:

1. Prüfe, ob `.template-version` im Projektwurzelverzeichnis existiert.
2. **Falls `.template-version` nicht existiert:**

   a. Frage den Benutzer, ob dieses Projekt jetzt mit dem öffentlichen Template unter `https://github.com/ag-constructiva/agentic-project-template` verknüpft werden soll.
   b. Nach Zustimmung: Ermittle den aktuellen Commit-Hash des `main`-Branches über die GitHub-API (`https://api.github.com/repos/ag-constructiva/agentic-project-template/commits/main`) und lege `.template-version` mit Repository, Commit-Hash und Datum an.
   c. Verändere in diesem Schritt keine weiteren Dateien.
3. **Falls `.template-version` existiert:**

   a. Rufe die GitHub-Compare-API auf: `https://api.github.com/repos/ag-constructiva/agentic-project-template/compare/<gespeicherter-commit-hash>...main`.
   b. Ist der Status `identical` (bzw. `ahead_by: 0`): teile dem Benutzer knapp mit, dass keine Template-Aktualisierung vorliegt, und beende den Befehl ohne weitere Schritte.
   c. Andernfalls: fasse dem Benutzer anhand der `commits[].commit.message`-Liste aus der Compare-Antwort grob zusammen, was sich seit dem zuletzt synchronisierten Stand geändert hat, und liste anhand von `files[].filename`, welche Dateien betroffen sind.
   d. Frage den Benutzer ausdrücklich, ob diese Änderungen übernommen werden sollen.
4. Bei Zustimmung zur Übernahme:

   a. Beschränke dich auf die Template-Dateien (`AGENTS.md`, `CLAUDE.md`, `UPDATE.md`, die Struktur- und Befehlsabschnitte von `README.md`), die laut `files[].filename` der Compare-Antwort tatsächlich betroffen sind.
   b. Lade für jede betroffene Datei die aktuelle Fassung vom Remote-Repository (`main`-Branch) und vergleiche sie mit der lokalen Fassung; die `files[].patch`-Angaben aus der Compare-Antwort können als zusätzlicher Anhaltspunkt dienen, ersetzen den Abgleich mit der lokalen Fassung aber nicht.
   c. Ermittle dabei lokale, projektspezifische Anpassungen und schlage je Datei eine zusammengeführte Fassung vor, die neue Template-Inhalte integriert und lokale Anpassungen erhält. Wende eine Änderung erst nach ausdrücklicher Bestätigung an — je Datei einzeln, nicht pauschal für alle Dateien zugleich.
   d. Aktualisiere nach Anwendung `.template-version` mit dem neuen Commit-Hash (dem `main`-Commit aus Schritt 3a) und Datum.
   e. Halte die durchgeführte Aktualisierung in `state.md` fest (z. B. unter `Last Work`); lege bei wesentlichen strukturellen Auswirkungen zusätzlich einen ADR unter `decisions.md` an.
5. Ohne Zustimmung des Benutzers in Schritt 3d oder 4c wird keine Datei verändert. Eine mögliche Aktualisierung wird stattdessen unter `Next Actions` in `state.md` festgehalten.
6. Ist kein Netzwerkzugriff auf das Remote-Repository möglich, teilt der Agent dies mit und erfindet keinen Vergleichsstand.
7. Dateien unter `01_sources/`, `02_work/` (mit Ausnahme von `state.md` und `decisions.md` gemäß Schritt 4e) und `03_dist/` werden durch diesen Befehl niemals verändert.
