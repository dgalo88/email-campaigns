# Prueba Técnica - Programador (Back-end)
La siguiente es una prueba para evaluar a los postulantes a programador **Back-end**.

## INTRODUCCIÓN
Este repositorio contiene una serie de requerimientos de un Caso Práctico, que busca evaluar las capacidades técnicas del candidato con respecto a las principales funciones y responsabilidades que se requieren dentro del Área de Investigación y Desarrollo de XXXXX.

#### Qué se busca evaluar?
Principalmente los siguientes aspectos:

* Creatividad para resolver los requerimientos,
* Calidad del código entregado (estructura y buenas prácticas),
* Eficiencia de los algoritmos entregados,
* Familiaridad con Spring Framework y plataformas de desarrollo.

## IMPORTANTE
1. Recomendamos emplear un máximo de **3 días calendario** y enviar todo lo que puedas.
2. Se requiere de una **cuenta de Github** para realizar este ejercicio.
3. **Antes de comenzar a programar:**
    * Realizar un `Fork` de este repositorio (https://github.com/dgalo88/email-campaigns).
    * Clonar el fork a su máquina local  `git clone git@github.com:<USERNAME>/<FORKED_PROJECT>.git`
    * Crear un `branch` en su cuenta de Github utilizando su nombre completo.
4. **Al finalizar**, para entregar su proyecto:
    * Realizar un `Commit` de su proyecto, **enviar un `Pull Request` al branch con su NOMBRE**, y notificar a las siguientes direcciones de correo electrónico  [yyy@xxxxx.com](mailto:yyy@xxxxx.com) y [zzz@xxxxx.com](mailto:zzz@xxxxx.com).
    

## EJERCICIOS

### Ejercicio #
La compañía ABC necesita una página llamada "Mis correos" que muestre las campañas de correo enviadas y los correos totales que un usuario ha enviado. Cada campaña se compone de un número de destinatarios, y los correos totales enviados corresponden a la suma del número de destinatarios de todas las campañas. Para esto se requiere la creación de varios servicios.

Para referencia de la base de datos, ver Figura 1.


##### Casos de uso

A continuación se describen los casos de uso. No se entra en detalles de la interacción entre el cliente y la aplicación, puesto que no va a ser tarea de este ejercicio desarrollar esa parte.

###### **Caso de uso "Registrar Usuario"**
1. Ingrese todos los datos requeridos (idUser debe ser único - se sugiere el uso de UUID)
2. Debe retornar mensaje de error si el usuario ya está registrado
3. Encriptación de contraseña a su preferencia.

###### **Caso de uso "Inicio de sesión"**
1. Ingresa email y contraseña
2. Debe retornar mensaje de error si el usuario no existe o si tiene un error en usuario/contraseña

###### **Caso de uso "Historial de Campaña"**
1. Devuelve historial de todas las campañas enviadas, ordenado por fecha (desc.) junto con toda su data - recibe un idUser
 

###### **Caso de uso "Total de Correos enviados"**
1. Devuelve la suma de correos enviados totales en campañas activas (status = 1) - recibe un idUser

###### **Caso de uso "Crear Campaña"**
1. Inserta data campaña en base de datos

###### **Caso de uso "Activar/Desactivar Campaña"**
1. Actualiza registro campaña con status = 1 (activada) o status = 0 (desactivada)

##### Persistencia de datos
La información de cada uno de los casos de uso será almacenada en una base de datos en memoria (H2). Debido a que el manejador de base de datos puede ser modificado en cualquier momento, se utilizará spring-data-jpa para la creación de la estructura de datos e inicialización de la misma.

##### Figura 1. Estructura de Datos
![ Figura 1. Estructura de Datos](https://bitbucket.org/ladonware/backend-test/raw/8a33024e293d441344790e84af9abb5aad3f7f9e/esquema-bd.png)

##### Puntos que se deben desarrollar
* Desarrollar los 6 servicios descritos anteriormente en SpringBoot.
* Dentro del proyecto se debe incluir el archivo schema.sql con la estructura de datos de la Figura 1, para que al momento de iniciarlizar la aplicación sea creada la dase de datos.
* Dentro del proyecto se debe incluir el archivo data.sql con datos de inicialización para la base de datos.
* Utilizar archivo application.yml para la configuración.
* Formato de fecha debe ser YYYY-MM-DD HH:MM:SS
* Los servicios deben ser independientes entre sí
* Aplicación para gestionar las Campañas. Deberá incluir:
    * Código de las clases que permitan gestionar los datos asociados.
    * Mapeo de las clases para poder almacenar la información en la base de datos.
    * Clases para gestionar la persistencia de datos, incluida la configuración de conexión a la base de datos.

#####  Valoraciones extras
* Se utilicen sistemas de autenticación para mejorar la seguridad (ej., OAUTH2  o JWT)
* Diagrama de clases y diagrama de secuencia  de las partes encargadas de la aplicación.
  
##### Consideraciones.
*** Utilizar Java 8.
