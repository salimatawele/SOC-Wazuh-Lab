# Collecte des Logs et Intégration Sysmon -> Wazuh

Pour que les journaux détaillés générés par Sysmon soient pris en compte et transmis au serveur Wazuh, l'agent Windows doit écouter le canal d'événements opérationnel de Sysmon.

## 1. Modification du fichier `ossec.conf`
1. Ouvre le Bloc-notes (Notepad) **en tant qu'Administrateur**.
2. Ouvre le fichier de configuration de l'agent : `C:\Program Files (x86)\ossec-agent\ossec.conf`.
3. Vérifie la présence du bloc de lecture pour les journaux d'événements Windows (Event Channel) pointant vers Sysmon :
   ```xml
   <localfile>
     <location>Microsoft-Windows-Sysmon/Operational</location>
     <log_format>eventchannel</log_format>
   </localfile>
   ```
4. Redémarrage du service agent
Appliquer les modifications en redémarrant le service Wazuh Agent via une invite PowerShell administrateur :

````PowerShell
Restart-Service wazuh
````
