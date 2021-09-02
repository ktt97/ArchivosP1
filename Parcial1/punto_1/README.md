# Tunel del servicio HTTP

## PORT FORWART

El port forwarding nos permite comunicar la maquina servidor desde uno de sus puertos, en este caso el 80, con nuestro host (Windows) en su puerto 8080. La comunicación permite al host acceder al servicio HTTP del servidor usando localhost indicando los puertos anteriormente descritos. 
La configuración se realiza directamente desde el vagrantfile (anexado) en la carpeta raiz usando la siguientes sintaxis:

servidor.vm.network "forwarded_port", guest: 80, host: 8080

## TUNEL NGROK Y VAGRANT SHARE

A continuacion, continuando con el acceso al servidor, especialmente al servicio HTTP, ahora fue posible generar el acceso desde acualquier lugar de internet mediante un enlace URL. En este caso, mediante una cuenta NGROK, y ejecuandolo en nuestro host, esta aplicacion genera un URL temporal. Sin embargo, para obtener el acceso debemos ejecutar nuevamente ngrok. Para evitar este proceso, se realiza la instalacion de Vagrant share:

vagrant plugin install vagrant-share

Luego simplemente se escribe la sentencia "Vagrant share" y nos arroja el URL temporal evitandonos ejecutar nuevamente NGROK
