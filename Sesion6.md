## Creación de una imagen a partir de un contenedor

### Arranque del contenedor

Para empezar, he creado un contenedor con una imagen base **debian** :

![](/Imagenes/31.png)

### Preparación del escenario

Para hacer los siguientes pasos necesitamos instalar unos paquetes:

~~~
apt-get update
apt-get install -y inetutils-ping iproute2 dnsutils
~~~

### Creación de cuenta

También necesitamos tener una cuenta de Docker hub, la cuál se ha conectado con la carpeta donde se encuentra el contenedor.

### Creación de imagen

Después, he creado una imagen a partir de un contenedor con el siguiente comando:

![](/Imagenes/32.png)

### Subida de imagen

He, subido la imagen a mi repositorio de Docker Hub con el siguiente comando:

~~~
docker push jmtatop011/comandos_redes
~~~

![](/Imagenes/33.png)

### Descarga de imagen

He descargado la imagen del repositorio, para después crear un contenedor nuevo:

![](/Imagenes/34.png)
