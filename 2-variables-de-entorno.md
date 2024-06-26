# Variables de Entorno
### ¿Qué son las variables de entorno
# COMPLETAR
Las variables de entorno son valores dinámicos que pueden afectar el comportamiento de los procesos en un sistema operativo. Son una forma de pasar información al software y configuraciones que se ejecutan en el sistema, sin necesidad de modificar el código de los programas.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.
docker run -d --name mi-nginx -e username=user -e role=admin nginx:alpine
# COMPLETAR
Las variables de entorno son valores dinámicos que pueden afectar el comportamiento de los procesos en un sistema operativo. Son una forma de pasar información al software y configuraciones que se ejecutan en el sistema, sin necesidad de modificar el código de los programas.

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
![Imagen](imagenes/variables.png)

### Crear un contenedor con mysql:8 , mapear todos los puertos
```
docker run --name mi_mysql  -p 3306:3306 -d mysql:8
```

### ¿El contenedor se está ejecutando?
No , el contenedor no se ejecuta 

### Identificar el problema

El error se produce al intentar iniciar un contenedor de MySQL sin especificar las variables de entorno necesarias para la configuración de la contraseña del usuario root


### Eliminar el contenedor creado con mysql:8 
# COMPLETAR
```
docker rm mi_mysql
```
### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

Previo a esto es necesario crear el archivo y colocar las variables en un archivo, **.env** se ha convertido en una convención estándar, pero también es posible usar cualquier extensión como **.txt**.
```
docker run -d --name <nombre contenedor> --env-file=<nombreArchivo>.<extensión> <nombre imagen>
```
**Considerar**
Es necesario especificar la ruta absoluta del archivo si este se encuentra en una ubicación diferente a la que estás ejecutando el comando docker run.

### Crear un contenedor con mysql:8 , mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR

```
docker run -d --name mi_mysql --env-file=env.txt -p 3306:3306 mysql:8
```

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
![Imagen](imagenes/env.png)

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR

Existen las siguientes 4 bases de datos:

- information_schema: Proporciona metadatos sobre las bases de datos MySQL y sus objetos.
- mysql: Gestiona los usuarios, privilegios y configuraciones del servidor MySQL.
- performance_schema: Almacena estadísticas de rendimiento sobre el servidor MySQL.
- sys: Proporciona vistas y funciones para la gestión y diagnóstico del rendimiento de MySQL.


