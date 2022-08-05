# TIPs 


## Preguntas teoricas:


* Pregunta: ¿Cuál es el equivalente de DataFrame y las columnas de los DataFrames en SQL? <br>
  R: Los DataFrames son las tablas en SQL y las columnas de los DataFrames son los campos de éstas.

* Pregunta: ¿Cuál es la diferencia entre un Data Warehouse y Data Lake? <br>
  R: El Data Lake es un gran conjunto de datos, los cuales no se han organizado, trabajado o definido la finalidad de éstos. En cambio, un data warehouse es un almacen de datos ya estructurados y filtrados.

* Pregunta: ¿Cuáles son los tipos de JOIN y con qué objetivo se utiliza cada uno? <br>
  R: Las cláusulas JOIN son usadas para combinar filas de dos o más tablas basados en la relación que tengan éstas. Existen cuatro tipos de joins:
  - Inner join o join: se utiliza generalmente para unir consultas, logrando extraer los registros que poseen coincidencias en ambas tablas (intersección de tablas). 
  - Left join: se utiliza para extraer todos los registros de la tabla definida a la izquierda de la cláusula y aquellos que coincidan con éstos y pertenezcan a la tabla definida a la derecha. 
  - Right join: se utiliza para extraer todos los registros de la tabla definida a la derecha de la cláusula y aquellos que coincidan con éstos y pertenezcan a la tabla definida a la izquierda. 
  - Full join (outer join): se utiliza para extraer todos los registros que coinciden con la tabla izquierda o derecha (unión de tablas)

* Pregunta: ¿Qué está mal en la siguiente consulta?<br>
  SELECT Rango_Etario, AVG(Edad)<br>
  FROM cliente<br>
  WHERE AVG(Edad)>30<br>
  GROUP BY Rango_Etario;

  R: Para filtrar con valores agrupados (media de la edad en este caso) se debe utilizar HAVING, no WHERE. La cláusula HAVING iría después del GROUP BY.

* Pregunta: ¿Cuál es la diferencia entre las cláusulas HAVING y WHERE?<br>
  R: WHERE se utiliza para definir una condición en uno o más campos de las tablas utilizadas en la consulta. <br>
  HAVING se utiliza para filtrar un resultado agregado. 

* Pregunta: ¿Cuál es el objetivo de la siguiente consulta? <br>
  SELECT * INTO cliente_2<br>
  FROM cliente WHERE 1 = 2;<br>

  R: La consulta copia una tabla vacía llamada "cliente_2" la cual posee la misma estructura que la tabla "cliente".
## Practico: 
Escribir un programa en Python que, dado un valor máximo que se le pide al usuario, devuelva un diccionario con los números y sus potencias asociadas, por ejemplo, si se le pasa el valor 5, devuelve {1:1, 2:4, 3:9, 4:16, 5:25}.

### Respuesta propuesta

maximo = int(input("Por favor, ingrese un valor máximo : "))<br>
diccionario = {}

for x in range(1, maximo + 1):<br>
    diccionario[x] = x * x<br>

print("\nDiccionario = ", diccionario)
