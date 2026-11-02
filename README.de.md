# EXZA Remote — AI Computer Commander

**Dein Computer. Deine Kontrolle. Mit ChatGPT und Claude.**

**Verbinde ChatGPT, Claude und kompatible KI-Assistenten sicherer mit deinem eigenen Computer – mit Geräte-Kopplung, Benutzerkonto und Freigaben für sensible Aktionen.**

[**Offizielle Website**](https://remote.exza.de/) · [**Kundenportal**](https://remote.exza.de/app/) · [**Terminal-Installation**](#exza-remote-installieren--terminal-befehle) · [**Hilfe auf Deutsch**](https://remote.exza.de/hilfe) · [**English README**](README.md)

## Was ist EXZA Remote?

**AI Computer Commander** ist der Zusatzname für EXZA Remote – unsere Plattform für kontrollierte KI-Unterstützung direkt auf deinem eigenen Computer.

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

## EXZA Remote installieren – Terminal-Befehle

Du musst **dieses GitHub-Repository nicht klonen**. Es enthält öffentliche Produktinformationen, **keinen privaten Quellcode**. Installiere den Client über die [offizielle EXZA-Webseite](https://remote.exza.de/) auf deinem eigenen oder ausdrücklich autorisierten Computer.

**Voraussetzungen:** [Node.js 22+](https://nodejs.org/) mit npm, Internetverbindung und ein EXZA-Konto. Auf macOS/Linux zusätzlich curl, unzip und ein SHA-256-Prüfprogramm. **Keine Administrator- oder Root-Rechte erforderlich.**

### Wenn Node.js fehlt oder zu alt ist

EXZA Remote benötigt **Node.js 22 oder neuer** inklusive **npm**. Du kannst Node.js **kostenlos** auf der offiziellen [Node.js-Downloadseite](https://nodejs.org/en/download) herunterladen. Wähle eine gepflegte **LTS-Version**, die zu deinem Betriebssystem passt. Du musst dafür weder GitHub klonen noch EXZA-Zugangsdaten weitergeben.

**Zuerst die vorhandenen Versionen prüfen** (macOS/Linux im Terminal oder Windows in PowerShell):

```sh
node --version
npm --version
```

- **macOS:** Öffne [nodejs.org/en/download](https://nodejs.org/en/download), wähle den offiziellen macOS-Installer (`.pkg`) für dein unterstütztes System, lade ihn herunter und folge der Installation. Danach Terminal schließen und neu öffnen.
- **Windows 10/11:** Wähle auf der offiziellen Webseite den Windows-Installer (`.msi`) für deine Gerätearchitektur. Bei der Installation soll npm mitinstalliert werden. Danach PowerShell schließen und neu öffnen. Für die Node.js-Installation kann eine Administratorfreigabe nötig sein; EXZA Remote selbst wird als normaler Benutzer gestartet.
- **Linux:** Verwende die Linux-Anleitung auf der [offiziellen Node.js-Seite](https://nodejs.org/en/download). Falls der Versionsmanager `nvm` **bereits installiert** ist, kannst du damit eine aktuelle LTS-Version für deinen Benutzer installieren. Fehlt `nvm`, nutze zuerst die offiziellen Hinweise für deine Distribution beziehungsweise einen vertrauenswürdigen Versionsmanager – **keine unbekannten `curl | bash`-Befehle ausführen**.

```sh
nvm install --lts
nvm use --lts
```

**Nach dem erneuten Öffnen des Terminals prüfen:**

```sh
node --version
npm --version
```

Bei `command not found`, `nicht erkannt` oder `v20` und älter überprüfe die Installation und die `PATH`-Umgebungsvariable und öffne das Terminal erneut. Wird bereits **v22 oder neuer** und eine npm-Version angezeigt, **überspringe die Node.js-Installation** und fahre unten mit dem EXZA-Remote-Befehl fort.

**Wichtig:** Eine bereits laufende EXZA-Remote-Verbindung nicht extra für die Node.js-Installation beenden oder neu starten. Änderungen erst nach dem regulären Sitzungsende durchführen.

### macOS – Terminal

Öffne Terminal und prüfe Node.js und npm:

```sh
node --version
npm --version
```

Danach den **offiziellen Installationsbefehl aus dem EXZA-Kundenportal** ausführen:

```sh
curl -fsSL https://remote.exza.de/install.sh -o exza-install.sh && sh exza-install.sh
```

### Windows 10/11 – PowerShell

Öffne PowerShell als **normaler Benutzer** und führe Folgendes aus:

```powershell
node --version
npm --version
curl.exe -fsSL https://remote.exza.de/install.ps1 -o exza-install.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File .\exza-install.ps1
```

`-ExecutionPolicy Bypass` gilt nur für diesen PowerShell-Prozess und ändert die dauerhafte Systemrichtlinie nicht. **Prüfe das Skript vor dem Start** und verwende nur die Domain `remote.exza.de`. Beachte gegebenenfalls die Sicherheitsregeln deiner Organisation. Windows ist als Installationsweg verfügbar, wurde jedoch noch nicht so umfassend nativ getestet wie macOS.

### Linux – Terminal

Installiere Node.js 22+ mit npm und nutze den offiziellen Unix-Installer:

```sh
node --version
npm --version
curl -fsSL https://remote.exza.de/install.sh -o exza-install.sh && sh exza-install.sh
```

Je nach Linux-Distribution können Funktionen abweichen. Siehe [Plattformen](docs/PLATFORMS.md).

**Was passiert dabei?** Der Installer lädt das offizielle Client-ZIP über HTTPS herunter, prüft dessen SHA-256-Prüfsumme, installiert die Laufzeitabhängigkeiten und startet EXZA Remote **im sichtbaren Terminal**. Lass dieses Fenster während der Verbindung geöffnet. Du kannst die öffentlichen Skripte vorher prüfen: [macOS/Linux](https://remote.exza.de/install.sh) · [Windows](https://remote.exza.de/install.ps1).

### Computer koppeln und ChatGPT oder Claude verbinden

1. Melde dich im [EXZA-Kundenportal → Meine Geräte](https://remote.exza.de/app/) an und bestätige gegebenenfalls deine E-Mail.
2. Warte auf die **serverbestätigte sechsstellige PIN** im laufenden Terminal und trage sie innerhalb von fünf Minuten auf der Webseite ein.
3. Prüfe das anfragende Konto. Bestätige die Kopplung **im Terminal mit Y** oder lehne sie mit **N** ab.
4. Füge in einem kompatiblen KI-Assistenten einen benutzerdefinierten Remote-MCP-Server hinzu:
   - **Name:** EXZA Remote
   - **Server-URL:** `https://remote.exza.de/mcp`
   - **Anmeldung:** EXZA-Konto über OAuth; Gerät und Berechtigungen prüfen.
5. Teste ohne Änderungen: *„Prüfe, ob mein EXZA-Remote-Computer online ist. Verändere nichts.“*

Ob benutzerdefinierte MCP-Verbindungen verfügbar sind, hängt vom KI-Anbieter, Tarif und den Kontoeinstellungen ab.

### Terminal-Befehle und Hilfe

| Befehl **im laufenden EXZA-Terminal** | Bedeutung |
| --- | --- |
| `status` | Verbindungs- und Kopplungsstatus anzeigen. |
| `new code` | Bei noch nicht gekoppeltem Gerät eine neue PIN anfordern, z. B. nach Ablauf der alten PIN. |
| `reset pairing`, danach `confirm reset pairing` | Eine widerrufene oder unbrauchbare lokale Kopplung innerhalb von 30 Sekunden ausdrücklich zurücksetzen. Für die neue Kopplung ist erneut eine Y-Freigabe nötig. |

**Keinen zweiten Agenten starten**, wenn das erste Terminal bereits verbunden ist. Gerät auf der Webseite entfernen und lokale Kopplung zurücksetzen sind getrennte Vorgänge. Beim Schließen des Terminals endet die aktive Verbindung. Teile niemals PINs, Passwörter, Tokens oder private Protokolle öffentlich.

[Vollständige Anleitung](docs/GETTING_STARTED.md) · [ChatGPT/Claude verbinden](docs/AI_MCP_GUIDE.md) · [Deutsche Hilfe](https://remote.exza.de/hilfe)

## Kostenloser Tarif und Premium

Der kostenlose Tarif umfasst **10.000 erfolgreiche Tool-Aufrufe pro EXZA-Konto und UTC-Monat**; alle verbundenen KI-Clients teilen sich dieses Kontingent. Aktuelle Premium-Preise, Leistungen und Vertragsbedingungen stehen auf der offiziellen Website und im Kundenportal.

## Sicherheit und Transparenz

Bei EXZA Remote behältst du die Kontrolle über gekoppelte Geräte und freigegebene Aktionen. Gehe sorgfältig mit Terminalbefehlen, Dateiveränderungen und Zugriffsfreigaben um. Teile niemals Passwort, PIN oder Zugangs-Token in Chats oder öffentlichen GitHub-Issues.

**Kontakt:** [info@exza.de](mailto:info@exza.de)

---

**EXZA – Technologies · © 2026. Alle Rechte vorbehalten.** Dieses Repository enthält Produktinformationen und Dokumentation, nicht den privaten Software-Quellcode. Siehe [NOTICE](NOTICE.md).
