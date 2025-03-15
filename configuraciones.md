# Entregable Docker #
## Introducción ##
Este documento describe la configuración de diferentes docker-compose y su ejecución.
## Drupal + MySQL ##
Se han configurado dos servicios en este docker-compose.
### MySQL ###
- Utiliza la versión 5.7 de la imagen oficial de MySQL
- Se le da el nombre de mysql_container
- Se definen varias variable de entorno para su correcto funcionamiento
- Se define el volumen mysql_data para la persistencia de datos, definido donde se guardan las bases de datos de forma local
- Se define una red para la correcta comunicación entre MySQL y Drupal
### Drupal ###
- Utiliza la última versión de la imagen oficial de Drupal
- Se le da el nombre de drupal_container
- Se definen varias variable de entorno para su correcto funcionamiento
- Se declara en el puerto 81
- Se define el volumen drupal_data para la persistencia de datos, definido donde se guarda el código fuente de forma local
- Se define una red para la correcta comunicación entre MySQL y Drupal
### Ejecución y comprobación ###
Para poder ejecutarlo en la misma ruta en la que esta el docker-compose ejecutamos 
`docker-compose up -d` (ejecuta el compose en segundo plano).  
Para comprobar que funciona nos dirigimos a `localhost:81`. Nos mostrará la página de configuración de drupal.  
Una vez ejecutado podemos detener (y eliminar si queremos los volúmenes) el composer `docker-compose down -v`, el flag de -v es para eliminar los volúmenes.
## Wordpress + Mariadb ##
Se han configurado dos servicios en este docker-compose.
### Mariadb ###
- Utiliza la última versión de la imagen oficial de Mariadb
- Se le da el nombre de mariadb_container
- Se definen varias variable de entorno para su correcto funcionamiento
- Se define el volumen mariadb_data para la persistencia de datos, definido donde se guardan las bases de datos de forma local
- Se define una red (redDocker) para la correcta comunicación entre Mariadb y Wordpress
### Wordpress ###
- Utiliza la última versión de la imagen oficial de Wordpress
- Se le da el nombre de wordpress_container
- Se definen varias variable de entorno para su correcto funcionamiento
- Se declara en el puerto 82
- Se define el volumen wordpress_data para la persistencia de datos, definido donde se guarda el código fuente de forma local
- Se define una red (redDocker) para la correcta comunicación entre Mariadb y Wordpress
### Ejecución y comprobación ###
Para poder ejecutarlo en la misma ruta en la que esta el docker-compose ejecutamos 
`docker-compose up -d` (ejecuta el compose en segundo plano).  
Para comprobar que funciona nos dirigimos a `localhost:82`. Nos mostrará la página de configuración de drupal.  
Una vez ejecutado podemos detener (y eliminar si queremos los volúmenes) el composer `docker-compose down -v`, el flag de -v es para eliminar los volúmenes.

