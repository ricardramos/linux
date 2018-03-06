### comandos mas utilizados para configuracion de la red en GNU/Linux

> la siguiente tabla muestra 2 formas de ejecutar el comando, mismo resultado pero con distinto software

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
    
> arping    Send ARP request to a neighbour host

    arping -I eth0 192.168.1.1    Send ARP request to 192.168.1.1 via interface eth0
    arping -D -I eth0 192.168.1.1    Check for duplicate MAC addresses at 192.168.1.1 on eth0

> ethtool     Query or control network driver and hardware settings

    ethtool -g eth0    Display ring buffer for eth0
    ethtool -i eth0    Display driver information for eth0
    ethtool -p eth0    Identify eth0 by sight, typically by causing LEDs to blink on the network port
    ethtool -S eth0    Display network and driver statistics for eth0
