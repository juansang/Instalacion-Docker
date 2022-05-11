# Instalación de Docker en Linux

Para tener docker instalado y funcionando en nuestro equipo linux, hay que seguir los siguientes pasos :

Primero de todo, se actualizan los repostiorios por si no están cargados con ``sudo apt-get update`` . Ahora hay que instalar una serie de paquetes para permitir que apt se conecte al repositorio a través de HTTPS. 

![Captura desde 2022-05-11 22-20-06](https://user-images.githubusercontent.com/91699247/167946200-04f305f1-1379-4575-bb2a-54ffefa82969.png)


Para poder conectarnos, debemos descargar la clave pública de docker.


```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

A continuación se añade el repositorio oficial de docker 

<img width="449" alt="inst1" src="https://user-images.githubusercontent.com/91699247/167951089-e1fb9298-1e34-421b-b213-55cd69d8cf76.PNG">


Hacemos un ``sudo apt-get update`` para actualizar e instalamos los paquetes de docker con el comando de la imagen :


![Captura desde 2022-05-11 22-29-14](https://user-images.githubusercontent.com/91699247/167946222-dc1ddca0-1ef0-42f6-bd0a-8525f2aff961.png)
![Captura desde 2022-05-11 22-30-56](https://user-images.githubusercontent.com/91699247/167946224-43401c87-d257-4216-b10e-ea1bbd20fff0.png)




Una vez instalado docker, debemos agregar un usuario al grupo de docker, para ello se usa el comando ``sudo gpasswd -a $USER docker``. 

Para acabar con este paso, se ejecuta ``newgrp docker``

<img width="308" alt="inst2" src="https://user-images.githubusercontent.com/91699247/167951124-de3851d3-7d17-49a2-9227-4d4537f08041.PNG">


En este momento, podemos comprobar que la instalación se ha hecho de forma correcta mediante la ejecución de una serie de contenedores.

``docker run hello-world``

<img width="450" alt="inst3" src="https://user-images.githubusercontent.com/91699247/167951147-f047ad54-db70-40ff-8c5a-ec6003f63fea.PNG">



``docker run docker/whalesay cowsay Saludos desde el fondo marino``


<img width="453" alt="inst4" src="https://user-images.githubusercontent.com/91699247/167951170-e9fa4f79-84b3-43b3-9d60-366ed21f9488.PNG">
<img width="311" alt="inst5" src="https://user-images.githubusercontent.com/91699247/167951168-3e1c1d19-3420-4146-9ee7-958ef7da83f5.PNG">



``docker run ociotec/tetris``

<img width="449" alt="inst6" src="https://user-images.githubusercontent.com/91699247/167951186-9412613f-1a81-49f1-b5e7-896d249ba730.PNG">
