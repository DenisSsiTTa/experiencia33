
Alumno: Denisse Velásquez Salazar
mail: denisse.velasquez@gmail.com


DenisSsiTTa=# CREATE DATABASE experiencia33;
CREATE DATABASE
DenisSsiTTa=# \c experiencia33
psql (10.1, server 10.3)
You are now connected to database "experiencia33" as user "DenisSsiTTa".

experiencia33=# Select 'Tablas Ejercicio 1' as ejercicio;
     ejercicio      
--------------------
 Tablas Ejercicio 1
(1 row)

experiencia33=# CREATE TABLE departamento ( id_depto SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE trabajador ( id_trabajador SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL, id_depto INTEGER REFERENCES departamento(id_depto));
CREATE TABLE
experiencia33=# CREATE TABLE liquidaciones ( id_liquidacion SERIAL PRIMARY KEY, monto integer, id_trabajador INTEGER REFERENCES trabajador(id_trabajador));
CREATE TABLE


experiencia33=# Select 'Tablas Ejercicio 2' as ejercicio;
     ejercicio      
--------------------
 Tablas Ejercicio 2
(1 row)

experiencia33=# CREATE TABLE alumno ( id_alumno SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE curso ( id_curso SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE profesor ( id_profesor SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE prueba ( id_prueba SERIAL PRIMARY KEY, link varchar(250) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE alumno_curso ( id_curso INTEGER REFERENCES curso(id_curso),id_alumno INTEGER REFERENCES alumno(id_alumno), PRIMARY KEY (id_curso, id_alumno));
CREATE TABLE
experiencia33=# CREATE TABLE nota_prueba ( id_prueba INTEGER REFERENCES prueba(id_prueba),id_alumno INTEGER REFERENCES alumno(id_alumno), id_profesor INTEGER REFERENCES profesor(id_profesor), nota INTEGER, PRIMARY KEY (id_prueba, id_alumno, id_profesor));
CREATE TABLE


experiencia33=# Select 'Tablas Ejercicio 3' as ejercicio;
     ejercicio      
--------------------
 Tablas Ejercicio 3
(1 row)

experiencia33=# CREATE TABLE partido ( id_partido SERIAL PRIMARY KEY, nombre varchar(250) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE mesa ( id_mesa SERIAL PRIMARY KEY, ubicacion varchar(250) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE candidato ( id_candidato SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL, id_partido INTEGER REFERENCES partido(id_partido));
CREATE TABLE
experiencia33=# CREATE TABLE voto ( id_voto SERIAL PRIMARY KEY, id_candidato INTEGER REFERENCES candidato(id_candidato), id_mesa INTEGER REFERENCES mesa(id_mesa));
CREATE TABLE


experiencia33=# Select 'Tablas Ejercicio 4' as ejercicio;
     ejercicio      
--------------------
 Tablas Ejercicio 4
(1 row)

experiencia33=# CREATE TABLE categoria ( id_categoria SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE tags ( id_tag SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE pelicula ( id_pelicula SERIAL PRIMARY KEY, nombre varchar(250) NOT NULL, id_categoria INTEGER REFERENCES categoria(id_categoria));
CREATE TABLE
experiencia33=# CREATE TABLE tag_peli ( id_pelicula INTEGER REFERENCES pelicula(id_pelicula),id_tag INTEGER REFERENCES tags(id_tag), PRIMARY KEY (id_pelicula, id_tag));
CREATE TABLE


experiencia33=# Select 'Tablas Ejercicio 5' as ejercicio;
     ejercicio      
--------------------
 Tablas Ejercicio 5
(1 row)

experiencia33=# CREATE TABLE cliente ( id_cliente SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL, direccion varchar(250) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE producto ( id_producto SERIAL PRIMARY KEY, nombre varchar(50) NOT NULL, tipo varchar(50) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE bodega ( id_bodega SERIAL PRIMARY KEY, ubicacion varchar(250) NOT NULL);
CREATE TABLE
experiencia33=# CREATE TABLE factura ( id_factura SERIAL PRIMARY KEY, id_cliente INTEGER REFERENCES cliente(id_cliente));
CREATE TABLE
experiencia33=# CREATE TABLE detallefac ( id_factura INTEGER REFERENCES factura(id_factura), id_producto INTEGER REFERENCES producto(id_producto), id_bodega INTEGER REFERENCES bodega(id_bodega), cantidad INTEGER, PRIMARY KEY (id_factura, id_producto, id_bodega));
CREATE TABLE


experiencia33=# \dt
              List of relations
 Schema |     Name      | Type  |    Owner    
--------+---------------+-------+-------------
 public | alumno        | table | DenisSsiTTa
 public | alumno_curso  | table | DenisSsiTTa
 public | bodega        | table | DenisSsiTTa
 public | candidato     | table | DenisSsiTTa
 public | categoria     | table | DenisSsiTTa
 public | cliente       | table | DenisSsiTTa
 public | curso         | table | DenisSsiTTa
 public | departamento  | table | DenisSsiTTa
 public | detallefac    | table | DenisSsiTTa
 public | factura       | table | DenisSsiTTa
 public | liquidaciones | table | DenisSsiTTa
 public | mesa          | table | DenisSsiTTa
 public | nota_prueba   | table | DenisSsiTTa
 public | partido       | table | DenisSsiTTa
 public | pelicula      | table | DenisSsiTTa
 public | producto      | table | DenisSsiTTa
 public | profesor      | table | DenisSsiTTa
 public | prueba        | table | DenisSsiTTa
 public | tag_peli      | table | DenisSsiTTa
 public | tags          | table | DenisSsiTTa
 public | trabajador    | table | DenisSsiTTa
 public | voto          | table | DenisSsiTTa
(22 rows)


