1.- editar /etc/resolv.conf y agregar en la primera linea la ip del domain controller

ej. DC = 1.2.3.4

nameserver 1.2.3.4

2.- instalar

apt-get update
apt-get install realmd sssd sssd-tools adcli krb5-user packagekit samba-common samba-common-bin samba-libs resolvconf 

3.- en la configuracion de kerberos poner primero el nombre del realm (reinado) por lo general es en Mayusculas, luego ingresar 
el nombre del controlador de dominio (que puede ser el mismo pero en minusculas).

4.- ejecutar

realm discover domain.com

donde domain.com es el nombre de del dominio a consultar

5.- ingresar al dominio

 realm join -v --user=usuario domain.com
 
 
