# Docker-Compose-Jenkins
_El siguiente repositorio contiene un entorno de Jenkins haciendo uso de Docker Compose._

## Descripción 

### Jenkins
_Jenkins es un servidor de automatización de código abierto, autónomo, que se puede utilizar para automatizar todo tipo de tareas relacionadas con la creación, prueba y entrega o implementación de software._

### Docker-Compose
_Compose es una herramienta para definir y ejecutar aplicaciones Docker de múltiples contenedores. Docker-Compose, utiliza un archivo YAML para configurar los servicios de su aplicación. Luego, con un solo comando, puede crear e iniciar todos los servicios desde su configuración._

## Requisitos
_El servidor Jenkins tendrá que crear imágenes docker, que requieren acceso a los servicios de Docker. Puede obtener acceso a esto montando el socket Unix desde el host del sistema operativo._

## Porcedimiento
_Primero hemos de crear una configuración de Docker-Compose, la cual llamaremos docker-compose.yml como se muestra a continuación._
```
version: "2"
services:
  jenkins:
    image: jenkinsci/blueocean
    user: root
    ports:
      - "8080:8080"
      - "8443:8443"
      - "50000:50000"
    volumes:
      - ./jenkins_data:/var/jenkins_home
      - ./home:/home
      - /var/run/docker.sock:/var/run/docker.sock
      
```
_La forma más fácil de ejecutar este contenedor es en modo privilegiado, ya que tendrá todos los permisos y el acceso necesarios para construir contenedores de ventana acoplable._

_Para montar la aplicacion simplemente ejecutamos:_
```docker-compose up```
_Una vez que el servicio esté listo, puede acceder a él desde el navegador con localhost:8080._

_Insertar una imagena aca_

## Autores

* **Cristian Camilo Cuervo Castillo** - *20142020025*

* **Edvard Frederick Bareño Castellanos** - *20142020014*

* **Neider Alejandro Fajardo Cardona** - *20142020025*

Hola :) Por fa cambien esto con lo que debe ir acá, el profe dijo que esto tiene que estar bien documentado, supongo que quiere que digamos que herramientas estamos dockerizando y esas cosas, acá está de donde lo saqué: 

https://medium.com/@Joachim8675309/jenkins-environment-using-docker-6a12603ebf9

Me avisan cualquier cosa
