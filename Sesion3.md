## Creación y uso de volúmenes


Primero he creado dos volúmenes en mi docker local con los siguientes comandos:


~~~
docker volume create volumen_datos
docker volume create volumen_web
~~~


![](/Imagenes/10.png)


Ahora he creado un contenedor llamado ``c1`` que estará basado en la imagen php versión 7.4 y el servidor apache, que se usará el volumen creado llamado ``volumen_web`` y que sea accesible por el puerto 8080:


![](/Imagenes/11.png)


Después, he creado un contenedor llamado ``c2`` que estará basado en la imagen mariadb, que se usará el volumen creado llamado ``volumen_datos``:


![](/Imagenes/12.png)


Luego, para borrar el volumen ``volumen_datos``, he tenido que parar el contenedor c2 y a continuación borrarlo:


![](/Imagenes/13.png)


El siguinete paso ha sido crear un fichero llamado ``index.html`` que he copiado en la ruta del contenedor ``c1`` para que se pueda visualizar en el navegador:


![](/Imagenes/14.png)


Por último he borrado el contenedor ``c1`` y he creado un contenedor con la misma configuración llamdo ``c3`` pero en el puerto 8081, para ver que se conserva el fichero ``index.html``:


![](/Imagenes/15.png)


## Bind mount para compartir datos


Para este ejercicio he creado una carpeta llamada ``saludo`` en la que hemos creado un fichero llamado ``index.html``:


~~~
mkdir saludo
echo "<h1>HOLA JULIO MANUEL</h1>" > ~/saludo/index.html
~~~


Una vez hemos hecho eso, hemos tenido que crear dos contenedores, con la imagen php con la version 7.4 y el servidor apache, y que hagan un bind mount de la carpeta creada en la carpeta ``/var/www/html``, lo único en lo que se van a diferenciar es en el puerto de acceso:


![](/Imagenes/16.png)


![](/Imagenes/17.png)


Podemos visualizar el contenido del fichero ``index.html`` en el navegador:


![](/Imagenes/18.png)


![](/Imagenes/19.png)


Por último, hemos comprobado que se puede acceder a los contenedores sin necesidad de reiniciarlos al modificar el fichero ``index.html``:


![](/Imagenes/20.png)
