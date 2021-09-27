# Servidor WEB Apache PHP

Este docker-compose permite levantar facilmente un servidor web LAMP incluyendo DNS

***

##  Instrucciones

**Notas:** Debes tener docker y docker compose instalado.

1. Crear la red "servers"

``docker network create --subnet 172.128.10.0/24 --gateway 172.128.10.1 -d bridge servers``

2. Levantar contenedores

``docker-compose up -d``

3. Opcional en linux systemd-resolved debe ser desactivado para usar coredns

``sudo systemctl disable systemd-resolved.service``

``sudo systemctl stop systemd-resolved``


``sudo rm -f /etc/resolv.conf``

``sudo tee /etc/resolv.conf << END
nameserver 8.8.8.8
nameserver 1.1.1.1
END``
