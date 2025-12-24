# Windows Server – DHCP et DNS

## 1. Contexte et objectifs
Mise en place des services DHCP et DNS sur Windows Server 2022 afin de fournir une
infrastructure réseau centralisée et automatisée.

## 2. Architecture réseau
- Réseau : 192.168.10.0/24
- DHCP : 192.168.10.1
- DNS : 192.168.10.2
- Domaine : celiwilli.lan

## 3. Pré-requis
- Windows Server 2022
- IP statique configurée
- Accès administrateur

## 4. Installation du rôle DHCP
### 4.1 Ajout du rôle
Gestionnaire de serveur → Ajouter rôles → Serveur DHCP

📷 screenshots/dhcp/ajout_role.png

### 4.2 Autorisation DHCP
Autoriser le serveur DHCP après installation

📷 screenshots/dhcp/autorisation.png

## 5. Configuration DHCP
### Étendue
- 192.168.10.10 → 192.168.10.99
- Masque : 255.255.255.0

### Exclusions
- 192.168.10.1 → 192.168.10.9
- 192.168.10.100 → 192.168.10.254

### Options
- 003 : 192.168.10.254
- 006 : 192.168.10.2
- 015 : celiwilli.lan

📷 screenshots/dhcp/

## 6. Installation DNS
Ajouter le rôle Serveur DNS

📷 screenshots/dns/installation.png

## 7. Configuration DNS
- Zone principale : celiwilli.lan
- Enregistrements A :
  - dhcp → 192.168.10.1
  - dns → 192.168.10.2

📷 screenshots/dns/

## 8. Tests
- ipconfig /all
- ping celiwilli.lan
- nslookup dhcp.celiwilli.lan
