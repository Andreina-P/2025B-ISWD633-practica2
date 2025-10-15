# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Respecto a esta practica me parece que he aprendido lo suficiente, desde redes hasta variables de entorno debido a que son temas nuevos.
Además, lo que me acuerdo es acerca de la creacion de contenedores, como se conectan a las redes, en dónde debo crear las variables de entrono o çomo debo revisarlas.


Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).
Como se mencionó en clase los secretos de docker contienen información sensible.
Docker los almacena de forma cifrada y sólo los servicios autorizados pueden acceder a ellos.
A diferencia de las variables de entorno, los secretos no quedan expuestos en el entorno del contenedor ni en los logs.

Entonces la manera de gestionarlos de manera segura luego de haberlos creado, sería:
Entonces sería:
```
docker swarm init
```

Crear un secreto

El siguiente comando crea un secreto llamado db_password con el valor MiContraseñaSegura:

```
echo "MiContraseñaSegura" | docker secret create db_password -

```
El - indica que el valor se toma desde la entrada estándar (stdin).

Ver los secretos disponibles

```
docker secret ls
```

