<p align="center">
  <a href="README.md">English</a> | <a href="README-ZH.md">中文</a> | <a href="README-ES.md">Español</a> | <b>Français</b> | <a href="README-PT.md">Português</a> | <a href="README-UA.md">Українська</a> | <a href="README-DE.md">Deutsch</a>
</p>

# Antigravity CLI

Antigravity CLI comprend votre base de code, effectue des modifications avec votre autorisation et exécute des commandes — directement depuis votre terminal.

- **Documentation officielle**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Site web officiel**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI apporte les fonctionnalités fondamentales d'Antigravity 2.0 (raisonnement en plusieurs étapes, édition multi-fichiers, appels d'outils et historique persistant) directement dans votre terminal. Il est optimisé pour les flux de travail axés sur le clavier et les sessions SSH distantes avec une surcharge de ressources minimale.

---

## Aperçu des fonctionnalités

| Fonctionnalité | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Objectif principal** | Vitesse, efficacité du clavier, faible surcharge | Exhaustivité, orchestration visuelle, gestion de projet |
| **Interface** | Interface utilisateur de terminal (TUI) | Application GUI complète et riche |
| **Flux de travail** | Sessions SSH/distantes, clavier d'abord | Espaces de travail locaux, orchestration lourde |
| **Moteur d'agent** | Moteur d'agent central partagé | Moteur d'agent central partagé |

---

## Intégration

- **Moteur d'agent partagé** : Les deux interfaces s'exécutent sur le même moteur d'agent central. Les améliorations s'appliquent automatiquement aux deux.
- **Paramètres partagés** : Les préférences et les autorisations se synchronisent de manière bidirectionnelle.
- **Exportation de session** : Exportez les sessions de terminal vers l'interface graphique Antigravity 2.0 pour continuer à travailler.

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

## Authentification

Le CLI s'authentifie via le trousseau d'accès du système, revenant à la connexion Google si aucune session active n'existe.

- **Local** : Ouvre automatiquement votre navigateur par défaut.
- **Remoto / SSH** : Détecte les sessions SSH et affiche une URL d'autorisation pour terminer la connexion localement.
- **Déconnexion** : Exécutez `/logout` pour effacer les identifiants enregistrés.

> [!NOTE]
> Pour un accès entreprise, connectez votre projet GCP lors de l'intégration. Consultez la page Enterprise pour plus de détails.

---

## Conditions d'utilisation et utilisation des données

> [!WARNING]
> Les agents de codage IA sont connus pour présenter certains risques de sécurité, notamment l'exécution autonome de code, l'exfiltration de données, l'injection de prompts et les risques liés à la chaîne d'approvisionnement. Assurez-vous de surveiller et de vérifier toutes les actions entreprises par l'agent.

En utilisant Antigravity CLI, vous acceptez d'aider à améliorer le produit en autorisant Google à collecter et utiliser vos données d'interactions, conformément aux Conditions d'utilisation de Google et à la Règles de confidentialité de Google. Vous pouvez choisir de vous désinscrire à tout moment via vos paramètres.

### Liens juridiques et confidentialité

- **Conditions d'utilisation** : [antigravity.google/terms](https://antigravity.google/terms)
- **Règles de confidentialité** : [policies.google.com/privacy](https://policies.google.com/privacy)
