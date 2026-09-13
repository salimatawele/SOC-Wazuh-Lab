# Test de Sécurité : Attaque par Force Brute 

## 1. Objectif du Test
Simuler une tentative d'authentification intensive (brute-force) depuis la machine attaquante (Kali Linux) vers la machine cible (Windows) afin de tester la capacité du SIEM à détecter des échecs de connexion répétés.

## 2. Méthodologie et Exécution
- **Machine Source (Attaquant) :** Kali Linux (`192.168.1.104`)
- **Machine Cible (Victime) :** Windows Client (`192.168.1.15`)
- **Outil utilisé :** `hydra`
- **Commande exécutée :**
  ```bash
  hydra -l Administrator -P rockyou.txt rdp://192.168.1.15
  ````
## 3. Résultats et Observations

- Événements Windows générés : Apparition massive d'événements d'échec de connexion (Event ID 4625) dans l'observateur d'événements de sécurité Windows.

- Remontée SIEM : L'agent Wazuh transmet les journaux en temps réel. La répétition rapide des échecs déclenche une règle de corrélation de niveau élevé (Brute-force attack / Authentication failure).
