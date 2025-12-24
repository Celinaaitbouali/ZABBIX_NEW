# ZABBIX_NEW  
## Supervision & redondance d’une infrastructure réseau

---

## 📌 Contexte et objectifs

Ce projet a pour objectif de mettre en place une solution de **supervision centralisée**
à l’aide de **Zabbix**, intégrée dans une infrastructure réseau d’entreprise.

Les objectifs principaux sont :
- Superviser des systèmes **Windows et Linux**
- Collecter des métriques système (CPU, RAM, disque, réseau)
- Détecter les incidents via des **triggers**
- Envoyer des **alertes par e-mail**
- Mettre en place une **redondance du serveur Zabbix** (optionnelle)

📸 **Capture à insérer**  
`screenshots/zabbix_dashboard.png`  
➡️ Vue du tableau de bord Zabbix après installation

---

## 🏗️ Architecture globale

L’infrastructure repose sur un réseau privé `192.168.10.0/24` intégrant des services
DHCP, DNS et Active Directory ainsi qu’un serveur de supervision Zabbix.

### Composants

- **Windows Server**
  - DHCP : `192.168.10.1`
  - DNS : `192.168.10.2`
  - Domaine : `celwill.lan`

- **Zabbix Server principal**
  - Adresse IP : `192.168.10.20`
  - Rôle : collecte des métriques, gestion des alertes et interface web

- **Zabbix Server secondaire** *(optionnel)*
  - Rôle : redondance et continuité de service

- **Clients supervisés**
  - Serveur **TrueNAS (Linux)**
  - **Client Windows**

📸 **Capture à insérer**  
`screenshots/zabbix_hosts.png`  
➡️ Liste des hôtes supervisés (Monitoring → Hosts)

---

## 🌐 Architecture réseau

- Réseau : `192.168.10.0/24`
- Passerelle : `192.168.10.254`
- DNS : `192.168.10.2`
- DHCP : `192.168.10.1`

📸 **Capture à insérer**  
`screenshots/ip_plan.png`  
➡️ Plan d’adressage ou configuration IP serveur

---

## 🔁 Flux de supervision

- Les **agents Zabbix** communiquent avec le serveur sur le port **10050**
- Le **serveur Zabbix** écoute sur le port **10051**
- L’interface Web est accessible via **HTTP / HTTPS**
- Les clients obtiennent leur configuration IP via **DHCP**

📸 **Capture à insérer**  
`screenshots/agent_available.png`  
➡️ État "Agent available" sur un hôte

---

## 🔄 Redondance (optionnelle)

Un serveur Zabbix secondaire peut être ajouté afin d’assurer la continuité de la supervision
en cas de défaillance du serveur principal.

📸 **Capture à insérer (optionnelle)**  
`screenshots/zabbix_redundancy.png`  
➡️ Documentation ou configuration de la redondance

---

## 🖼️ Schéma d’architecture

Le schéma suivant illustre l’architecture de supervision mise en place :

![Architecture Zabbix](../architecture/architecture_zabbix.png)
