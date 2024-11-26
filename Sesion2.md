# Servidor web
## Creación de  index.html


Para empezar creamos un contenedor que ejecute la imagen "php:7.4-apache" y que se llame "web" para que se pueda acceder desde el puerto 8000, y colocarlo en la raíz "/var/www/html" y guardarlo en un documento llamado "index.html", lo podemos hacer con el siguiente comando:


~~~
>docker run -d --name web -p 8000:80 php:7.4-apache
>docker exec -it web bash echo "<h1> Hola soy Julio Manuel Tato Pulido</h1>" > /var/www/html/index.html
>exit
~~~


Comprobandolo en el navegador, buscando "http://localhost:8000/index.html":


![](/Imagenes/5.png)


## Creación de  index.php


En ese mismo directorio hemos colocado el archivo "index.php", con el comando:


~~~
docker exec web bash -c ‘echo “<?php echo phpinfo(); ?>” > /var/www/html/index.php’
~~~


Comprobandolo también en el navegador, buscando "http://localhost:8000/index.php" :


![](/Imagenes/6.png)


Después de crear los dos ficheros he comprobado el tamaño del contenedor con el comando ``docker ps -s | grep web``:


![](/Imagenes/7.png)


# Servidor de base de datos
## Creación de bbdd


He creado un contenedor llamado "bbdd" que tiene la imagen de "Mariadb" y para que sea accesible por el puerto 3336:


~~~
docker run -d --name bbdd
-p 3336:3306 \
-e MYSQL_ROOT_PASSWORD=root \
-e MYSQL_DATABASE=prueba \
-e MYSQL_USER=invitado \
-e MYSQL_PASSWORD=invitado \
mariadb
~~~


Después, me he instalado una aplicación llamada "Dbeaver", que se trata de un cliente de base de datos, con la que me he conseguido conectar al servidor de base de datos:


![](/Imagenes/8.png)


Por último, he comprobado que no se puede borrar la imagen "Maridb" mientras esta creado el contenedor "bbdd":


![](/Imagenes/9.png)
