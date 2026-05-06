# Cas d’usage : Brute-force SSH → Compromission réussie

Ce cas d’usage simule une attaque brute-force réelle sur un serveur Debian.

## Commande Hydra utilisée

hydra -l dexter -P /usr/share/wordlists/rockyou.txt -t 1 -W 3 ssh://192.168.100.11<img width="752" height="270" alt="image" src="https://github.com/user-attachments/assets/e97813af-9690-43e5-97d2-840e7a8f2c31" />

## Résultat

- Mot de passe trouvé : dexter  
- Compromission du compte utilisateur<img width="1358" height="722" alt="image" src="https://github.com/user-attachments/assets/0b24ecc8-c2bc-4868-a6f9-8d2dde142f20" />

## Alertes Wazuh

- Rule 5710 – SSH authentication failed  
- Rule 5712 – Multiple SSH authentication failures  
- Rule 5720 – Possible brute-force attack  
- Rule 5503 – Successful SSH login
- <img width="1367" height="658" alt="image" src="https://github.com/user-attachments/assets/92e3dfc4-4bf4-4b6c-9a4f-e57650b30476" />
<img width="1357" height="688" alt="image" src="https://github.com/user-attachments/assets/4724dea0-f9cf-41ff-b176-eb2158608830" />

- <img width="1342" height="708" alt="image" src="https://github.com/user-attachments/assets/b838b046-f135-40f9-96fb-9c3dcd32576d" />
<img width="1337" height="757" alt="image" src="https://github.com/user-attachments/assets/20bcdbc5-ed67-42f6-9871-4f544afcdc42" />


<img width="1350" height="686" alt="image" src="https://github.com/user-attachments/assets/1e71cf7a-65a3-4a3d-b5b4-424c59e4d0d8" />

## MITRE ATT&CK

- T1110 – Brute Force  
- T1078 – Valid AccountsRésultats de l’analyse des vulnérabilités

- 48 vulnérabilités critiques  
- 413 vulnérabilités hautes  
- 402 vulnérabilités moyennes  

## Score CIS Benchmark

- Score global : 32%  
- Recommandations de durcissement disponibles dans Wazuh

  
<img width="1347" height="387" alt="image" src="https://github.com/user-attachments/assets/53eacb17-63e6-4753-ac94-415ff40d23c7" />

![Uploading image.png…]()



