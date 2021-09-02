# Servicio PXE (Preboot eXecution Environment)

## DCHP (Dynamic Host Configuration Protocol)

El servicio DCHP nos permite configurarle a la maquina servidor, un rango de direcciones IP utilizables, direccion Broadcast. Estas configuraciones permiten posteriormente al servidor PXE, enlazar maquinas clientes y asignarle su respectiva dirección IP de manera automática. Teniendo en cuenta que el servicio PXE debe facilitar la instalacion de archivos o sistemas operativos de manera desatendida, el DHCP en gran parte permite iniciar una conexión desatendida.

## TFTP (Trivial File Transfer Protocol)

El servicio TFTP suele usarse en redes de computadores y permite una transmisión de archivos como lo es el servicio FTP, pero de forma muy sencilla y básica, incluso a diferencia del FTP, TFTP usa el puerto 69 y el protocolo de transporte UDP en lugar de TCP. Para activarlo se configura la opción de disable a "no" en el archivo de configuración de TFTP.

## KICKSTART

Como se explicó anteriormente, las instalaciones desatendidas no requieren interacción humana. Para que toda la instalación se realice automáticamente es necesario configurar un archivo de inicio rápido indicando todas las configuraciones iniciales que va a ejecutar el servicio de PXE, por ejemplo: la zona horaria, el idioma, los paquetes de descarga, etc. En este archivo se configura el acceso al TFTP indicando la ip del servidor y la ruta de acceso que se ha configurado con una contraseña encriptada que se ha obtenido durante el proceso de configuración del servicio PXE.

## PXE MENU FILE

Es el menu de configuración inicial para el boot del servicio. Este menu y sus caracteristicas se deben indicar en el archivo de configuración determinado de inicio.
