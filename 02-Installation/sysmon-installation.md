# Installation de Sysmon (System Monitor)

## 1. Introduction
Sysmon est un outil officiel Microsoft Sysinternals qui s'exécute en tant que service système et pilote de périphérique. Il journalise de manière très granulaire les créations de processus, les connexions réseau et les modifications de fichiers, fournissant les données indispensables à l'analyse SOC.

---

## 2. Guide d'installation pas à pas

### A. Téléchargement des composants
1. Télécharge l'archive officielle de **Sysmon** depuis le site de Microsoft Sysinternals.
2. Télécharge un fichier de configuration XML recommandé et largement éprouvé (par exemple, le fichier `sysmonconfig.xml` de *SwiftOnSecurity* sur GitHub).
3. Crée un dossier dédié sur ta machine Windows (par exemple `C:\Sysmon`) et place-y l'exécutable Sysmon ainsi que ton fichier de configuration renommé en `sysmonconfig.xml`.

### B. Installation via PowerShell
1. Ouvre **PowerShell en tant qu'Administrateur**.
2. Positionne-toi dans le dossier de travail :
   ```powershell
   cd C:\Sysmon
   ```
3. Installe Sysmon en appliquant le fichier de configuration XML :

````PowerShell
.\sysmon.exe -i sysmonconfig.xml
````
4. Accepte le contrat de licence qui s'affiche.

5. Vérification du service
Vérifie que le service Sysmon s'exécute correctement sur le système :

````PowerShell
Get-Service *sysmon*
````
(Le statut doit indiquer Running).
