# Servidor WEB Apache PHP

Este docker-compose permite levantar facilmente un servidor web LAMP incluyendo DNS

##  Instrucciones

**Notas:** Debes tener docker y docker compose instalado.

1. Crear la red "servers"

`docker network create --subnet 172.128.10.0/24 --gateway 172.128.10.1 -d bridge servers`

1. Levantar contenedores

`docker-compose up -d`
