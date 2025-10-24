# Variables de Entorno
### ¿Qué son las variables de entorno?
# COMPLETAR
Las variables de entorno son valores que almacenan información de configuración del sistema o de una aplicación, permitiendo modificar su comportamiento sin cambiar el código.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR
```
docker run -d --name nginx-env \
  -e USERNAME=andreina \
  -e ROLE=admin \
  nginx:alpine
```

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
<img width="548" height="120" alt="image" src="https://github.com/user-attachments/assets/c7a803f7-974b-4e1d-8664-e390a3fc0653" />


### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR
```
docker run -d --name mysql-db -P mysql:8
```

### ¿El contenedor se está ejecutando?
# COMPLETAR
No, aparece con Exited

### Identificar el problema
# COMPLETAR
MySQL no puede iniciar porque no se le indicó una contraseña para el usuario root.

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
```
docker exec -it mysql-db mysql -uroot -p
  SHOW DATABASES;
```
<img width="998" height="589" alt="image" src="https://github.com/user-attachments/assets/2d426543-c62c-4a2c-baab-d28016bc1634" />


