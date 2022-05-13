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
 
 3- Compilar el proyecto con el siguiente comando.
 
    docker run -it --rm --network host --name priceservice-maven -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.8.1-openjdk-11 mvn clean install -Dmaven.test.skip=true
 
 ### A partir de ahora los pasos a realizar son para el reto final tambien.
 
 4- Vamos a la carpeta binaries y creamos un **docker-compose.yml**
 
 5- En el docker-compose.yml vamos a añadir los volumenes y los servicios pero primero se realizaran otros pasos.
 
 6- Crear una imagen de todos los servicios que tenemos mediante el build ubicados en sus respectivos directorios.
 
 priceservicemysql: 
 
 
    devops@devops-bootcamp-everis:~/Road2Cloud/00.Microservices/binaries/priceservicemysql$  docker build -t priceservicemysql:1.0 .

 adminservice:
 
 
     devops@devops-bootcamp-everis:~/Road2Cloud/00.Microservices/binaries/adminservice$ docker build -t adminservice:1.0 .

 eurekaservice:
 
 
    devops@devops-bootcamp-everis:~/Road2Cloud/00.Microservices/binaries/eurekaservice$ docker build -t eurekaservice:1.0 .

 zuulservice:
 
 
    devops@devops-bootcamp-everis:~/Road2Cloud/00.Microservices/binaries/zuulservice$ docker build -t zuulservice:1.0 .

 productservice:
 
 
    devops@devops-bootcamp-everis:~/Road2Cloud/00.Microservices/binaries/productservice$ docker build -t productservice:1.0 .
    
    
 7- Una vez creadas todas las imagenes, queremos que nuestro docker-compose.yml haga su función y nos despliegue los contenedores de todas nuestras imágenes sin necesidad
 de utilizar el comando run como veníamos haciendo hasta ahora, esto significa dockerizar.
 Para ello entramos al docker-compose.yml y vamos a añadir todos nuestros servicios, diciendo de que otros servicios dependen, la imagen, la cual tendría el nombre y tag     que nosotros hemos escrito al hacer el build de cada una de ellas. En el puerto colocaremos el puerto del host y el puerto al que queremos que nos haga el mapping y en el     environment pondríamos las variables de entorno que queremos que añada.

8- Ya completo nuestro docker-compose.yml


