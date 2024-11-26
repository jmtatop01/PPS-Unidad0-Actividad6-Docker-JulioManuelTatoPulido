## Creación de contenedor
En este ejercicio he creado un contenedor demonio a partir de una imagen nginx, llamandose "servidor_web" y que se acceda desde el puerto 8181, con el comando ``docker run -d --name servidor_web -p 8181:80 nginx``


![](/Imagenes/1.png)


## Comprobación


Y lo podemos comprobar que está funcionando, si buscamos en el navegador con la ip de nuestra máquina y el puerto al que se ha conectado el contenedor:


![](/Imagenes/2.png)


Ahora, vamos a comprobar que imágenes tenemos en nuestro registro local:


![](/Imagenes/3.png)


## Eliminación


Y, por último, hemos parado el contenedor con el comando ``docker stop servidor_web`` y eliminado con el comando ``docker rm servidor_web``


![](/Imagenes/4.png)
