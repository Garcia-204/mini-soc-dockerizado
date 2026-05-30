# Mini SOC Dockerizado
## Proyecto Integrador - Seguridad en Redes ISER 2026-1
### Distribuidora Pamplona S.A.S.

## Requisitos
- Docker Desktop instalado
- Git instalado
- VMware con Kali Linux (para ataques simulados)

## Despliegue paso a paso

### 1. Clonar el repositorio
git clone https://github.com/Garcia-204/mini-soc-dockerizado.git
cd mini-soc-dockerizado

### 2. Generar certificados
docker compose -f generate-indexer-certs.yml run --rm generator

### 3. Levantar el stack completo
docker compose up -d

### 4. Acceder al dashboard
https://localhost
Usuario: admin
Contraseña: SecretPassword

### 5. Ruta de red para Kali Linux
sudo ip route add 172.21.0.0/16 via 192.168.32.1

## Stack tecnológico
- Wazuh Manager 4.7.0
- Wazuh Indexer 4.7.0
- Wazuh Dashboard 4.7.0
- Nginx (servidor web)
- DVWA (aplicación vulnerable)
- Ubuntu SSH (servidor SSH)

## Incidentes simulados
1. Fuerza bruta SSH con Hydra
2. Escaneo de puertos con Nmap
3. Inyección SQL contra DVWA