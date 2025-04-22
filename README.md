# Consultas2_SQL

## Vista previa
![screen1](screen1.png  "screen2")
## Estructura Departamento
![screen2](screen2.png  "screen2")
## Estructura Empleado
![screen3](screen3.png  "screen3")

# CONSULTAS

## Consulta 1

1 .Obtener la lista de los apellidos de todos los empleados.

`SELECT apellidos_empleado FROM Empleado;`

![screen4](screen4.png  "screen4")

2.Obtener los apellidos de todos los empleados sin repeticiones.

`SELECT DISTINCT apellidos_empleado FROM Empleado;`

![screen5](screen5.png  "screen5")

3.Obtener todos los datos de los empleados que se apellidan 'Gomez'.

`SELECT * FROM Empleado WHERE apellidos_empleado = 'Gomez';`

![screen6](screen6.png  "screen6")

4.Obtener todos los datos de los empleados que se apellidan "Diaz" y los que se apellidan "Rodriguez".  Usar OR o IN

`SELECT * FROM Empleado WHERE apellidos_empleado = 'Diaz' OR apellidos_empleado = 'Rodriguez';`

![screen7](screen7.png  "screen7")

5.Obtener los nombres de los empleados que trabajan en el departamento 11

`SELECT nombre_empleado FROM Empleado WHERE id_departamento = 11;`

![screen8](screen8.png  "screen8")

6. Obtener todos los datos de los empleados cuyo apellido empiece por 'P'

`SELECT * FROM Empleado WHERE apellidos_empleado LIKE 'P%';`

![screen9](screen9.png  "screen9")

7. Obtener el presupuesto total de todos los departamentos.

`SELECT SUM(presupuesto_departamento) AS presupuesto_total FROM Departamentos;`

![screen10](screen10.png  "screen10")

8. Obtener el número de empleados de cada departamento.

`SELECT departamento_id, COUNT(*) AS cantidad_empleados FROM empleados GROUP BY departamento_id;`

![screen12](screen12.png  "screen12")

9. Obtener un listado completo de empleados, incluyendo por cada empleado los datos del empleado y de su departamento.

`SELECT * FROM Empleado JOIN Departamento ON Empleado.id_departamento = Departamento.id_departamento;`

![screen11](screen11.png  "screen11")

10. Obtener un listado completo de empleados, incluyendo el nombre y apellidos del empleado junto al nombre y presupuesto de su departamento.

`SELECT Empleado.nombre_empleado, Empleado.apellidos_empleado, Departamento.nombre_departamento, Departamento.presupuesto_departamento FROM Empleado JOIN Departamento ON Empleado.id_departamento = Departamento.id_departamento;`

![screen13](screen13.png  "screen13")

11. Obtener los nombres y apellidos de los empleados que trabajen en departamentos cuyo presupuesto sea mayor a 100000000.

`SELECT Empleado.nombre_empleado, Empleado.apellidos_empleado FROM Empleado JOIN Departamento ON Empleado.id_departamento = Departamento.id_departamento WHERE Departamento.presupuesto_departamento > 100000000;`

![screen14](screen14.png  "screen14")