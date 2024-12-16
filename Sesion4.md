## Redes docker

### Creación de redes
Para empezar vamos a crear dos redes de tipo **bridge** con las siguientes configuraciones:

Nombre: red1
Dirección de red: 172.28.0.0
Máscara de red: 255.255.0.0
Gateway: 172.28.0.1

Nombre: red2
El resto de los datos será proporcionados automáticamente por Docker.

Se han configurado con los siguientes comandos respectivamente:

~~~
docker network create \
> --driver bridge \
> --subnet=172.28.0.0/16 \
> --gateway=172.28.0.1 \
> red1 
~~~

~~~
docker network create \
> --driver bridge \
> red2
~~~

### Creación de contenedores

Después, he creado un contenedor llamado u1 con las siguientes características:

- Nombre : u1
- Nombre del host : host1
- Red : red1
- Ip : 172.28.0.10
- Imagen : ubuntu:20.04

Lo haremos de con los siguientes comandos:

![](/Imagenes/21.png)

En este contenedor se nos pide que instalemos la aplicación **ping** la cuál se instala con el comando ``apt update && apt install -y inetutils-ping`` :

~~~
docker exec -it u1 bash
root@host1:/# apt update && apt install -y inetutils-ping
~~~

Luego, he creado otro contenedor llamado **u2** , con una configuración muy parecida al contenedor anterior:

![](/Imagenes/22.png)

### Comprobación de conexión

A continuación, también se ha instalado la aplicación ping:

~~~
docker exec -it u2 bash
root@host2:/# apt update && apt install -y inetutils-ping
~~~

Hemos comprobado que no se pueden hacer ping entre los dos contenedores, ni por ip ni por nombre, ya que no estan dentro de la misma red:

![](/Imagenes/23.png)

Por último, hemos comprobado que si cambiamos el contenedor **u1** con el comando ``docker network connect red2 u1`` a la red2 para comprobar que si se pueden hacer ping:

![](/Imagenes/24.png)

## Despliegue de Nextcloud + mariadb/postgreSQL

Para empezar he creado una red de tipo bridge con el comando ``docker network create nextcloud-net``.

### Creación de contenedor de la base de datos

Se me ha pedido que cree un contenedor de la base de datos y que se haga con los siguientes parametros:

![](/Imagenes/25.png)

### Creación de contenedor de la aplicación

También, se me ha pedido que se cree un contenedor de la aplicación con los siguientes parametros:

![](/Imagenes/26.png)

### Comprobación de la aplicación

Por último, he comprobado que puedo acceder a la aplicación con la ip del servidor y el puerto desde el navegador:

![](/Imagenes/27.png)
