# Architecture du Mini SOC

## 1. Vue d'ensemble
Mise en place d'un environnement de surveillance minimaliste (Mini SOC) pour collecter, détecter et analyser des événements de sécurité sur un système Windows.

## 2. Schéma d'Architecture
*(Ajoute ton image d'architecture sous `01-Architecture/network-diagram.png`)*

## 3. Composants du Laboratoire
- **Serveur SIEM (Ubuntu / Wazuh) :** Centralise la collecte des logs et l'analyse via le dashboard.
- **Machine Cible (Windows + Sysmon) :** Génère les événements système et applicatifs détaillés.
- **Machine Attaquante (Kali Linux) :** Utilisée pour simuler des scénarios d'attaques contrôlés.
