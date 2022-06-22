# TIPs - Grupo B - Entrevista n°1

Recuerden que esto es una herramienta para practicar como seria una entrevista real<br>
Bajo ningun punto de vista queremos su compañero pase un mal momento, es simplemente guiarlo a traves de las preguntas<br>
Esto tampoco quiere decir que hay que darle las respuestas facilmente, se lo puede aconsejar, se lo puede guiar o incluso darle pistas

## Preguntas teoricas:
### 1)¿Cuáles son las reglas para las variables locales y globales en Python?


Si una variable es definida fuera de una función entonces es implícitamente global.
Si la variable se asigna a un nuevo valor dentro de la función significa que es local. 
Si queremos que sea global tenemos que definirla explícitamente como global.
La variable referenciada dentro de la función están implícitas como global

### 2) ¿Cuántos tipos de datos existen en Pandas?

Pandas dispone de tres estructuras de datos diferentes: <br>
	1.Series: Estructura de una dimensión.<br>
	2.DataFrame: Estructura de dos dimensiones (tablas)<br>
	3.Panel: Estructura de tres dimensiones (cubos).<br>

### 3) ¿Qué es un "diccionario"?
¿Saben que es un tipo de datos integrados? Un diccionario es exactamente eso.

Los diccionarios están compuestos de claves y sus valores correspondientes. 
Aquí tienes un ejemplo:

dict={'Car':'Ford','Type':'Mustang','Year':'1967'}<br>
print dict[Car]<br>
Ford<br>
print dict[Type]<br>
Mustang<br>
print dict[Year]<br>
1967<br>



## Practico: 
Escribir un programa en Python para comprobar si una secuencia es un Palíndromo.


Opcion #1
```
a=input("introduzca una secuencia: 	")
b=a[::-1]
if a==b:
 print("palindromo")
 ptint(a)
else:
 print("No es palindromo")
 ```
 
Opcion #2 

```
a_string =input("introduzca una secuencia: ")
def palindrome(string):
    string = string.lower().replace(' ', '')
    reversed = ''
    for i in range(len(string), 0, -1):
        reversed += string[i-1]
    return string == reversed
print(palindrome(a_string))
```

