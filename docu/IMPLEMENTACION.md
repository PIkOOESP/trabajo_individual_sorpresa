# Dockerizacion de Pets con 2 entornos, neon y local

El trabajo consiste en crear 2 contenedores diferentes usando el mismo codigo, usando 2 docker-compose diferentes apuntando a diferentes properties.

## Estructura del proyecto

'''
/
├── Dockerfile
├── docker-compose.local.yml
├── docker-compose.dev.yml
├──src
|   └──main
|       └──resources
|               ├──application.properties
|               ├──application-neon.properties
|               └──application-local.properties
├── sql/
│   ├── sql_mysql.sql
│   └── sql_neon.sql
├── ...
'''

## Properties

Cada application.properties tiene una conexion a una base de datos:

- Local tiene una conexion a mysql en la misma maquina
- Neon tiene una conexion a PosgreSQL

## Docker-Compose

Cada docker-compose tiene la misma aplicacion pero cada uno apunta a un properties diferente usando el comando 'SPRING_PROFILES_ACTIVE'

## GitHub

En GitHub hay creadas 3 branches:

- feature/local: Crea el docker-compose.local y el application-local.properties
- feature/neon: Crea el docker-compose.neon y el application-neon.properties
- documentacion: Se crea este mismo documento
