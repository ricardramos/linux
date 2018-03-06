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
|  |   | |
|   |  | |
|   |  | |
|  |  |
|  |   |    |
|  |   | |
|   |  | |
|   |  | |
|  |  |
|  |   |    |
|  |   | |
|   |  | |
|   |  | |
|  |  |






