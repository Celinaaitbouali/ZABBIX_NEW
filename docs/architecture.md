# Architecture réseau et supervision

## Vue d’ensemble
L’infrastructure repose sur un réseau privé unique supervisé par Zabbix.

## Machines
- Windows Server 2022
  - DHCP : 192.168.10.1
  - DNS : 192.168.10.2
- Zabbix Server (Linux) : 192.168.10.20
- Clients :
  - TrueNAS (Linux)
  - Client Windows

## Réseau
- Réseau : 192.168.10.0/24
- Passerelle : 192.168.10.254

## Flux
- Clients → DHCP/DNS
- Agents Zabbix → Zabbix Server
- Administrateur → Interface Web Zabbix

📷 Voir le schéma dans `architecture/architecture_zabbix.png`
