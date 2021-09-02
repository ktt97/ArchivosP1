# Servicio PXE (Preboot eXecution Environment)

## DCHP (Dynamic Host Configuration Protocol)

El servicio DHCP sirve para asignar la ip a un número de hosts de forma automática ahorrando el trabajo manual de asignar una ip a cada uno de los computadores en una red. Esto resulta útil para el PXE a la hora de asignar la ip al cliente que use el servicio. Pero para conseguirlo es necesaro configurar la subred, la mascara, el rango de ips utilizables, la ip de boradcast (ultima ip de la red) y la ip del servidor. Para el servicio de PXE se agrega el archivo de instalación dentro del archivo de configuración de DHCP y se activan opciones de boot dentro del mismo. Todo esto se puede ver en el archivo de configuración anexo.

## TFTP (Trivial File Transfer Protocol)

TFTP es un servicio que se usa normalmente en redes locales. Su uso principal es para transferir archivos. En este caso TFTP (Protocolo de transferencia de archivos trivial) presenta una seguridad reducida con respecto al FTP tradicional, es decir, permite que cualquier cliente en la red LAN (local) pueda acceder a él sin mayor autenticación. En el caso del PXE, nos resulta muy util ya que se pretende transferir archivos y realizar instalaciones en multiples clientes. 
En el archivo de configuracion Anexado, se activa este servicio cambiando el comando disable a "NO".

## KICKSTART

Como su nombre lo indica, el archivo KickStart facilita la instalacion desatendida del sistema operativo CENTOS. En dicho archivo se declaran parametros de configuración basicos como el idioma, zona horaria, región, entre otras. Un parametro importante es el enlace con el servicio TFTP, para ello, se realiza la configuracion de la IP del servicio dentro del archivo. De esta manera el cliente del PXE obtiene la ruta para conectarse y obtener los archivos necesarios.

## PXE MENU FILE

Es el menu de configuración inicial para el boot del servicio. Este menu y sus caracteristicas se deben indicar en el archivo de configuración determinado de inicio.
