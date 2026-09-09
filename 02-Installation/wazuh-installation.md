# Installation du Serveur Wazuh

## 1. Prérequis
- Machine virtuelle Linux (Ubuntu Server recommandé)
- Ressources : 2 vCPU, 4 Go RAM minimum.

## 2. Procédure d'installation
1. Mettre à jour le système :
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
   voir: ![Screenshots des intallations](../06-Screenshots)

2. Télécharger le script d'installation officiel de Wazuh :

````Bash
curl -sO [https://packages.wazuh.com/4.8/wazuh-install.sh](https://packages.wazuh.com/4.8/wazuh-install.sh)
````
3. Lancer l'installation en mode tout-en-un (-a) :

````Bash
sudo bash ./wazuh-install.sh -a -i
````
Récupération des identifiants : À la fin de l'installation, le script génère un résumé contenant l'URL d'accès, l'utilisateur (admin) et un mot de passe sécurisé par défaut. Conserve ces informations précieusement.

````Bash
nom d'utilisateur: admin
Mot de passe du server wazuh:6HWxU?9EVlLZi*VL4hCKmb+XvVwk8fFS
````
4. Accès au Dashboard
- Ouvre un navigateur web depuis ta machine hôte ou ton environnement de test.
- Renseigne l'URL sécurisée : https://<192.168.1.10>
- Ignore l'avertissement de certificat SSL auto-signé du laboratoire et connecte-toi avec l'utilisateur admin et le mot de passe généré.
