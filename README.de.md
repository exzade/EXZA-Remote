# EXZA Remote — Dein Computer. Deine Kontrolle.

**Verbinde ChatGPT, Claude und kompatible KI-Assistenten sicherer mit deinem eigenen Computer – mit Geräte-Kopplung, Benutzerkonto und Freigaben für sensible Aktionen.**

[**Offizielle Website**](https://remote.exza.de/) · [**Kundenportal**](https://remote.exza.de/app/) · [**Hilfe auf Deutsch**](https://remote.exza.de/hilfe) · [**English README**](README.md)

## Was ist EXZA Remote?

EXZA Remote ist eine Plattform für die Verbindung von KI-Assistenten mit einem eigenen Computer über das **Model Context Protocol (MCP)**. Unterstützte Aktionen können beispielsweise Dateiinformationen, System- und Prozessabfragen oder freigegebene Terminal-Aufgaben umfassen. Welche Funktionen tatsächlich verfügbar sind, hängt vom Betriebssystem, der gekoppelten Sitzung und den erteilten Berechtigungen ab.

## Funktionen im Überblick

- **ChatGPT und Claude:** Verbindung über einen gemeinsamen MCP-Endpunkt.
- **Sicherheitscode:** Computer mit einem einmaligen Code koppeln und die Anfrage lokal im Terminal bestätigen.
- **Dateiverwaltung:** Dateien im ausdrücklich erlaubten Bereich anzeigen und – je nach Berechtigung – bearbeiten oder verwalten.
- **Terminal & Prozesse:** Freigegebene Befehle und unterstützte Prozesse ausführen bzw. prüfen.
- **Desktop-Aktionen:** Plattformabhängige Bedienung unterstützter Programme und Fenster; einige Werkzeuge gelten nur für macOS.
- **Geräteübersicht:** Verbindungen, Kontoeinstellungen und Nutzung im Kundenportal verwalten.
- **Freigaben:** Sensible Aktionen erfordern die passende Berechtigung und können eine zusätzliche lokale Bestätigung benötigen.

Aktuell sind **59 MCP-Werkzeug-Schnittstellen registriert**. Die Zahl ist keine Zusage, dass jede Funktion auf jedem Betriebssystem identisch nutzbar ist.

## Schnellstart

1. Auf [remote.exza.de](https://remote.exza.de/) ein Konto erstellen.
2. Im [Kundenportal](https://remote.exza.de/app/) **Meine Geräte** öffnen.
3. Die offiziellen Anweisungen für macOS, Windows oder Linux auswählen und den Client am eigenen Computer starten.
4. Den sechsstelligen Code aus dem Terminal im Portal eingeben und die Verbindung lokal bestätigen.
5. Im unterstützten KI-Client den MCP-Endpunkt **`https://remote.exza.de/mcp`** hinzufügen und die EXZA-Anmeldung abschließen.
6. Mit einer ungefährlichen Statusabfrage beginnen.

Weitere Informationen: [Hilfe](https://remote.exza.de/hilfe) · [Plattformen](docs/PLATFORMS.md) · [Sicherheitsmodell](docs/SECURITY_MODEL.md) · [FAQ](docs/FAQ.md)

## Kostenloser Tarif und Premium

Der kostenlose Tarif umfasst **10.000 erfolgreiche Tool-Aufrufe pro EXZA-Konto und UTC-Monat**; alle verbundenen KI-Clients teilen sich dieses Kontingent. Aktuelle Premium-Preise, Leistungen und Vertragsbedingungen stehen auf der offiziellen Website und im Kundenportal.

## Sicherheit und Transparenz

Bei EXZA Remote behältst du die Kontrolle über gekoppelte Geräte und freigegebene Aktionen. Gehe sorgfältig mit Terminalbefehlen, Dateiveränderungen und Zugriffsfreigaben um. Teile niemals Passwort, PIN oder Zugangs-Token in Chats oder öffentlichen GitHub-Issues.

**Kontakt:** [info@exza.de](mailto:info@exza.de)

---

**EXZA – Technologies · © 2026. Alle Rechte vorbehalten.** Dieses Repository enthält Produktinformationen und Dokumentation, nicht den privaten Software-Quellcode. Siehe [NOTICE](NOTICE.md).
