# ZABBIX_NEW  
## Supervision & redondance d’une infrastructure réseau

---

## 📌 Contexte et objectifs

Ce projet a pour objectif de mettre en place une solution de **supervision centralisée**
à l’aide de **Zabbix**, intégrée dans une infrastructure réseau d’entreprise.

Les objectifs principaux sont :
- Superviser des systèmes **Windows et Linux**
- Détecter les incidents via des **triggers**
- Envoyer des **alertes par e-mail**
- Mettre en place une **redondance** du serveur Zabbix (optionnelle)

📸 **Capture à insérer** : vue globale du projet ou page d’accueil Zabbix

---

## 🏗️ Architecture du projet

- **Zabbix Server principal** : `192.168.10.20`
- **Zabbix Server secondaire** (redondance)
- **Clients supervisés** :
  - Serveur **TrueNAS (Linux)**
  - Client **Windows**
- Réseau : `192.168.10.0/24`

📸 **Capture à insérer** : schéma d’architecture réseau Zabbix

---

## 🌐 Architecture réseau détaillée

- Serveur DHCP : `192.168.10.1`
- Serveur DNS : `192.168.10.2`
- Passerelle : `192.168.10.254`
- Domaine : `celwill.lan`

📸 **Capture à insérer** : configuration IP / plan d’adressage

---

## 🔁 Flux de supervision

- Les agents Zabbix installés sur les clients communiquent avec le serveur Zabbix via le port **10050**
- Le serveur Zabbix écoute sur le port **10051**
- L’interface web est accessible via **HTTP/HTTPS**

📸 **Capture à insérer** : vue des hôtes dans l’interface Zabbix (Monitoring → Hosts)

---

## 🧩 Évolutivité et redondance

L’architecture permet :
- L’ajout de nouveaux hôtes supervisés
- La mise en place d’un serveur Zabbix secondaire
- La supervision SNMP d’équipements réseau

📸 **Capture à insérer** : configuration ou documentation de la redondance (optionnel)

---

## 🖼️ Schéma d’architecture

Le schéma ci-dessous illustre l’architecture de supervision mise en place :

![Architecture Zabbix](../architecture/architecture_zabbix.png)
