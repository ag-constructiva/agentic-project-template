# Template-Update — Agentenprotokoll

> **Hinweis:** Diese Datei enthält ausschließlich technische Ablaufanweisungen für den Agenten zum Befehl `update agentic-project-template`. Wird nur eingelesen bei Ausführung dieses Befehls. Für Nutzungsinfos: siehe [README.md](README.md); für alle übrigen Arbeitsregeln siehe [AGENTS.md](AGENTS.md).

## `update agentic-project-template`

Beispiele:

```text
update agentic-project-template
Update project template
Gibt es ein Update für das Projekt-Template?
```

Prüft, ob für das öffentliche Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) eine neuere Version vorliegt als die zuletzt synchronisierte, hilft bei Übernahme relevanter Änderungen. Siehe `.template-version` unter `Verzeichnisstruktur` in [AGENTS.md](AGENTS.md).

Ablauf:

1. Prüfen, ob `.template-version` im Projektwurzelverzeichnis existiert.
2. **Falls nicht, oder falls vorhanden aber Commit-Hash unklar/nicht auswertbar (z. B. alter Projektstand ohne bekannten Ausgangsstand):**

   a. Nutzer fragen, ob Projekt jetzt mit öffentlichem Template unter `https://github.com/ag-constructiva/agentic-project-template` verknüpft werden soll — dabei darauf hinweisen, dass ohne bekannten Ausgangsstand kein Diff möglich ist und stattdessen der jeweils **neueste Stand** der Template-Dateien direkt übernommen wird.
   b. Nach Zustimmung: aktuellen Commit-Hash des `main`-Branches über GitHub-API (`https://api.github.com/repos/ag-constructiva/agentic-project-template/commits/main`) ermitteln.
   c. Aktuelle Fassung jeder Template-Datei (`AGENTS.md`, `CLAUDE.md`, `UPDATE.md`, Struktur-/Befehlsabschnitte von `README.md`) vom Remote-Repository (`main`-Branch) laden, mit lokaler Fassung vergleichen. Lokale, projektspezifische Anpassungen ermitteln, je Datei zusammengeführte Fassung vorschlagen (neueste Template-Inhalte + lokale Anpassungen erhalten). Änderung erst nach ausdrücklicher Bestätigung anwenden — je Datei einzeln, nicht pauschal.
   d. Nach Anwendung `.template-version` mit Repository, ermitteltem Commit-Hash (aus 2b) und Datum anlegen/aktualisieren.
   e. Durchgeführte Aktualisierung in `state.md` festhalten (z. B. unter `Last Work`).
   f. Ohne Zustimmung in 2a oder 2c: keine Datei verändern, `.template-version` nicht anlegen. Mögliche Verknüpfung/Aktualisierung unter `Next Actions` in `state.md` festhalten.
3. **Falls `.template-version` existiert mit eindeutig auswertbarem Commit-Hash:**

   a. GitHub-Compare-API aufrufen: `https://api.github.com/repos/ag-constructiva/agentic-project-template/compare/<gespeicherter-commit-hash>...main`.
   b. Status `identical` (bzw. `ahead_by: 0`) → Nutzer knapp mitteilen, keine Aktualisierung, Befehl ohne weitere Schritte beenden.
   c. Andernfalls: anhand `commits[].commit.message` aus Compare-Antwort grob zusammenfassen, was sich seit letztem Stand geändert hat; anhand `files[].filename` betroffene Dateien listen.
   d. Nutzer ausdrücklich fragen, ob Änderungen übernommen werden sollen.
4. Bei Zustimmung zur Übernahme:

   a. Nur Template-Dateien (`AGENTS.md`, `CLAUDE.md`, `UPDATE.md`, Struktur-/Befehlsabschnitte von `README.md`), die laut `files[].filename` tatsächlich betroffen sind.
   b. Für jede betroffene Datei aktuelle Fassung vom Remote-Repository (`main`-Branch) laden, mit lokaler Fassung vergleichen; `files[].patch` aus Compare-Antwort als zusätzlicher Anhaltspunkt, ersetzt Abgleich mit lokaler Fassung aber nicht.
   c. Lokale, projektspezifische Anpassungen ermitteln, je Datei zusammengeführte Fassung vorschlagen (neue Template-Inhalte + lokale Anpassungen erhalten). Änderung erst nach ausdrücklicher Bestätigung anwenden — je Datei einzeln, nicht pauschal.
   d. Nach Anwendung `.template-version` mit neuem Commit-Hash (`main`-Commit aus Schritt 3a) und Datum aktualisieren.
   e. Durchgeführte Aktualisierung in `state.md` festhalten (z. B. unter `Last Work`); bei wesentlichen strukturellen Auswirkungen zusätzlich ADR unter `decisions.md` anlegen.
5. Ohne Nutzer-Zustimmung in Schritt 3d oder 4c: keine Datei verändern. Mögliche Aktualisierung stattdessen unter `Next Actions` in `state.md` festhalten.
6. Kein Netzwerkzugriff auf Remote-Repository möglich: Agent teilt dies mit, erfindet keinen Vergleichsstand.
7. Dateien unter `01_sources/`, `02_work/` (außer `state.md`/`decisions.md` gemäß Schritt 4e) und `03_dist/` werden durch diesen Befehl niemals verändert.
