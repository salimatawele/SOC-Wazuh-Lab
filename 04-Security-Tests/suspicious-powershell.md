### Test de Sécurité : Activité PowerShell Suspecte 

## 1. Objectif du Test
Exécuter une commande ou un script obfusqué via PowerShell sur la machine Windows pour valider la surveillance fine des processus par Sysmon et leur détection par Wazuh.

## 2. Méthodologie et Exécution
- **Machine Cible :** Windows Client
- **Commande de test exécutée en administrateur :**
  ```powershell
  powershell -NoP -NonI -W Hidden -Exec Bypass -Command "Write-Host 'Test Detection Sysmon Wazuh'"
  ````
## 3. Résultats et Observations
- Événements Sysmon générés : Sysmon Event ID 1 (Process Creation) capturant la ligne de commande complète avec les arguments de contournement de politique d'exécution.

- Remontée SIEM : Wazuh analyse la ligne de commande suspecte et génère une alerte de niveau moyen à élevé signalant l'utilisation de paramètres d'obfuscation PowerShell.
