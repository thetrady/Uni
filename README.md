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


## Ejercicios SQL

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






