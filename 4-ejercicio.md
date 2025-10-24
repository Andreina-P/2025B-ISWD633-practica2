## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
```
docker network create net-wp -d bridge
```

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name mysql-wp --network net-wp \
  -e MYSQL_ROOT_PASSWORD=admin123 \
  -e MYSQL_DATABASE=wordpress \
  -e MYSQL_USER=wpuser \
  -e MYSQL_PASSWORD=wpsecret \
  mysql:8
```

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name wordpress --network net-wp \
  -p 9300:80 \
  -e WORDPRESS_DB_HOST=mysql-wp:3306 \
  -e WORDPRESS_DB_USER=wpuser \
  -e WORDPRESS_DB_PASSWORD=wpsecret \
  -e WORDPRESS_DB_NAME=wordpress \
  wordpress
```

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **9300**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="874" height="391" alt="image" src="https://github.com/user-attachments/assets/d72defbe-4031-49dc-beb9-dbd22f861f6b" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="936" height="908" alt="image" src="https://github.com/user-attachments/assets/0ecf5e64-49f3-43b7-be33-f32293d91fce" />

### Eliminar el contenedor wordpress
# COMPLETAR
```
docker rm -f wordpress
```

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR
Al ingresar a esa URL nuevamente, el sitio WordPress sigue configurado y funcionando, con el mismo tema, usuario y publicaciones creadas anteriormente.
Esto es porque solo elimine el contenedor de wordpress, es por esto que la info del sitio que se guardó en el contenedor MySQL se muestra. Es decor, wordpress se volvió a conectar a la misma base de datos (wordpress) donde ya estaban los datos guardados.
