# UNIVERSIDAD MULTICULTURAL CUDEC
## Luis Alberto Arroyo Hernandez 
### Generacion 2016-2019


║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║
║║║║║║║║║║║║▄▄║║║║║║║║║║║║║║║║║║║║║║║║║║║║
║║║║║║║║║║║███║║║║║║║║║║║║║║║║▄▄║║║║║║║║║║
║║║║║║║║║║████║║║║║║║║║║║║║║║████║║║║║║║║║
║║║║║║║║║████║║║║║║║║║║║║║║██████▌║║║║║║║║
║║║║║║║║████║║║║║║║║║║║║║║████▀███║║║║║║║║
║║║║║║║████║║║║║║║║║║║║║║████║║▐██▌║║║║║║║
║║║║║║████║║║║║║║║║║║║║█████║║║║███║║║║║║║
║║║║║████║║║║║║║▄▄▄▄║▄█████▄▄▄▄║▐███║║║║║║
║║║║║███████████████║███████████████║║║║║║
║║║║║▀▀▀▀▀▀▀▀▀▀▀▀▀║║║▀▀▀▀║║║║║▀██████║║║║║
║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║████║║║║║
║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║▀███║║║║
║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║║



### Programacion Intermedia


## Ejercicio mySQL - 01

```mysql
CREATE DATABASE bd_empleados;
USE bd_empleados;
```
>CREACION BASE DE DATOS 


```mysql
create table emple(
   emp_no INTEGER PRIMARY KEY,
  apellido VARCHAR(50) NOT NULL,
  oficio VARCHAR(30),
  dir INTEGER, 
  fecha_alt DATE, 
  salario INTEGER,
  comision INTEGER,
  dept_no INTEGER);
```
>CREACION DE LA TABLA [emple]

```mysql
INSERT INTO emple VALUES (7369,'SÁNCHEZ', 'EMPLEADO', 7902, '1990/12/17', 1040, NULL, 20);
INSERT INTO emple VALUES (7499,'ARROYO', 'VENDEDOR', 7698, '1990/02/20', 1500, 390, 30);
INSERT INTO emple VALUES (7521,'SALA', 'VENDEDOR', 7698, '1991/02/22', 1625, 650, 30);
INSERT INTO emple VALUES (7566,'JIMÉNEZ', 'DIRECTOR', 7839, '1991/04/02', 2900, NULL, 20);
INSERT INTO emple VALUES (7654,'MARTÍN', 'VENDEDOR', 7698, '1991/09/29', 1600, 1020, 30);
INSERT INTO emple VALUES (7698,'NEGRO', 'DIRECTOR', 7839, '1991/05/01', 3005, NULL, 30);
INSERT INTO emple VALUES (7782,'CEREZO', 'DIRECTOR', 7839, '1991/06/09', 2885, NULL, 10);
INSERT INTO emple VALUES (7788,'GIL', 'ANALISTA', 7566, '1991/11/09', 3000, NULL, 20);
INSERT INTO emple VALUES (7839,'REY', 'PRESIDENTE', NULL, '1991/11/17', 4100, NULL, 10);
INSERT INTO emple VALUES (7844,'TOVAR', 'VENDEDOR', 7698, '1991/09/08', 1350, 0, 30);
INSERT INTO emple VALUES (7876,'ALONSO', 'EMPLEADO', 7788, '1991/09/23', 1430, NULL, 20);
INSERT INTO emple VALUES (7900,'JIMENO', 'EMPLEADO', 7698, '1991/12/03', 1335, NULL, 30);
INSERT INTO emple VALUES (7902,'FERNÁNDEZ','ANALISTA', 7566, '1991/12/03', 3000, NULL, 20);
INSERT INTO emple VALUES (7934,'MUÑOZ', 'EMPLEADO', 7782, '1992/01/23', 1690, NULL, 10);
```
>INSERTAMOS LOS REGISTROS EN LA TABLA [emple]


emp_no|apellido|oficio|dir|fecha_alt|salario|comision|dept_no
---|---|---|---|---|---|---|---
7369|SÁNCHEZ|EMPLEADO|7902|1990-12-17|1040|null|20
7499|ARROYO|VENDEDOR|7698|1990-02-20|1500|390|30
7521|SALA|VENDEDOR|7698|1991-02-22|1625|650|30
7566|JIMÉNEZ|DIRECTOR|7839|1991-04-02|2900|null|20
7654|MARTÍN|VENDEDOR|7698|1991-09-29|1600|1020|30
7698|NEGRO|DIRECTOR|7839|1991-05-01|3005|null|30
7782|CEREZO|DIRECTOR|7839|1991-06-09|2885|null|10
7788|GIL|ANALISTA|7566|1991-11-09|3000|null|20
7839|REY|PRESIDENTE|...|1991-11-17|4100|null|10
7844|TOVAR|VENDEDOR|7698|1991-09-08|1350|null|30
7876|ALONSO|EMPLEADO|7788|1991-09-23|1430|null|20
7900|JIMENO|EMPLEADO|7698|1991-12-03|1335|null|30
7902|FERNÁNDEZ|ANALISTA|7566|1991-12-03|3000|null|20
7934|MUÑOZ|EMPLEADO|7782|1992-01-23|1690|null|10



```mysql
create table depart(
  dept_no INTEGER,
  dnombre VARCHAR(30),
  loc VARCHAR(30)
);
```
>CRACION DE LA TABLA [depart]

```mysql
INSERT INTO depart VALUES (10, 'CONTABILIDAD', 'SEVILLA');
INSERT INTO depart VALUES (20, 'INVESTIGACIÓN', 'MADRID');
INSERT INTO depart VALUES (30, 'VENTAS', 'BARCELONA');
INSERT INTO depart VALUES (40, 'PRODUCCIÓN', 'BILBAO');
```
>INSERAMOS VALORES A LA TABLA [depart]

dept_no|dnombre|loc
---|---|---
10|CONTABILIDAD|SEVILLA
20|INVESTIGACIÓN|MADRID|
30|VENTAS|BARCELONA
40|PRODUCCIÓN|BILBAO

>-- 1) Mostrar el apellido, oficio y número de departamento de cada empleado.
```mysql
SELECT apellido, oficio, dept_no 
FROM emple; 
```

>-- 2) Mostrar el número, nombre y localización de cada departamento.
```mysql
SELECT dept_no, dnombre, loc 
FROM depart; 
```
>-- 3) Mostrar todos los datos de todos los empleados. 
```mysql
SELECT * 
FROM emple; 
```

>-- 4) Datos de los empleados ordenados por apellidos. 
```mysql
SELECT * 
FROM emple 
ORDER BY apellido; 
```

>-- 5) Datos de los empleados ordenados por número de departamento descendentemente. 
```mysql
SELECT * 
FROM emple 
ORDER BY dept_no DESC; 
```

>-- 6) Datos de los empleados ordenados por número de departamento descendentemente y dentro de cada departamento ordenados por apellido ascendentemente. 
```mysql
SELECT * 
FROM emple 
ORDER BY dept_no DESC, apellido; 
```

>-- 7) Mostrar el departamento y el apellido de los empleados ordenados por departamento descendentemente y por apellido ascendentemente
```mysql
SELECT dept_no, apellido 
FROM emple 
ORDER BY dept_no DESC, apellido; 
```

>-- 8) Mostrar los datos de los empleados cuyo salario sea mayor que 2000. 
```mysql
SELECT * 
FROM emple 
WHERE salario > 2000; 
```

>-- 9) Mostrar los datos de los empleados cuyo oficio sea 'ANALISTA'.
```mysql
SELECT * 
FROM emple 
WHERE oficio = 'ANALISTA'; 
```

>-- 10) Seleccionar el apellido y oficio de los empleados del departamento número 20. 
```mysql
SELECT apellido, oficio 
FROM emple 
WHERE dept_no = 20; 
```

>-- 11) Mostrar todos los datos de los empleados ordenados por apellido. 
```mysql
SELECT * 
FROM emple 
ORDER BY apellido; 
```

>-- 12) Seleccionar los empleados cuyo oficio sea 'VENDEDOR'. Mostrar los datos ordenados por apellido. 
```mysql
SELECT * 
FROM emple 
WHERE oficio = 'VENDEDOR' 
ORDER BY apellido; 
```

>-- 13) Mostrar los empleados cuyo departamento sea 20 y cuyo oficio sea 'EMPLEADO'. Ordenar el resultado por apellido. 
```mysql
SELECT * 
FROM emple 
WHERE dept_no = 20 AND oficio = 'EMPLEADO' 
ORDER BY apellido; 
```

>-- 14) Mostrar los empleados que tengan un salario mayor que 2000 o que pertenezcan al departamento número 20. 
```mysql
SELECT * 
FROM emple 
WHERE salario > 2000 OR dept_no = 20; 
```

>-- 15) Ordenar los empleados por oficio, y dentro de oficio por nombre. 
```mysql
SELECT * 
FROM emple 
ORDER BY oficio, apellido; 
```

>-- 16) Seleccionar de la tabla EMPLE los empleados cuyo apellido empiece por 'A'. 
```mysql
SELECT * 
FROM emple 
WHERE apellido LIKE 'A%'; 
```

>-- 17) Seleccionar de la tabla EMPLE los empleados cuyo apellido termine por 'Z'. 
```mysql
SELECT * 
FROM emple 
WHERE apellido LIKE '%Z';
```

>-- 18) Seleccionar de la tabla EMPLE aquellas filas cuyo APELLIDO empiece por 'A' y el OFICIO tenga una 'E' en cualquier posición. 
```
SELECT * 
FROM emple 
WHERE apellido LIKE 'A%' AND oficio LIKE '%E%'; 
```

>-- 19) Seleccionar los empleados cuyo salario esté entre 1000 y 2000. Utilizar el operador BETWEEN. 
```mysql
SELECT * 
FROM emple 
WHERE salario BETWEEN 1000 AND 2000; 
```

>-- 20) Obtener los empleados cuyo oficio sea 'VENDEDOR' y tengan una comisión superior a 1000. 
```mysql
SELECT * 
FROM emple 
WHERE oficio = 'VENDEDOR' AND comision > 1000; 
```

>-- 21) Seleccionar los datos de los empleados ordenados por número de departamento, y dentro de cada departamento ordenados por apellido. 
```mysql
SELECT * 
FROM emple 
ORDER BY dept_no, apellido; 
```

-- 22) Número y apellidos de los empleados cuyo apellido termine por 'Z' y tengan un salario superior a 2000. 

```mysql
SELECT emp_no, apellido 
FROM emple 
WHERE apellido LIKE '%Z' AND salario > 2000; 
```

>-- 23) Datos de los departamentos cuya localización empiece por 'B'. 
```mysql
SELECT * 
FROM depart 
WHERE loc LIKE 'B%'; 
```

>-- 24) Datos de los empleados cuyo oficio sea 'EMPLEADO', tengan un salario superior a 1100 y pertenezcan al departamento número 10. 
```mysql
SELECT * 
FROM emple 
WHERE oficio = 'EMPLEADO' AND salario > 1100 AND dept_no = 10; 
```

>-- 25) Mostrar los apellidos de los empleados que no tengan comisión. 
```mysql
SELECT apellido 
FROM emple 
WHERE comision IS NULL; SELECT apellido, comision
FROM emple
WHERE comision IS NULL OR comision = 0; 
```

>-- 26) Mostrar los apellidos de los empleados que no tengan comisión y cuyo apellido empiece por 'J'. 
```mysql
SELECT apellido 
FROM emple 
WHERE comision IS NULL AND apellido LIKE 'J%'; 
```

>-- 27) Mostrar los apellidos de los empleados cuyo oficio sea 'VENDEDOR', 'ANALISTA' o 'EMPLEADO'. 
```mysql
SELECT apellido 
FROM emple 
WHERE oficio IN ('VENDEDOR', 'ANALISTA', 'EMPLEADO'); 
```

>-- 28) Mostrar los apellidos de los empleados cuyo oficio no sea ni 'ANALISTA' ni 'EMPLEADO', y además tengan un salario mayor de 2000. 
```mysql
SELECT apellido, oficio, salario 
FROM emple 
WHERE oficio NOT IN ('ANALISTA', 'EMPLEADO') AND salario > 2000; SELECT apellido, oficio, salario
FROM emple
WHERE oficio <> 'ANALISTA'
  AND oficio <> 'EMPLEADO'
  AND salario > 2000;
  ```
  
>-- 29) Seleccionar de la tabla EMPLE los empleados cuyo salario esté entre 2000 y 3000 (utilizar BETWEEN). 
```mysql
SELECT * 
FROM emple 
WHERE salario BETWEEN 2000 AND 3000; 
```

>-- 30) Seleccionar el apellido, salario y número de departamento de los empleados cuyo salario sea mayor que 2000 en los departamentos 10 ó 30. 
```mysql
SELECT apellido, salario, dept_no 
FROM emple 
WHERE salario > 2000 AND (dept_no = 10 OR dept_no = 30); SELECT apellido, salario, dept_no
FROM emple
WHERE salario > 2000 AND dept_no IN (10, 30);
```

>-- 31) Mostrar el apellido y número de los empleados cuyo salario no esté entre 1000 y 2000 (utilizar BETWEEN). 
```mysql
SELECT apellido, emp_no 
FROM emple 
WHERE salario NOT BETWEEN 1000 AND 2000;
```

>-- 32) Obtener el apellidos de todos los empleados en minúscula
```mysql
SELECT lower(apellido) 
FROM emple; 
```

>-- 33) En una consulta concatena el apellido de cada empleado con su oficio. 
```mysql
SELECT concat(apellido, ' ', oficio) empleado_oficio 
FROM emple
ORDER BY 1; 
```

>-- 34) Mostrar el apellido y la longitud del apellido (función LENGTH) de todos los empleados, ordenados por la longitud de los apellidos de los empleados descendentemente. 
```mysql
SELECT apellido, length(apellido) 
FROM emple 
ORDER BY length(apellido) DESC; SELECT apellido, length(apellido) largo
FROM emple
ORDER BY 2 DESC;
```

>-- 35) Obtener el año de contratación de todos los empleados (función YEAR). 
```mysql
SELECT DISTINCT year(fecha_alt) año 
FROM emple; 
```

>-- 36) Mostrar los datos de los empleados que hayan sido contratados en el año 1992. 
```mysql
SELECT * 
FROM emple 
WHERE year(fecha_alt) = 1992; 
```
>-- 37) Mostrar los datos de los empleados que hayan sido contratados en el mes de febrero de cualquier año (función MONTHNAME). 
```mysql
SELECT * 
FROM emple 
WHERE monthname(fecha_alt) = 'February'; 
```

```mysql
SELECT apellido, fecha_alt
FROM emple
WHERE month(fecha_alt) = 2;
```

>-- 38) Para cada empleado mostrar el apellido y el mayor valor del salario y la comisión que tienen (funciones GREATEST y COALESCE)
```mysql
SELECT apellido, greatest(salario, coalesce(comision, 0)) 
FROM emple; 
```

>-- 39) Mostrar los datos de los empleados cuyo apellido empiece por 'A' y hayan sido contratados en el año 1990.
```mysql
SELECT apellido 
FROM emple 
WHERE apellido LIKE 'A%' AND year(fecha_alt) = 1990; 
```

>-- 40) Mostrar los datos de los empleados del departamento 10 que no tengan comisión. 
```mysql
SELECT * 
FROM emple 
WHERE dept_no = 10 AND comision IS NULL;
```

## Ejercicio MySQL - 02
```mysql
CREATE DATABASE bd_colegio;
USE bd_colegio
```
>CREACION DE BASE DE DATOS
```mysql
create table alumnos(
  expediente int(10) primary key,
  nombre varchar(50),
  localidad varchar(50),
  fecha_nac date,
  direccion varchar(50),
  curso int(2),
  nivel varchar(10),
  faltas int(3)
);
```

>CREACION DE LA TABLA alumnos
```mysql
insert into alumnos values(123456,'Juan Miguel Soler Bakero','Murcia','1995/10/10','Gran Vía, 2, 4A',1,'ESO',15);
insert into alumnos values(654321,'Laura Gómez Fernández','Lorca','1994/05/10','Junterones, 10, 5B',2,'ESO',25);
insert into alumnos values(765432,'Beatriz Martínez Hernández','Murcia','1993/05/05','Plaza Mayor, 6, 3B',3,'ESO',5);
insert into alumnos values(987654,'Diego Martín Llorente','Alhama de Murcia','1990/06/03','Diego de la Cierva, 5, 7A',1,'BACHILLER',34);
insert into alumnos values(445544,'Juan Francisco Cano Riquelme','Murcia','1992/07/01','Plaza de Belluga, 3, 4A',4,'ESO',13);
insert into alumnos values(223322,'Raquel Riquelme Rubio','Lorca','1990/11/23','San Juan, 14, 3B',1,'BACHILLER',7);
insert into alumnos values(9988877,'Cristina Sánchez Bermejo','Murcia','1995/03/19','Torre de Romo, 7',1,'ESO',1);
insert into alumnos values(334455,'Pedro Jesús Rodríguez Soler','Alhama de Murcia','1994/03/10','Camino de Badel, 4',2,'ESO',11);
insert into alumnos values(334400,'Javier Ramánez Rodríguez','Murcia','1993/05/27','Gran Vía, 4, 3A',3,'ESO',0);
insert into alumnos values(993322,'Gema Rubio Colero','Lorca','1992/09/09','Plaza Fuensanta, 5, 7A',1,'BACHILLER',19);
insert into alumnos values(554411,'Joaquín Hernández González','Lorca','1991/12/12','Junterones, 4, 5A',2,'BACHILLER',14);
```
>INSERTAMOS VALORES EN LA TABLE alumnos




expediente|nombre|localidad|fecha_nac|direccion|curso|nivel|faltas
---|---|---|---|---|---|---|---
123456|Juan Miguel Soler Bakero|Murcia|1995-10-10|Gran Vía, 2, 4A|1|ESO|15
654321|Laura Gómez Fernández|Lorca|1994-05-10|Junterones, 10, 5B|2|ESO|25
765432|Beatriz Martínez Hernández|Murcia|1993-05-05|Plaza Mayor, 6, 3B|3|ESO|5
987654|Diego Martín Llorente|Alhama de Murcia|1990-06-03|Diego de la Cierva, 5, 7A|1|BACHILLER|34
445544|Juan Francisco Cano Riquelme|Murcia|1992-07-01|Plaza de Belluga, 3, 4A|4|ESO|13
223322|Raquel Riquelme Rubio|Lorca|1990-11-23|San Juan, 14, 3B|1|BACHILLER|7
9988877|Cristina Sánchez Bermejo|Murcia|1995-03-19|Torre de Romo, 7|1|ESO|1
334455|Pedro Jesús Rodríguez Soler|Alhama de Murcia|1994-03-10|Camino de Badel, 4|2|ESO|11
334400|Javier Ramánez Rodríguez|Murcia|1993-05-27|Gran Vía, 4, 3A|3|ESO|0
993322|Gema Rubio Colero|Lorca|1992-09-09|Plaza Fuensanta, 5, 7A|1|BACHILLER|19
554411|Joaquín Hernández González|Lorca|1991-12-12|Junterones, 4, 5A|2|BACHILLER|14



>-- 1) Muestra todos los datos de todos los alumnos. 
```mysql
SELECT * 
FROM alumnos; 
``` 
>-- 2) Muestra el nombre , localidad y fecha de nacimiento de todos los alumnos. 
```mysql
SELECT nombre, localidad, fecha_nac 
FROM alumnos; 
```
>-- 3) Muestra el nombre de todos los alumnos. En el resultado de la consulta, la columna “Nombre” debe aparecer con la etiqueta “Nombre y apellidos” (ALIAS DE COLUMNAS). 
```mysql
SELECT nombre "Nombre y apellidos", fecha_nac 
FROM alumnos; 
```
>-- 4) Obtén el nombre y el número de faltas multiplicado por 2 de todos los alumnos (COLUMNAS CALCULADAS). En el resultado de la consulta, la columna faltas debe aparecer con la etiqueta “Faltas de asistencia” (ALIAS DE COLUMNAS) 
```mysql
SELECT nombre, faltas * 2 "Faltas de asistencia" 
FROM alumnos; 
```
>-- 5) Consulta los datos de los alumnos que son de Lorca. 
```mysql
SELECT * 
FROM alumnos 
WHERE localidad = 'Lorca'; 
```
>-- 6) Obtén los datos de los alumnos que son de Murcia o Alhama de Murcia. 
```mysql
SELECT nombre, localidad
FROM alumnos 
WHERE localidad = 'Alhama de Murcia' 
  OR localidad = 'Murcia'; SELECT nombre, localidad 
FROM alumnos 
WHERE localidad IN ('Murcia', 'Alhama de Murcia') 
```
```mysql
SELECT nombre, localidad 
FROM alumnos 
WHERE localidad LIKE '%murcia%'; 
```
>-- 7) Obtén los datos de los alumnos que son de Murcia y están en el primer curso de E.S.O. 
```mysql
SELECT * 
FROM alumnos 
WHERE localidad = 'Murcia' 
  AND nivel = 'ESO' 
  AND curso = 1; 
 ```
>-- 8) Muestra los alumnos que son de Lorca, están en segundo curso de Bachillerato y tienen más de 10 faltas. 
```mysql
SELECT * 
FROM alumnos 
WHERE localidad = 'Lorca' 
  AND nivel = 'BACHILLER' 
  AND curso = 2
  AND faltas > 10; 
  ```
>-- 9) Obtén los datos de aquellos alumnos que son de Murcia ordenados por nombre. 
```mysql
SELECT * 
FROM alumnos 
WHERE localidad = 'Murcia' 
ORDER BY nombre; 
```
>-- 10) Obtén los datos de todos los alumnos ordenados por nivel, y dentro de cada nivel por curso. 
```mysql
SELECT nivel, nombre, curso 
FROM alumnos 
ORDER BY nivel, curso; 
```
>-- 11) Muestra los datos de aquellos alumnos que tengan más de 10 faltas en primer o segundo curso. 
```mysql
SELECT nombre, faltas, curso 
FROM alumnos 
WHERE faltas > 10 
  AND (curso = 1 OR curso = 2);
```
```mysql
  SELECT nombre, faltas, curso 
FROM alumnos 
WHERE faltas > 10 
  AND curso IN (1, 2);
  ```
>-- 12) Muestra los datos de todos aquellos alumnos que tengan menos de 10 faltas en 3o o 4o curso y además sean de Murcia. 
```mysql
SELECT nombre, faltas, curso, localidad 
FROM alumnos 
WHERE faltas < 10 
  AND localidad = 'Murcia' 
  AND (curso = 3 or curso = 4); 
  ```
  ```mysql
  SELECT * 
FROM alumnos 
WHERE faltas < 10 
  AND localidad = 'Murcia' 
  AND curso IN (3, 4); 
  ```
>-- 13) Obtén con una consulta todos los cursos que hay sin repeticiones (DISTINCT). 
```mysql
SELECT DISTINCT curso 
FROM alumnos; SELECT DISTINCT nivel 
FROM alumnos; SELECT DISTINCT localidad 
FROM alumnos; 
```
>-- 14) Obtén los datos de los alumnos que no tengan 10 faltas en 1o de E.S.O. 
```mysql
SELECT nombre, faltas, curso, nivel 
FROM alumnos 
WHERE faltas <> 10 
  AND nivel = 'ESO' 
  AND curso = 1; 
  ```
>-- 15) Muestra los datos de aquellos alumnos cuyo nombre empiece por la letra 'B'. 
```mysql
SELECT nombre 
FROM alumnos 
WHERE nombre LIKE 'B%'; 
```
>-- 16) Con una consulta obtén los alumnos que son de Murcia y cuyo nombre termina con una letra 'O'. 
```mysql
SELECT nombre, localidad 
FROM alumnos 
WHERE nombre LIKE '%o' 
  AND localidad = 'Murcia'; 
  ```
>-- 17) Muestra los datos de todos aquellos alumnos que están en 1o curso de E.S.O. Y tienen una letra 'U' en la segunda posición del nombre. 
```mysql
SELECT nombre, curso, nivel 
FROM alumnos 
WHERE curso = 1 
  AND nivel = 'ESO' 
  AND nombre LIKE '_u%'; 
  ```
>-- 18) Obtén los datos de los alumnos cuya columna “Faltas” es nula. 
```mysql
SELECT nombre, faltas 
FROM alumnos 
WHERE faltas IS NULL ; 
```
>-- 19) Muestra los datos de aquellos alumnos que tienen entre 10 y 20 faltas (BETWEEN). Ordena el resultado por nombre. 
```mysql
SELECT nombre, faltas 
FROM alumnos 
WHERE faltas BETWEEN 10 AND 20
ORDER BY nombre; 
```
>-- 20) Muestra los datos de los alumnos que tienen entre 10 y 20 faltas y además son de Murcia. 
```mysql
SELECT nombre, faltas, localidad 
FROM alumnos 
WHERE faltas BETWEEN 10 AND 20 
  AND localidad = 'Murcia';
  ```
>-- 21) Muestra los datos de los alumnos que tienen entre 10 y 20 faltas, son de Murcia y están matriculados en 1o de E.S.O. 
```mysql
SELECT nombre, faltas, localidad, curso, nivel 
FROM alumnos 
WHERE faltas BETWEEN 10 AND 20 
  AND localidad = 'Murcia' 
  AND curso = 1 
  AND nivel = 'ESO'; 
  ```
>-- 22) Con una consulta muestra los datos de los alumnos cuyas faltas sean menores que 10 y mayores que 20. 
```mysql
SELECT nombre, faltas 
FROM alumnos 
WHERE faltas NOT BETWEEN 10 AND 20; SELECT nombre, faltas 
FROM alumnos 
WHERE faltas < 10 
  OR faltas > 20; 
  ```
>-- 23) Muestra los datos de los alumnos cuya fecha de nacimiento comprenda los años 1993 y 1994. Ordena el resultado por nombre. 
```mysql
SELECT nombre, fecha_nac 
FROM alumnos 
WHERE fecha_nac BETWEEN '1993-01-01' AND '1994-12-31' 
ORDER BY nombre; SELECT nombre, fecha_nac 
FROM alumnos 
WHERE year(fecha_nac) BETWEEN 1993 AND 1994 
ORDER BY nombre; SELECT nombre, fecha_nac 
FROM alumnos 
WHERE year(fecha_nac) IN (1993, 1994) 
ORDER BY nombre; SELECT nombre, fecha_nac 
FROM alumnos 
WHERE year(fecha_nac) = 1993 
  OR year(fecha_nac) = 1994
ORDER BY nombre; 
```
>-- 24) Muestra los datos de los alumnos que sean de primer o segundo curso (no importa que sean de E.S.O. O Bachiller). Utiliza el operador IN. 
```mysql
SELECT nombre, curso, nivel 
FROM alumnos 
WHERE curso IN (1, 2); 
-- 25) Obtén los datos de aquellos alumnos que sean de tercer o cuarto curso y sean de Murcia. Utiliza el operador IN. 
SELECT nombre, curso, localidad 
FROM alumnos 
WHERE curso IN (3, 4) 
  AND localidad = 'Murcia'; 
  ```
>-- 26) Muestra los datos de los alumnos que no sean de E.S.O, ordenados por curso y por nombre descendentemente. Utiliza el operador IN. 
```mysql
SELECT nombre, curso, nivel 
FROM alumnos 
WHERE nivel NOT IN ('ESO') 
ORDER BY curso DESC, nombre DESC; 
```
>-- 27) Muestra los datos de los alumnos que sean de primer o segundo curso y no sean de Bachiller. Ordena el resultado por nombre. 
```mysql
SELECT nombre, curso, nivel 
FROM alumnos 
WHERE nivel <> 'BACHILLER'
  AND (curso = 1 OR curso = 2) 
ORDER BY nombre; SELECT nombre, curso, nivel 
FROM alumnos 
WHERE nivel NOT IN ('BACHILLER') 
  AND curso IN (1, 2) 
ORDER BY nombre; 
```
>-- 28) Obtén los datos de los alumnos cuyo nombre empiece por la letra 'J', que tengan más de 10 faltas y no sean de Bachiller. Ordena el resultado por curso, y dentro de cada curso, por nombre. 
```mysql
SELECT nombre, faltas, curso, nivel 
FROM alumnos 
WHERE nivel <> 'BACHILLER' 
  AND faltas > 10
  AND nombre LIKE 'J%' 
ORDER BY curso, nombre; SELECT nombre, faltas, curso, nivel 
FROM alumnos 
WHERE nivel <> 'BACHILLER' 
  AND faltas > 10
  AND nombre >= 'J' AND nombre < 'K'
ORDER BY curso, nombre; 
```
>-- 29) Con una consulta obtén el expediente, nombre, curso y nivel de todos los alumnos ordenado por curso, nivel ascendentemente y nombre descendentemente cuyo nivel no sea 'BACHILLER'. 
```mysql
SELECT expediente, nombre, curso, nivel 
FROM alumnos 
WHERE nivel <> 'Bachiller'
ORDER BY curso, nivel, nombre DESC; 
```
>-- 30) Con una consulta obtén el nombre de cada alumno en mayúscula cuya localidad sea Murcia. 
```mysql
SELECT upper(nombre) 
FROM alumnos 
WHERE localidad = 'Murcia';
```
>-- 31) Muestra el nombre de cada alumno en mayúscula y la localidad a la que pertenecen en minúscula, ordenados por localidad. 
```mysql
SELECT upper(nombre), lower(localidad) 
FROM alumnos 
ORDER BY localidad; 
```
>-- 32) Con una consulta concatena el nombre de cada alumno y la localidad y sustituye 'BACHILLER' por 'Bachillerato'. 
```mysql
SELECT concat(nombre, ' ', localidad), 
  replace(nivel, 'BACHILLER', 'Bachillerato') 
FROM alumnos; SELECT replace(nivel, 'E', 'XX')
FROM alumnos; 
```
>-- 33) Con una consulta obtén el nombre de cada alumno y la longitud de la cadena “Nombre”. 
```mysql
SELECT nombre, length(nombre) 
FROM alumnos; SELECT nombre,
  length(nombre) numero_caracteres, 
  replace(nombre, ' ', '') nombre_sin_espacios,
  length(replace(nombre, ' ', '')) numero_letras 
FROM alumnos; 
```
>-- 34) Con una consulta obtén el nombre, año de nacimiento y mes de nacimiento de cada uno de los alumnos. 
```mysql
SELECT nombre,
  year(fecha_nac),
  month(fecha_nac),
  day(fecha_nac),
  monthname(fecha_nac) 
FROM alumnos; 
```
>-- 35) Con una consulta muestra el nombre y edad de cada uno de los alumnos (la edad se calcula restando al año actual el año de nacimiento) 
```mysql
SELECT nombre, 
  2012 - year(fecha_nac) 
FROM alumnos; SELECT nombre, 
  year(current_date()) - year(fecha_nac) edad
FROM alumnos; SELECT CURRENT_DATE, CURRENT_TIME, CURREN_TIMESTAMP;
```



