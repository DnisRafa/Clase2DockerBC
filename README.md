# Clase2DockerBC

## RESUMEN DE CLASE.


### El objetivo principal de la clase de hoy, era hacer un reto el cual pudiesemos dockerizar todos los servicios con los que habíamos estado trabajando anteriormente.

0- Primero hicimos un taller en el que tuvimos que hacer un duplicado de nuestro priceservice, haciendo uso de este para hacer la conexión con mysql.
  Entramos al directorio binaries creamos un nuevo directorio ya sea usando el mkdir o desde la interfaz de Moba y copiamos el contenido de la carpeta priceservice en
  su interior. A continuación entramos al directorio source y hacemos los mismos pasos, creamos una carpeta nueva y copiamos el contenido de priceservice.
  Una vez copiado todo nos quedarian estas dos carpetas.
  
  
  Directorio priceservicemysql en binaries:
  
  
  -priceservicemysql


    -Dockerfile
    -priceservice-0.0.1-SNAPSHOT.jar
    
    
 Directorio priceservicemysql en source:
 
 
 -priceservicemysql
 
 
    -directorio target
    -directorio src
    -directorio .mvc
    -pom.xml
    -mvnw.cmd
    -mvnw
    -HELP.md
    -.gitgnore


1- Añadir las siguientes dependencias en el pom.xml de nuestra carpeta priceservicemysql en source.
 
 
  <dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <scope>runtime</scope>
  </dependency>
  
  Estas dependencias hacen que tu servicio puedan conseguir una conexión con mysql.
  
  
 2- Entrar en el aplication.yml y cambiar las propiedades para funcionamiento correcto.
 
 ### A partir de ahora los pasos a realizar son para el reto final.
 
 3- Vamos a la carpeta binaries y creamos un **docker-compose.yml**
 
 4- En el docker-compose.yml vamos a añadir los volumenes y los servicios pero primero se realizaran otros pasos.
 
 5- Crear una imagen de todos los servicios que tenemos mediante el build.
 
 priceservicemysql:
 > docker build -t priceservicemysql:1.0 .

priceservicemysql:
 > docker build -t priceservicemysql:1.0 .

priceservicemysql:
 > docker build -t priceservicemysql:1.0 .

priceservicemysql:
 > docker build -t priceservicemysql:1.0 .

priceservicemysql:
 > docker build -t priceservicemysql:1.0 .



