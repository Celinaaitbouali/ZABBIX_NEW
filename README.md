# ZABBIX_NEW
## Supervision & redondance d’une infrastructure réseau

## 📌 Contexte et objectifs
Ce projet a pour objectif de mettre en place une solution de **supervision centralisée**
à l’aide de **Zabbix**, intégrée dans une infrastructure réseau d’entreprise.

Les objectifs principaux sont :
- Superviser des systèmes **Windows et Linux**
- Détecter les incidents via des **triggers**
- Envoyer des **alertes par e-mail**
- Mettre en place une **redondance** du serveur Zabbix (optionnelle)

---

## 🏗️ Architecture du projet
- **Zabbix Server principal** : `192.168.10.20`
- **Zabbix Server secondaire** (redondance)
- **Clients supervisés** :
  - Serveur **TrueNAS (Linux)**
  - Client **Windows**
- Réseau : `192.168.10.0/24`

📷 Le schéma d’architecture est disponible dans le dossier :

