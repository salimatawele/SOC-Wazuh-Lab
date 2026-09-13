# Synthèse des Tests de Sécurité 

| ID Test | Scénario | Outil | Résultat Attendu | Statut |
| :--- | :--- | :--- | :--- | :--- |
| **TEST-01** | Brute-force RDP / Auth | Hydra (Kali) | Génération d'ID 4625 + Alerte Wazuh (Niveau 10+) | Validé |
| **TEST-02** | PowerShell Suspect | PowerShell (Windows) | Sysmon Event ID 1 + Alerte de processus | Validé |
| **TEST-03** | Scan Réseau | Nmap (Kali) | Sysmon Event ID 3 + Alerte de reconnaissance | Validé |
