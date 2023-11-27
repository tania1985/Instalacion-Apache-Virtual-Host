# Instalacion-Apache-Virtual-Host
## Antes de empezar

Lo primero es ir a git y crear un nuevo repositorio. Después de esto, creamos nuestro nuevo proyecto en el Code. Una vez listo esto, creamos también un nuevo proyecto en Git y lo asociamos al repositorio creado anteriormente.
Apache

Ahora ponemos lo siguiente para crear el contenedor de apache.

$ docker run -d -p 80:80 --name asir_my-apache -v "$PWD"
:/var/www/html php:7.2-apache

Y creamos un docker-compose.yml con lo siguiente:
```
version: '3.9'
services:
 asir_apache-php: 
   container_name: asir_apache
   image: php:7.4-apache
   ports:
     - '80:80'
   volumes: 
     - ./html:/var/www/html
     - ./confApache:/etc/apache2
```
Mapeamos el puerto 80 al 80 porque vamos a usar un navegador web y la configuración de apache en un nuevo volumen.
Configuración DNS

Lo que haremos en este apartado es configurar un servidor DNS que nos resuelva dos dominios:

    - www.fabulasoscuras.com

    - www.fabulasmaravillosas.com

Como en una práctica anterior hemos configurado un servidor DNS, voy a usarlo y copiar la configuración para posteriormente adaptarla a nuestros servicios.