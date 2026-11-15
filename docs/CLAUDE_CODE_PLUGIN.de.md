# EXZA Remote für Claude Code — Computersteuerung über MCP

**Claude Code mit dem eigenen Mac, Windows-PC oder Linux-Rechner verbinden.** EXZA Remote stellt einen durch OAuth geschützten MCP-Dienst bereit. Auf dem Server sind derzeit **84 Werkzeugdefinitionen** registriert. Welche davon nutzbar sind, hängt von Gerät, Freigabe und Betriebssystem ab.

[EXZA Remote Website](https://remote.exza.de/) · [EXZA-Konto erstellen](https://remote.exza.de/app/?register=1&utm_source=github&utm_medium=repository&utm_campaign=claude_code_de) · [84 Werkzeuge](https://remote.exza.de/de/tools/) · [English guide](CLAUDE_CODE_PLUGIN.md)

## In zwei Befehlen installieren

Claude Code muss bereits installiert sein. Führe diese Befehle im Terminal aus:

~~~bash
claude plugin marketplace add exzade/EXZA-Remote
claude plugin install exza-remote@exza-remote-marketplace
~~~

Danach in Claude Code `/mcp` öffnen und die EXZA-Remote-Anmeldung durchführen. **Kein `npx exza-remote` aus Drittquellen installieren** – unser MCP-Server ist unter `https://remote.exza.de/mcp` erreichbar.

## Computer verbinden

1. Auf [remote.exza.de](https://remote.exza.de/app/?register=1&utm_source=github&utm_medium=repository&utm_campaign=claude_code_de) registrieren oder anmelden.
2. Die offizielle EXZA Remote Connection auf dem eigenen Mac, Windows-PC oder Linux-Rechner starten: [Installationsanleitung](GETTING_STARTED.md).
3. Falls nötig, die sechsstellige PIN aus dem lokalen Terminal im EXZA-Kundenportal eintragen.
4. Am **physischen Terminal Y drücken**, um die angezeigte Kontoverbindung für diese Sitzung freizugeben, oder **N** zum Ablehnen. Das Terminal muss während der Verbindung offen bleiben.
5. In Claude Code unter `/mcp` die EXZA-OAuth-Anmeldung abschließen und das gewünschte Gerät sowie die Berechtigungen prüfen.
6. Sicher beginnen: **„Ist mein EXZA-Remote-Computer verbunden? Zeige nur Betriebssystem und Status.“**

## Was ist möglich?

- CPU, Arbeitsspeicher, Prozesse und Systemzustand auslesen.
- Dateien im ausdrücklich freigegebenen Arbeitsbereich auflisten und nach Zustimmung bearbeiten.
- Installierte Desktop-Anwendungen erkennen, Webseiten öffnen und erlaubte Fensteraktionen ausführen.
- Nach ausdrücklicher Zustimmung konkrete Terminalbefehle ausführen und Ergebnisse prüfen.

**Sicherheit:** OAuth-Berechtigungen (`computer:read` und `computer:write`), gerätegebundene Anmeldung, Y/N-Freigabe vor Ort, Claudes Werkzeugfreigaben und Betriebssystemrechte gelten unabhängig voneinander. Eine sichtbare Werkzeugliste ersetzt keine Zugriffsberechtigung.

**Claude im Browser:** Statt dieses ZIP-/Marketplace-Plugins einen benutzerdefinierten Remote-MCP-Connector mit `https://remote.exza.de/mcp` hinzufügen. Ein Eintrag im offiziellen Anthropic-Verzeichnis ist davon unabhängig und bisher nicht genehmigt.

**Kosten:** Die GitHub-Veröffentlichung dieses Plugin-Verzeichnisses ist kostenlos. EXZA Remote bietet je nach aktuellem Angebot kostenlose Nutzung und optionale Premium-Tarife; Claude-Abonnements bzw. -Nutzung können unabhängig davon kostenpflichtig sein.

**Hilfe:** [EXZA Support](https://remote.exza.de/hilfe) · [Datenschutz](https://remote.exza.de/legal/datenschutz.html) · [Nutzungsbedingungen](https://remote.exza.de/legal/nutzungsbedingungen.html) · [Sicherheitsmeldungen](../SECURITY.md) · info@exza.de

## RC50-Client und Einreichung ins offizielle Claude-Verzeichnis

**EXZA Remote Connection 1.9.0-rc50** korrigiert die Windows-Fensteraktivierung über vollständige Titel und prüft Unicode- sowie lange Texteingaben in unterstützten Windows-Editoren. MCP-Server und **84 Werkzeugdefinitionen** bleiben unverändert.

Für die **öffentliche Anthropic-Einreichung** das [Einreichungsportal](https://claude.ai/directory/manage) verwenden und auf den [GitHub-Plugin-Ordner](../plugins/exza-remote) verweisen. Alternativ nur den **Remote-MCP-Connector** mit der URL https://remote.exza.de/mcp einreichen. Dafür ist ein geeigneter kostenpflichtiger Claude-Tarif erforderlich.

**[Claude-Plugin RC50 herunterladen](https://remote.exza.de/downloads/exza-remote-claude-code-plugin-rc50.zip)** · [Windows-/Mac-/Linux-Client RC50 herunterladen](https://remote.exza.de/downloads/exza-remote-client-rc50.zip)

Das **Marketplace-ZIP** ist für lokale/organisationsinterne Installationen bestimmt, **nicht** für die Einreichung eines einzelnen Plugins.

