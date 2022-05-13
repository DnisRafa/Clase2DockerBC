# Clase2DockerBC

## RESUMEN DE CLASE:


### El objetivo principal de la clase de hoy, era hacer un reto el cual pudiesemos dockerizar todos los servicios con los que habíamos estado trabajando anteriormente.

0- Primero hicimos un taller en el que tuvimos que hacer un duplicado de nuestro priceservice, haciendo uso de este para hacer la conexión con mysql.
  Entramos al directorio binaries creamos un nuevo directorio ya sea usando el mkdir o desde la interfaz de Moba y copiamos el contenido de la carpeta priceservice en
  su interior. A continuación entramos al directorio source y hacemos los mismos pasos, creamos una carpeta nueva y copiamos el contenido de priceservice.
  Una vez copiado todo nos quedarian estas dos carpetas.
  
  
  Directorio priceservicemysql en binaries:
  
  #!/bin/bash

#File: tree-md

tree=$(tree -tf --noreport -I '*~' --charset ascii $1 |
       sed -e 's/| \+/  /g' -e 's/[|`]-\+/ */g' -e 's:\(* \)\(\(.*/\)\([^/]\+\)\):\1[\4](\2):g')

printf "# Project tree\n\n${tree}"
  
  
  > -priceservicemysql
  > 
      |
      
      
        - Dockerfile
        
        
      |
      
      
        -priceservice-0.0.1-SNAPSHOT.jar
