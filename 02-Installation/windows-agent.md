#### `02-Installation/windows-agent.md`

# Installation de l'agent Wazuh sur Windows

## 1. Enregistrement de l'agent
1. Se connecter au Dashboard Wazuh.
2. Aller dans **Agents > Deploy new agent**.
3. Sélectionner **Windows**, renseigner l'IP du serveur Wazuh et nommer l'agent (ex: `Windows-Lab`).
4. Copier la commande PowerShell générée.

## 2. Exécution sur la cible Windows
1. Ouvrir **PowerShell en tant qu'Administrateur**.
2. Coller et exécuter la commande d'installation.
3. Démarrer le service Wazuh :
   ```powershell
   NET START wazuh
