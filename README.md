# SOC-Wazuh-Lab — Mini SOC et Analyse de Sécurité

## Présentation du Projet
Ce projet consiste à concevoir et déployer un **Mini SOC (Security Operations Center) fonctionnel** dans le cadre d'un laboratoire de cybersécurité. L'objectif n'est pas de construire une infrastructure d'entreprise complexe, mais de mettre en place une chaîne complète de supervision : **de la génération d'événements sur une machine cible jusqu'à la détection, la collecte des logs, la corrélation et l'analyse des alertes de sécurité**.

---

## Architecture du Laboratoire

Le laboratoire repose sur un environnement virtualisé composé de trois machines interconnectées :

```text
┌────────────────────────────────────────┐
│         Wazuh Server (Linux)           │
│  - Wazuh Manager / Indexer / Dashboard │
└───────────────────┬────────────────────┘
                    │
              Logs / Alerts
                    │
┌───────────────────▼────────────────────┐
│            Windows Client              │
│  - Windows 10/11                       │
│  - Sysmon (System Monitor)             │
│  - Wazuh Agent                         │
└───────────────────▲────────────────────┘
                    │
            Tests & Simulations
                    │
┌───────────────────┴────────────────────┐
│         Kali Linux (Attacker)          │
│  - Scénarios d'attaques contrôlés      │
└────────────────────────────────────────┘
```

## Structure du Dépôt GitHub
```
SOC-Wazuh-Lab/
│
├── README.md
│
├── 01-Architecture/
│   ├── network-diagram.png
│   └── architecture.md
│
├── 02-Installation/
│   ├── wazuh-installation.md
│   ├── windows-agent.md
│   └── sysmon-installation.md
│
├── 03-Configuration/
│   ├── wazuh-agent.md
│   ├── sysmon-config.md
│   └── log-collection.md
│
├── 04-Security-Tests/
│   ├── brute-force.md
│   ├── suspicious-powershell.md
│   ├── network-scan.md
│   └── test-results.md
│
├── 05-Alerts/
│   ├── alert-01.png
│   ├── alert-02.png
│   ├── alert-03.png
│   └── analysis.md
│
├── 06-Screenshots/
│   ├── wazuh-dashboard.png
│   ├── sysmon.png
│   ├── agent.png
│   └── alerts.png
│
└── 07-Report/
    └── SOC-Wazuh-Report.md
```
