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
