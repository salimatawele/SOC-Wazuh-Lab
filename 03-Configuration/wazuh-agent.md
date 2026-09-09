# Configuration de l'agent Wazuh

L'agent Wazuh repose sur un fichier de configuration principal nommé `ossec.conf`, situé par défaut dans le répertoire d'installation Windows : 
`C:\Program Files (x86)\ossec-agent\ossec.conf`

## Paramètres clés configurés :
- **Adresse du Manager :** Lien réseau pointant vers l'IP du serveur Wazuh pour l'envoi des alertes et des logs.
- **Fréquence et tampons :** Gestion de la remontée des données et du chiffrement des communications (ports par défaut 1514 / 1515).
