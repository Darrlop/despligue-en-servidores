# Configuración de Servidores y Despliegue de Aplicaciones

    > David Arrarás López
	> Web Full Stack 16
	> Redactado con VIM

## Introducción

El objetivo de este proyecto es la configuración de un servidor y el despliegue de una serie de aplicaciones en el mismo.

La plataforma de hosting elegida es AWS.

## Acceso a las aplicaciones desplegadas

Inicialmente se configuraron las siguientes IPs y DNS elásticas:

- 52.23.28.248
- ec2-52-23-28-248.compute-1.amazonaws.com

Después se incluyó el uso de https y dns con subdominios, quedando el acceso a las aplicaciones así:

- Web estática -> https://darrlop.duckdns.org/
- App Node -> https://node-chollopop.duckdns.org/
- App React -> https://react-chollopop.duckdns.org/

En todos los casos las peticiones son recibidas por el puerto 443 (https) y redirigidas a la app correspondiente por Nginx

## Objetivos

Se indican a continuación los objetivos buscados y su realización

- [X] Uso de Node como servidor de aplicación
- [X] Uso de Supervisor como gestor de procesos
- [X] Utilización de Nginx como proxy inverso
- [X] Archivos estáticos suministados por Nginx
- [X] Uso de dns con subdominios para cada despliegue
- [X] Aplicación de protocolo https para una mayor seguridad
- [X] Instalación e integración de mongoDB con la aplicación Node
- [X] Verificación, mediante Postman, del correcto funcionamiento de peticiones a la api de Chollopop
- [ ] Integración de la api Nodepop-api con la aplicación React
- [ ] Utilización de Docker en la práctica


### Archivos estáticos

La aplicación Node (Chollopop) utilizada es la de Backend Avanzado. La parte accesible desde navegador permite el listado general de anuncios por medio del enlace "Artículos" en la parte superior. En dicho listado no se muestran las fotografías del anuncio, sólo su nombre.

No obstante, es posible verificar con sencillez el requisito de los archivos estáticos suministrados por Nginx en la página de "Inicio", chequeando en la pestaña de red: 

- Logo de la web: 'chollopop-transparente.png'
- Archivo css: 'styles.css'

En ambos casos se puede observar que poseen la cabecera 'X-Owner darrlop'





