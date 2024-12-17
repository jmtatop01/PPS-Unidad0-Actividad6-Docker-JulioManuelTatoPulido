## Despliegue de Nextcloud

### Instalación de Docker Compose

Para empezar, he tenido que ejecutar estos dos comandos:

~~~
sudo apt update
sudo apt install docker-compose -y
~~~

### Escenario Docker-compose

Después, he creado una carpeta con el comando ``mkdir nextcloud`` en la que hemos descargado un archivo llamado **docker-compose.yml**, con las siguientes líneas:

![](/Imagenes/28.png)

He ejecutado el comando ``docker-compose ip -d`` para levantar los contenedores, y el comando ``docker ps`` para que se puedan ver los contenedores funcionando:

![](/Imagenes/29.png)

### Comprobación del contenedor

Por último, he comprobado en el navegador que se ha levantado correctamente el contenedor:

![](/Imagenes/30.png)
