# TIPs - Grupo A - Entrevista n°2 

Recuerden que esto es una herramienta para practicar como seria una entrevista real<br>
Bajo ningun punto de vista queremos su compañero pase un mal momento, es simplemente guiarlo a traves de las preguntas<br>
Esto tampoco quiere decir que hay que darle las respuestas facilmente, se lo puede aconsejar, se lo puede guiar o incluso darle pistas

## Preguntas teoricas:

* Pregunta 8 ¿Cuáles son las ventajas y desventajas de las vistas en la base de datos?
 Ventajas de las vistas:

Como no hay una ubicación física donde se almacenan los datos en la vista, genera resultados sin desperdiciar recursos.
El acceso a los datos está restringido ya que no permite comandos como la inserción, actualización y eliminación.
Desventajas de las vistas:

La vista se vuelve irrelevante si descartamos una tabla relacionada con esa vista.
Se ocupa mucho espacio de memoria cuando se crea la vista para tablas grandes.

* Pregunta 10: ¿Qué entiendes por Join?

  Unir es el proceso de derivar la relación entre diferentes tablas combinando columnas de una o más tablas que tienen valores comunes en cada una. Cuando una tabla se une a sí misma, se conoce como Self Join.

* Pregunta 11: Diferenciar entre índice 'Clúster' y 'No clúster'.

  El índice agrupado altera la tabla y reordena la forma en que se almacenan los registros en la tabla. La recuperación de datos se acelera mediante el uso del índice agrupado.

Un índice no agrupado altera los registros que se almacenan en la tabla, pero crea un objeto completamente diferente dentro de la tabla.

* Pregunta 12: ¿Qué es la partición de bases de datos?

El particionamiento de la base de datos es el proceso de particionar tablas, índices en partes más pequeñas para administrar y acceder a los datos en un nivel más fino.
Este proceso de partición reduce el costo de almacenar una gran cantidad de datos y mejora el rendimiento y la capacidad de administración.

* Pregunta 13:Explique la importancia del particionamiento de la base de datos.

 La importancia de la partición de la base de datos es:

Mejora el rendimiento y la capacidad de administración de las consultas.
Simplifica las tareas de administración comunes.
Actúa como una herramienta clave para los sistemas de construcción con requisitos de disponibilidad extremadamente altos.
Permite acceder a gran parte de una única partición.


* Pregunta 14: Diferenciar entre los comandos 'DELETE', 'TRUNCATE' y 'DROP'.

Responder: Después de la ejecución de 'ELIMINAR' operación, las declaraciones COMMIT y ROLLBACK se pueden realizar para recuperar los datos perdidos.

Después de la ejecución de 'TRUNCAR' operación, COMMIT y ROLLBACK no se pueden realizar para recuperar los datos perdidos.

'SOLTAR' El comando se usa para eliminar la tabla o la clave como la clave principal / clave externa.


## Practico: 
#El fichero titanic.csv contiene información sobre los pasajeros del Titanic. Escribir un programa con los siguientes requisitos:

#El fichero titanic.csv contiene información sobre los pasajeros del Titanic. Crear un dataframe con Pandas y a partir de él generar los siguientes diagramas.

* 1 Diagrama de sectores con los fallecidos y supervivientes.
* 2 Histograma con las edades.
* 3 Diagrama de barras con el número de personas en cada clase.
* 4 Diagrama de barras con el número de personas fallecidas y supervivientes en cada clase.
* 5 Diagrama de barras con el número de personas fallecidas y supervivientes acumuladas en cada clase.
* 6 Mostrar por pantalla el porcentaje de personas que sobrevivieron y murieron.
* 7 Mostrar por pantalla el porcentaje de menores edad que sobrevivieron en cada clase.


import pandas as pd 
import matplotlib.pyplot as plt 

#Creamos un dataframe a partir del fichero csv
df_titanic = pd.read_csv('titanic.csv')
#Creamos la figura y los ejes
fig, ax = plt.subplots()

* 1 Diagrama de sectores de falleccidos y supervivientes
df_titanic.Survived.value_counts().plot(kind = "pie", labels = ["Muertos", "Supervivientes"], title = "Distribución de supervivientes")
plt.show()

* 2 Histograma de edades
df_titanic.Age.plot(kind = "hist", title = "Histograma de edades")
plt.show()

* 3 Diagrama de barras con el número de personas de cada clase
df_titanic.Pclass.value_counts().plot(kind = "bar", title = "Número de personas por clase")
plt.show()

#Otra forma
df_titanic.groupby("Pclass").size().plot(kind = "bar", title = "Número de personas por clase")
plt.show()

* 4 Diagrama de barras con el número de personas fallecidas y supervivientes de cada clase
df_titanic.groupby(["Pclass", "Survived"]).size().unstack().plot(kind = "bar", title = "Número de personas fallecidas y supervivientes por clase")
plt.show()

* 5 Diagrama de barras con el número de personas fallecidas y supervivientes acumuladas de cada clase
df_titanic.groupby(["Pclass", "Survived"]).size().unstack().plot(kind = "bar", stacked = True, title = "Número de personas fallecidas y supervivientes por clase")
plt.show()

* 6 Mostrar por pantalla el porcentaje de personas que sobrevivieron y murieron
print(df_titanic['Survived'].value_counts()/df_titanic['Survived'].count() * 100)

# Alternativa
print(df_titanic['Survived'].value_counts(normalize=True) * 100)


