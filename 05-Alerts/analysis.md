# Analyse Détaillée des Incidents 

## Fiche d'Incident #01 — Tentative de Force Brute
- **Date / Heure :** 13/09/2026
- **Cible :** Windows Client (`192.168.1.15`)
- **Source :** Kali Linux (`192.168.1.104`)
- **Gravité :** Élevée (High - Niveau 10)
- **Description technique :** Série de connexions infructueuses répétées sur le service d'authentification, enregistrées via l'événement Windows ID `4625`. Wazuh a corrélé ces échecs pour remonter une alerte de type *Brute-force attack*.
- **Plan de remédiation :** 
  1. Identifier l'adresse IP source et vérifier sa légitimité.
  2. Mettre en place un blocage temporaire (fail2ban ou pare-feu) si l'IP est externe ou non autorisée.
  3. Renforcer la politique de complexité des mots de passe.

## Fiche d'Incident #02 — Exécution PowerShell Suspecte
- **Date / Heure :** 13/09/2026
- **Cible :** Windows Client
- **Gravité :** Moyenne (Medium - Niveau 7)
- **Description technique :** Utilisation des arguments `-NoP -Exec Bypass -W Hidden` capturée par Sysmon (Event ID `1`). Indicateur classique de tentative d'exécution de script malveillant sans interaction utilisateur.
- **Plan de remédiation :**
  1. Restreindre l'accès à l'interpréteur PowerShell via les stratégies de groupe (GPO).
  2. Activer l'audit renforcé de PowerShell (Script Block Logging).
