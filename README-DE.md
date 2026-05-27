<p align="center">
  <a href="README.md">English</a> | <a href="README-ZH.md">中文</a> | <a href="README-ES.md">Español</a> | <a href="README-FR.md">Français</a> | <a href="README-PT.md">Português</a> | <a href="README-UA.md">Українська</a> | <b>Deutsch</b>
</p>

# Antigravity CLI

Antigravity CLI versteht Ihre Codebasis, nimmt Änderungen mit Ihrer Erlaubnis vor und führt Befehle aus – direkt in Ihrem Terminal.

- **Offizielle Dokumentation**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Offizielle Website**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI bringt die Kernfunktionen von Antigravity 2.0 (mehrstufiges Denken, Bearbeiten mehrerer Dateien, Tool-Aufrufe und persistenter Verlauf) direkt in Ihr Terminal. Es ist für tastaturgesteuerte Arbeitsabläufe und Remote-SSH-Sitzungen mit minimalem Ressourcen-Overhead optimiert.

---

## Funktionen im Überblick

| Funktion | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Hauptfokus** | Geschwindigkeit, Tastatureffizienz, geringer Overhead | Vollständigkeit, visuelle Orchestrierung, Projektmanagement |
| **Schnittstelle** | Terminal-Benutzeroberfläche (TUI) | Vollständige, umfangreiche GUI-Anwendung |
| **Arbeitsabläufe** | SSH/Remote-Sitzungen, Tastatur zuerst | Lokale Arbeitsbereiche, komplexe Orchestrierung |
| **Agenten-Engine** | Gemeinsame Core-Agenten-Engine | Gemeinsame Core-Agenten-Engine |

---

## Integration

- **Gemeinsame Agenten-Engine**: Beide Schnittstellen laufen auf derselben Core-Agenten-Engine. Verbesserungen werden automatisch auf beide angewendet.
- **Gemeinsame Einstellungen**: Einstellungen und Berechtigungen werden bidirektional synchronisiert.
- **Sitzungsexport**: Exportieren Sie Terminalsitzungen in die Antigravity 2.0 GUI, um die Arbeit fortzusetzen.

---

## Installation

### macOS / Linux
```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

### Windows PowerShell
```powershell
irm https://antigravity.google/cli/install.ps1 | iex
```

### Windows CMD
```cmd
curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
```

---

## Authentifizierung

Die CLI authentifiziert sich über den System-Schlüsselbund und greift auf die Google-Anmeldung zurück, wenn keine aktive Sitzung vorhanden ist.

- **Lokal**: Öffnet automatisch Ihren Standardbrowser.
- **Remote / SSH**: Erkennt SSH-Sitzungen und gibt eine Autorisierungs-URL aus, um die Anmeldung lokal abzuschließen.
- **Abmelden**: Führen Sie `/logout` aus, um gespeicherte Anmeldeinformationen zu löschen.

> [!NOTE]
> Verbinden Sie für den Unternehmenszugriff Ihr GCP-Projekt während des Onboardings. Weitere Informationen finden Sie auf der Enterprise-Seite.

---

## Nutzungsbedingungen und Datennutzung

> [!WARNING]
> Es ist bekannt, dass KI-Codierungsagenten bestimmte Sicherheitsrisiken aufweisen, darunter die autonome Codeausführung, Datenabfluss, Prompt-Injektionen und Risiken in der Lieferkette. Stellen Sie sicher, dass Sie alle Aktionen des Agenten überwachen und überprüfen.

Durch die Nutzung von Antigravity CLI erklären Sie sich damit einverstanden, zur Verbesserung des Produkts beizutragen, indem Sie Google gestatten, Ihre Interaktionsdaten zu erfassen und zu verwenden, vorbehaltlich der Google-Nutzungsbedingungen und der Google-Datenschutzerklärung. Sie können sich jederzeit über Ihre Einstellungen abmelden.

### Rechtliche Links und Datenschutz

- **Nutzungsbedingungen**: [antigravity.google/terms](https://antigravity.google/terms)
- **Datenschutzerklärung**: [policies.google.com/privacy](https://policies.google.com/privacy)
