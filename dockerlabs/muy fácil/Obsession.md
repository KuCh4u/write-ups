# 💻 DockerLabs - Obssesion

## Descripción
Máquina vulnerable a un ataque de fuerza bruta con hydra al protocolo SSH.

## Herramientas utilizadas
- Nmap
- Gobuster
- Hydra

## Técnicas aplicadas
- Enumeración de puertos y servicios
- Fuerza Bruta
- Escalada de privilegios con sudo

## Recomendaciones

## Desarrollo del laboratorio
Iniciamos con un escaneo de puertos y servicios con Nmap

![nmap](images/obsession/1.png)

detectamos 3 puertos abiertos con sus respectivos servicios

| Puerto | Servicio | Versión |
|--------|----------|---------|
|   21   | FTP      | vsftpd 3.0.5 |
| 22     | SSH      | OpenSSH 9.6p1 |
| 80     | HTTP     | Apache 2.4.58 |

procedemos a revisar la página alojada en el puerto 80.

![pagina_web](images/obsession/2.png)

parece ser una página normal. Al revisar el código fuente de la página, encontramos un comentario.

![comentario_pag_web](images/obsession/3.png)

esto nos da un indicio, por lo que procedemos a enumerar otras rutas dentro de la página web con la herramienta Gobuster.

![gobuster](images/obsession/4.png)

encontramos dos rutas interesantes **backup** y **important**, al revisar la ruta **http://{{ip_objetivo}}/backup**, encontramos el usuario que estabamos buscando.

![usuario](images/obsession/5.png)

con el usuario que encontramos, procedemos a intentar ingresar por SSH al servidor (recordar el mensaje que encontramos en el código de la página), esto lo realizaremos por fuerza bruta con la herramienta Hydra, el diccionario que utilizaremos será rockyou.txt

![hydra](images/obsession/6.png)

encontramos con exito la contraseña del usuario russoski.

| usuario | contraseña |
|---------|------------|
| russoski | iloveme   |

ingresamos por SSH al servidor.

![ssh_connection](images/obsession/7.png)

al ingresar al servidor, comenzaremos con la escalación de privilegios, por lo que listamos los comandos que podemos ejecutar con sudo.

![sudo_list](images/obsession/8.png)

podemos ejecutar el comando vim con sudo, procedemos a buscar vim en **gtfobins**
![sudo_list](images/obsession/9.png)

encontramos el comando que ejecutaremos para acceder como root

![sudo_list](images/obsession/10.png)

y listo, tenemos acceso como root al sistema.