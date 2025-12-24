# Installation Zabbix Server

## 1. Pré-requis
- Ubuntu 22.04
- IP fixe : 192.168.10.20
- Accès Internet

## 2. Installation
```bash
sudo apt update
sudo apt install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf mariadb-server
```
## 3. Base de données
```bash
sudo mysql
CREATE DATABASE zabbix;
CREATE USER zabbix@localhost IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON zabbix.* TO zabbix@localhost;
FLUSH PRIVILEGES;
```

## 4. Configuration
```bash
/etc/zabbix/zabbix_server.conf
DBPassword=password
```

## 5. Démarrage 
```bash
sudo systemctl restart zabbix-server apache2 mariadb
```
