# Proyecto Docker 01

Este proyecto trata las funciones básicas de Docker, desde su instalación, hasta el uso de contenedores e imágenes, para ello seguiremos los siquientes pasos:

    1. Instalación
       1.1 Instalación de Docker
       1.2 Descarga de la imagen "Alpine"
       
    2. Administración de datos
       2.1 Crear un contenedor sin nombre
       2.2 Obtener el nombre por defecto que le da Docker al nuevo contenedor
       2.3 Comprobar que el contenedor esté arrancado y sea funcional
    
    3. Conexión con contenedores
       3.1 Crear un contenedor con nombre
       3.2 Crear una conexion entre el contenedor y Google utilizando el comando "Ping"
       3.3 Crear un segundo contenedor con nombre 
       3.4 Conectar ambos contenedores con el comando "Ping"
    
    4. Parámetros del contenedor
       4.1 Comprobar que sucede con el contenedor cuando se cierra la terminal
       4.2 Comprobar cuanto espacio ocupa el contenedor en el disco duro
       4.3 Comprobar cuanta RAM requiere el contenedor

# 1. Instalación

> [!NOTE]
> En este apartado vamos a tratar la instalación de docker y la descarga de la imagen alpine

## 1.1 Instalación de Docker

Para instalar Docker vamos a utilizar los siguientes comandos:

  **sudo apt update**
  
  > [!IMPORTANT]
  > Este comando se encarga de actualizar la lista de paquetes listos para instalar

  **sudo apt-get update**

  > [!IMPORTANT]
  > Este comando se encarga de actualizar la lista de repositorios de donde recoger datos

  **sudo apt install docker.io**

  > [!IMPORTANT]
  > Este comando se encarga de instalar docker de la lista de paquetes

  **sudo systemctl start docker**

  > [!IMPORTANT]
  > Este comando inicia el docker una vez esté instalado

  **sudo systemctl enable docker**

  > [!IMPORTANT]
  > Este comando permite que docker pueda usar sus comandos y crear archivos en el equipo

  **sudo docker version**

  > [!IMPORTANT]
  > Este comando muestra la versión instalada de Docker, permite comprobar la instalación

  Resultado: 

## 1.2 Descarga de la imagen "Alpine"

Para instalar la imagen de alpine utilizamos el siguiente comando:

  **sudo docker pull alpine**

  > [!IMPORTANT]
  > Este comando se encarga de descargar la imagen de alpine de la base de datos de Docker 

  Resultado:

  **sudo docker images**

  > [!IMPORTANT]
  > Este comando se encarga de mostrar las imágenes que contiene Docker

  Resultado:

# 2. Administración de datos

> [!NOTE]
> En este apartado vamos a tratar como administrar los datos, contenedores e imagenes de Docker

## 2.1 Crear un contenedor sin nombre

Para crear un contenedor sin nombre utilizamos los siguientes comandos:

  **sudo docker run -d alpine** 

  > [!IMPORTANT]
  > Este comando se encarga de crear un contenedor sin nombre

  **sudo docker start (Nombre Contenedor)**

  > [!IMPORTANT]
  > Este comando se encarga de iniciar el contenedor

## 2.2 Comprobar el nombre del contenedor

Para ver los datos de los contenedores utilizamos el siguiente comando:

  **sudo docker ps -a**

  > [!IMPORTANT]
  > Este comando se encarga de mostrar todos los contenedores

  Resultado:

## 2.3 Comprobar estado del contenedor

  Para ver el estado de los contenedores utilizamos el siguiente comando:

  **sudo docker ps -a**

  > [!IMPORTANT]
  > Este comando se encarga de mostrar el estado de todos los contenedores

  Resultado:

# 3. Conexión con contenedores

> [!NOTE]
> En este apartado veremos como conectar contenedores con internet y entre sí

## 3.1 Crear un contenedor con nombre

Para crear un contenedor con nombre utilizamos el siguiente comando:

  **sudo docker run -d --name dam_alp1 alpine**

  >[!IMPORTANT]
  > Este comando se encarga de crear un contenedor con el nombre indicado

## 3.2 Conectar el contenedor con google.com

Para conectar un contenedor con google utilizamos los siguientes comandos:

  **sudo docker exec -it dam_alp1 /bin/sh**

  > [!IMPORTANT]
  > Este comando se encarga de iniciar una linea de comandos para que interactue con el contenedor

  **sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' dam_alp1**

  > [!IMPORTANT]
  > Este comando se encarga de comprobar que se pueda iniciar una conexion y nos da la IP del contenedor

  **ping google.com**

  > [!IMPORTANT]
  > Este comando se encarga de intercambiar datos entre el contenedor y google

  > [!CAUTION]
  > **ESTE COMANDO DEBE INTRODUCIRSE EN LA CONSOLA DEL CONTENEDOR**

  Resultado:

## 3.3 Crear un segundo contenedor con nombre

Al igual que en apartados anteriores el comando es:

  **sudo docker run -d --name dam_alp2 alpine**

  >[!IMPORTANT]
  > Este comando se encarga de crear un contenedor con el nombre indicado

## 3.4 Conectar ambos contenedores

Para conectar ambos contenedores creados anteriormente usamos los siguientes comandos:

  **sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' dam_alp2**

  > [!IMPORTANT]
  > Este comando se encarga de comprobar que se pueda iniciar una conexion y nos da la IP del contenedor

  **ping [IP del segundo contenedor]**

  > [!IMPORTANT]
  > Este comando se encarga de intercambiar datos entre ambos contenedores

  > [!CAUTION]
  > **ESTE COMANDO DEBE INTRODUCIRSE EN LA CONSOLA DEL CONTENEDOR**

  Resultado:

# 4. Parámetros del contenedor

> [!NOTE]
> En este apartado trataremos los diferentes parámetros y datos del contenedor


## 4.1 Salir de la terminal y comprobar el contenedor

Para salir de la terminal y comprobar el estado del contenedor usamos los siguientes comandos

  **Exit**

  > [!IMPORTANT]
  > Este comando se encarga de salir de la terminal que hemos creado en el contenedor

  > [!CAUTION]
  > **ESTE COMANDO DEBE INTRODUCIRSE EN LA CONSOLA DEL CONTENEDOR**

  **sudo docker ps -a** 

  > [!IMPORTANT]
  > Este comando se encarga de mostrar los datos de todos los contenedores

  Resultado:

## 4.2 Comprobar espacio ocupado en el disco duro

Para comprobar el espacio utilizado en el disco duro utilizamos el siguiente comando:

  **sudo docker system df**

  > [!IMPORTANT]
  > Este comando se encarga de mostrar la cantidad de memoria utilizada por docker

  Resultado:

## 4.3 Comprobar memoria RAM utilizada

Para comprobrar cuanta memoria RAM necesita el contenedor utilizamos el siguiente comando:

  **sudo docker stats**

  > [!IMPORTANT]
  > Este comando se encarga de mostrar la cantidad de RAM que utiliza el contenedor

  Resultado:

  
  
  


  
