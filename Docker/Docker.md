## Instalando Docker

Una vez dentro de nuestra maquina virtual, tendremos que abrir la terminal. Estando dentro de la terminal, escribiremos:
```
sudo apt update
sudo apt install docker.io
```
Esto nos instalara el docker en nuestra maquina virtual.

![Instalar Docker](/Docker/Instalar-Docker.png)

Si intentamos ejecutar el comando "docker ps" en nuestra terminal para ver los contenedores que tenemos y esta nos muestra un mensaje de error, debemos de ejecutar los siguientes comandos de la forma que se muestra en la siguiente imagen:
```
sudo usermod -aG docker ${USER}
su - ${USER}
sudo usermod -aG docker "nombre de usuario"
```
Esto nos dara permisos para que nuestro usuario pueda ejecutar el comando "docker" en nuestra terminal.

![Super usuario Docker](/Docker/Super-usuario-Docker.png)

Después de tener permisos para ejecutar el comando "docker", debemos de descargar la imagen de docker que queremos que nuestro contenedor use. Para ello, debemos ejecutar el siguiente comando:
```
docker pull bkimminich/juice-shop //Esto nos descargara la imagen de docker.

NOTA: Esta linea se puede ejecutar con cualquier usuario, no solo con el superusuario como muestra la foto de abajo.
```
Una vez ejecutada ese comando, podes ejecutar:
```
docker image ls //Esto nos mostrara las imagenes que tenemos en nuestra maquina virtual.
```

![Super Usuario Docker](/Docker/Descarga-Imagen-Contenedor-Docker.png)

Una vez tengamos la imagen descargada, es hora de cresr el contenedor en base a la imagen anteriormente descargada. Para ello, debemos ejecutar una de las siguientes lineas de comandos:
```
docker run -d -p 8000:3000 --name juice-shop bkimminich/juice-shop 

docker run -d -p 8000:3000 bkimminich/juice-shop //Esto nos creara el contenedor en nuestra maquina virtual.

NOTA: La diferencia entre ellas es "--name", que nos permite darle un nombre al contenedor.
```
Esto nos creara y arrancara el contenedor en nuestra maquina virtual.
```
docker start juice-shop //Esto arrancara el contenedor en nuestra maquina virtual.
```
Finalmente, para ver el sitio web que tenemos en nuestra maquina virtual, debemos de acceder a la siguiente direccion:
[http://localhost:8000/](http://localhost:8000/)</br>

![Creacion Contenedor Docker](/Docker/Creacion-Contenedor-Docker.png)

### Comenzar o Detener el funcionamiento de un contenedor

Después de tener creado el contenedor, podemos arrancarlo utilizando el sisguiente comando:
```
docker start {NAME or CONTAINER ID} //CONTAINER ID, se encuentra en la tabla y es otra forma de iniciar o finalizar el contenedor en caso de no habrle puesto un nombre. 
```

Para finalizar el contenedor, debemos de ejecutar el siguiente comando:
```
docker stop {NAME or CONTAINER ID} 
```
![Detener Contenedor](/Docker/Detener-Contenedor-Docker.png)
___
