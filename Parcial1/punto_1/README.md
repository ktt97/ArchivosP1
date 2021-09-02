# Tunel del servicio HTTP

## PORT FORWART
Permite la conexión entre los puertos de la maquina virtual (servidor) y el host (maquina real) lo que hace posible acceder al servidor HTTP usando localhost e indicando el puerto de acceso (que a su vez está conectado al puerto de HTTP del servidor), para esto se configura el vagrantfile de la maquina y se indica que puerto se desea conectar entre host y maquina virtual por ejemplo el puerto 80 del servidor y el 8080 del host (esto se puede ver en el Vagrantgile anexado).

servidor.vm.network "forwarded_port", guest: 80, host: 8080

## TUNEL NGROK Y VAGRANT SHARE

A continuacion, continuando con el acceso al servidor, especialmente al servicio HTTP, ahora fue posible generar el acceso desde acualquier lugar de internet mediante un enlace URL. En este caso, mediante una cuenta NGROK, y ejecuandolo en nuestro host, esta aplicacion genera un URL temporal. Sin embargo, para obtener el acceso debemos ejecutar nuevamente ngrok. Para evitar este proceso, se realiza la instalacion de Vagrant share:

kvagrant plugin install vagrant-share

Luego simplemente se escribe la sentencia "Vagrant share" y nos arroja el URL temporal evitandonos ejecutar nuevamente NGROK
