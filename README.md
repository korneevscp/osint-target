# AutoPentest Advanced v3.0

**By X01.EXE** — Outil de pentest automatisé avec détection CVE, matching de versions, et génération d'exploits.

## 🎯 Vue d'ensemble

AutoPentest Advanced est un framework de test d'intrusion automatisé qui combine :
- **Nmap** pour le scan de ports et la détection de versions
- **WhatWeb** pour l'identification des technologies web
- **Base CVE locale** (150+ CVE) couvrant Apache, Nginx, IIS, WordPress, Drupal, MySQL, Redis, etc.
- **API NVD (NIST)** pour l'enrichissement temps réel des vulnérabilités
- **Nikto** pour le scan de vulnérabilités web
- **Génération automatique d'exploits** par CVE et par service détecté
- **Rapport HTML** complet avec résumé exécutif

## ✨ Fonctionnalités

### 🔍 Reconnaissance
- Scan de ports rapide (nmap optimisé `-T3 -n -Pn`)
- Détection de versions de services
- Fingerprinting web via WhatWeb (agressivité minimale `-a 1`)
- Scan de vulnérabilités web via Nikto (filtrage `-Tuning 123`)

### 🎯 Détection CVE
- Base de données locale de 150+ CVE classées par logiciel/version
- Matching exact, partiel et wildcard
- Enrichissement temps réel via API NVD (NIST) avec scores CVSS
- Dédoublonnage automatique

### ⚡ Exploitation
- Génération de commandes d'exploitation spécifiques par CVE :
  - Apache Path Traversal & RCE (CVE-2021-41773, CVE-2021-42013)
  - EternalBlue / SMBGhost (CVE-2017-0143, CVE-2020-0796)
  - Drupalgeddon 2 (CVE-2018-7600)
  - Heartbleed (CVE-2014-0160)
  - Ghostcat (CVE-2020-1938)
  - GitLab RCE (CVE-2021-22205)
  - Joomla! Info Disclosure (CVE-2023-23752)
  - +120 autres CVE couvertes
- Exploits par service : MySQL, PostgreSQL, Redis, RDP, SMB, VNC, WinRM, MongoDB, FTP, SMTP, DNS, Telnet, Rsync

### 📊 Rapports
- Rapport HTML complet avec design moderne (thème dark)
- Statistiques : CVE trouvées, exploits générés, ports ouverts
- Résumé exécutif avec niveau de risque
- Sections détaillées : reconnaissance, CVE, exploitation, vulnérabilités Nmap, scan web

### 🌐 Interface Web
- Interface Flask avec authentification sécurisée
- Sessions utilisateur persistantes
- Barre de progression en temps réel
- Historique des scans stocké en SQLite
- Téléchargement des rapports HTML
- Limite de 3 scans simultanés
- Statut des outils disponibles

## 🛠️ Prérequis

### Outils requis
```bash
# Installation sur Kali Linux / Debian
sudo apt update
sudo apt install -y nmap whatweb nikto python3 python3-pip

# Paquets Python
pip3 install flask
