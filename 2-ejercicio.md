### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
# COMPLETAR
```
docker run -d --name postgres-db \
  -e POSTGRES_PASSWORD=admin123 \
  postgres:15-alpine3.21
```

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4
```
docker run -d --name pgadmin \
  --network postgres-net \
  -e PGADMIN_DEFAULT_EMAIL=admin@example.com \
  -e PGADMIN_DEFAULT_PASSWORD=admin123 \
  -p 5050:80 \
  dpage/pgadmin4
```

# COMPLETAR

La figura presenta el esquema creado en donde los puertos son:
- a: (5050)
- b: (80)
- c: (5432)

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
<img width="937" height="719" alt="image" src="https://github.com/user-attachments/assets/7bf250d2-8509-48df-bede-074b191275f9" />
<img width="822" height="483" alt="image" src="https://github.com/user-attachments/assets/9fa9af96-4da6-4f7e-ae1c-7d47a38d572e" />


### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
<img width="665" height="404" alt="image" src="https://github.com/user-attachments/assets/c74c4874-b84a-4965-94f5-73fb3cdc33c1" />

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
```
docker exec -it postgres-db psql -U postgres
```
```
\c info
SELECT * FROM personas;
```

### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
<img width="655" height="213" alt="image" src="https://github.com/user-attachments/assets/32a917ed-9e47-42a6-888f-0963215816be" />

