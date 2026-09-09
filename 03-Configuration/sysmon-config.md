# Configuration de Sysmon (`sysmonconfig.xml`)

Le fichier de configuration filtre et structure les événements capturés par Sysmon pour éviter le bruit tout en conservant les traces critiques pour un analyste SOC :

- **Event ID 1 (Process Creation) :** Permet de tracer l'exécution de tout nouveau processus, incluant la ligne de commande complète et l'empreinte de hachage.
- **Event ID 3 (Network Connection) :** Enregistre les connexions TCP/UDP établies par les processus.
- **Event ID 11 (File Creation) :** Surveille la création de fichiers dans les emplacements sensibles.
- **Event ID 22 (DNS Query) :** Journalise les requêtes de résolution de noms, utiles pour détecter le trafic de command and control (C2).
