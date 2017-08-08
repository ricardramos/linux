1.- editar /etc/resolv.conf y agregar el DC en la lista de servidores dns, ejemplo el servidor DC = 1.2.3.4

nameserver 1.2.3.4

2.- instalar

primero hacer un update

   apt-get update

luego

   apt-get install realmd ntp adcli sssd samba-common-bin sssd-tools libnss-sss libpam-sss adcli 
     
   
 3.- crear directorio
 
 mkdir -p /var/lib/samba/private
 
 4.- activar ssd
 
 systemctl enable sssd
 
 5.- hacer un discover al dominio
 
 realm discover nombre_de_dominio.tld
 
 6.- conectarse al dominio
 
 realm join -v --user=nombre usuario nombre_de_dominio.tld
 
 7.- salir del dominio
 
 realm leave -v --user=nombre usuario nombre_de_dominio.tld
 
