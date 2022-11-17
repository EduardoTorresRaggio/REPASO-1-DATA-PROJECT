# REPASO-1-DATA-PROJECT

Un contenedor debe cumplir un objetivo y morir

**¿Cual es la diferencia entre una maquina virtual y docker?**

- La maquina virtual consume mucho, en cmabio docker puedes tener muchos contenedores y no se nota

**¿Cuales son los COMANDOS de los CONTENEDORES docker?**
- Levantar contenedor : docker run
- Nombre contenedor cuando levantas : docker run ubuntu echo (nombre)
- Listado de los contenedores vivos : docker ps
- Lista contenedores vivos y muertos : docker ps -a
- Ver la version de docker: docker --version
- Muestra todos los posibles comandos existentes: docker --info
- Cambiar el nombre : docker rename (nombre actual) (nombre nuevo)
- Entrar dentro de un contenedor : docker run -it ubuntu 
- Levantar un contenedor y que no muera : docker run -dt (S.O)
- Entrar en un contenedor ya ejecutado y ver lo que hay sin levantar la terminal: docker exec (nombre_contenedor) ls
- Mover un archivo : docker cp (archivo) (nombre_contenedor+ubicacion) 

**Extraer informacion en formato JSON  y guardar en carpeta**
*previamente has de moverte a la carpeta en la que quieres guardarlo*
- docker info --format '{{json .}} > docker-config.jsonn

# IMAGENES
**Siempre que vayamos a contruir una imagen, que sea verificada**
***
## METODO 1: DESCARGAR UNA IMAGEN OFICIAL Y CREAR CONTENDEDORES A PARTIR DE ELLA
***

**Comandos importantes**
- Docker image ls: listado de las imagenes
- Docker pull (image) : descargar la imagen

**"Visualizacion" de un contenedor en internet a partir de una imagen**
- docker run --name my-web -p 8080:80 -d nginx
    - docker run : crear un contenedor
    - --name : decir a docker que vamos a dar un nombre
    - my-web : nombre del contenedor que queremos poner
    - -publisher
    - 8080 : puerto externo al que hay que conectarse
    - 80 : puerto de mi ordenador
    - -d : para que no se congele la terminal
    - nginx : imagen del cual se crea el contenedor

Para poder ver que funciona, (recordemos que Nginx, es como Apache que solo sirve para saber que se está ejecutando el comando correctamente y que el contenedor se ha levantado), buscamos en google "localhost:8080". Previamente se ha de ver accionado.

*¿Como sabemos que tenemos que emparejarnos con el 8080?*

Nos vamos a la documentacion de Nginx y en la parte Exposing external port sale que hayq ue hacerlo así

***
*Muy importante que a la hora de crear un contenedor no tengan el mismo nombre y si lo conectamos "fuera" no coincidan con el mismo puerto*
***

