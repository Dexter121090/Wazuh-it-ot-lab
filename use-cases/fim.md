# Cas d’usage : File Integrity Monitoring (FIM)

Ce cas d’usage démontre la capacité de Wazuh à détecter en temps réel toute modification de fichiers sensibles.

## Exemple de fichier modifié

/etc/resolv.conf — modified — Rule 550 — Level 7

## Résultat

- Détection immédiate de la modification  
- Génération d’une alerte Wazuh  
- Preuve de surveillance en temps réel

## Intérêt SOC

- Détection d’altérations malveillantes  
- Identification de compromissions système  
- Suivi des changements non autorisés

## MITRE ATT&CK

- T1565 – Data Manipulation  
- T1070 – Indicator Removal on Host
