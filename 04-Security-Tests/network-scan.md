# Test de Sécurité : Scan Réseau et Reconnaissance

## 1. Objectif du Test
Effectuer un balayage de ports (reconnaissance) depuis Kali Linux pour simuler la phase initiale de repérage d'un attaquant sur le réseau local.

## 2. Méthodologie et Exécution
- **Machine Source :** Kali Linux
- **Machine Cible :** Windows Client
- **Outil utilisé :** `nmap`
- **Commande exécutée :**
  ```bash
  nmap -sS -T4 -p- 192.168.1.15
  ````
## 3. Résultats et Observations
- Événements générés : Activité de connexion TCP SYN massive capturée par Sysmon (Event ID 3 - Network Connection) ou par les journaux de trafic.

- Remontée SIEM : Déclenchement d'une alerte de type Network Scan ou Port Scanning sur le dashboard Wazuh.
