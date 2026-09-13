# Rapport Technique — Mini SOC & Analyse de Sécurité

## Table des Matières
1. Introduction et Contexte
2. Objectifs du Projet
3. Architecture du Laboratoire
4. Installation et Configuration des Composants
5. Scénarios de Tests de Sécurité (Simulations)
6. Analyse des Alertes et Incidents
7. Recommandations et Durcissement (Hardening)
8. Conclusion

## 1. Introduction et Contexte
Dans le cadre d'une montée en compétences en cybersécurité, ce projet consiste à concevoir et déployer un **Mini SOC (Security Operations Center)** opérationnel. L'objectif est de reproduire le cycle complet de gestion des incidents de sécurité : de la journalisation granulaire des systèmes jusqu'à la détection proactive et l'analyse forensique des alertes.

## 2. Objectifs du Projet
- Déployer et configurer un serveur SIEM centralisé (**Wazuh**).
- Durcir et superviser un poste client **Windows** à l'aide de **Sysmon**.
- Simuler des attaques réalistes et contrôlées depuis un environnement **Kali Linux**.
- Documenter et analyser les alertes de sécurité sous forme de fiches d'incidents professionnelles.

## 3. Architecture du Laboratoire
Le laboratoire repose sur un environnement virtuel virtualisé interconnecté :
- **Serveur SIEM (Ubuntu / Wazuh) :** Centralisation des flux et tableau de bord.
- **Machine Cible (Windows + Sysmon) :** Collecte des journaux système et applicatifs.
- **Machine Attaquante (Kali Linux) :** Génération de trafic de test et de scénarios d'intrusion.

## 4. Installation et Configuration
- **Serveur :** Déploiement automatisé du manager, de l'indexeur et du dashboard Wazuh.
- **Agents :** Enregistrement de l'agent Windows pointant vers l'IP du serveur Wazuh.
- **Sysmon :** Application d'une configuration XML rigoureuse (`sysmonconfig.xml`) et intégration du canal de log `EventChannel` dans le fichier de configuration de l'agent Wazuh (`ossec.conf`).

## 5. Scénarios de Tests de Sécurité
Trois scénarios majeurs ont été joués pour valider la chaîne de détection :
1. **Force Brute :** Tentatives d'authentification répétées.
2. **PowerShell Suspect :** Exécution de commandes obfusquées.
3. **Scan Réseau :** Balayage Nmap de reconnaissance.

## 6. Analyse des Alertes et Incidents
Les événements bruts (tels que les échecs de connexion Event ID `4625` ou les créations de processus Sysmon Event ID `1`) ont été transformés par le moteur de règles de Wazuh en alertes exploitables. L'analyse détaillée de ces alertes a permis de valider le bon fonctionnement de la chaîne d'alerte et d'identifier précisément les vecteurs d'attaque simulés.

## 7. Recommandations et Durcissement
Pour mitiger les risques identifiés lors des tests :
- Restreindre l'utilisation de PowerShell via les stratégies de groupe (GPO).
- Mettre en place des politiques de verrouillage de compte après plusieurs échecs consécutifs.
- Assurer une surveillance continue des connexions distantes non autorisées.

## 8. Conclusion
Ce projet a permis de concrétiser les concepts fondamentaux de la supervision de sécurité, de la configuration des agents SIEM et de l'analyse d'incidents, fournissant une base solide et documentée pour un portfolio professionnel.
