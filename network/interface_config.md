| # nettools  | #### iproute | #### Descrp |
| ------------- | ------------- |----------------|
| arp -a  | ip neigh  | ver tabla ARP
| arp -i eth0 -d 172.16.10.10  |  ip neigh del 172.16.10.10 dev eth0 |Eliminar MAC Address de la t d r|
| arp -s 172.16.10.10 AA:BB:CC:11:22:33 | ip neigh add 172.16.10.10 lladdr AA:BB:CC:11:22:33 dev eth0 | Setear MAC a direccion IP
| arp -v | ip -s neigh | ver tabla ARP +verbosity |
| ifconfig -a | ip a | ver listado de todas las if de red|
| ifconfig eth0 up  | ip link set eth0 up | iniciar interface de red eth0 |
| ifconfig eth0 down | ip link set eth0 down | bajar interface de red eth0|
| ifconfig eth0 172.16.10.10 | ip addr add 172.16.10.10/24 dev eth0  | Poner direccion IP en eth0 con prefijo/24    |
| ifconfig eth0 netmask 255.255.255.0 | ip addr add 172.16.10.10/24 dev eth0  | Configurar mascaca de subred|
| ifconfig eth0:0 172.16.10.10 | ip addr add 172.16.10.21/24 dev eth0  |  configurar ip secundario en if eth0|
| ifconfig eth0 mtu 9000  | ip link set eth0 mtu 9000 | Cambiar MTU a 9000 Bytes |
| route add -net 172.16.10.0 netmask 255.255.255.0 dev eth0  | ip route add 172.16.10.0/24 dev eth0 |Agregar ruta estatica|
| route delete -net 172.16.10.0 netmask 255.255.255.0 dev eth0|ip route del 172.16.10.0/24|Eliminar ruta estatica|
| route add default gw 172.16.10.1| ip route add default via 172.16.10.1  |  Agregar ruta por default  |
| netstat -rn |  ip route | Ver tabla de ruta|
| netstat -atn | ss| Ver listado de conexiones|
|   |  | |


### otros comandos

> link set

     ip link set eth0 promisc on       Enable promiscuous mode for eth0

> ss Display socket statistics.

    ss -a    Show all sockets (listening and non-listening)
    ss -e    Show detailed socket information
    ss -n    Do not resolve addresses
    ss -p    Show process using the socket

