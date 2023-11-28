# Reto 12, un reto breve

Por fin un reto que no me lleve 1 día en hacerlo, FELICIDAD
Aquí en este repo vamos a trabajar un poco lo que son herramientas y un poco más de ejemplificar que usos se le puede llegar a dar a este tipo de programas.

Bueno, como primer punto nos piden:
Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.

Aquí información de cada uno, con un pequeño ejemplo que pude encontrar buscando en el famoso y muy querido internet (Ojo, no es información mía):

1. **`endswith(suffix[, start[, end]])`:**
   - Este método comprueba si la cadena termina con el sufijo especificado.
   - `suffix`: El sufijo que se está buscando al final de la cadena.
   - `start` (opcional): Índice donde comienza la búsqueda (por defecto, toda la cadena).
   - `end` (opcional): Índice donde termina la búsqueda (por defecto, toda la cadena).

2. **`startswith(prefix[, start[, end]])`:**
   - Similar a `endswith`, pero verifica si la cadena comienza con el prefijo proporcionado.

3. **`isalpha()`:**
   - Devuelve `True` si todos los caracteres de la cadena son letras del alfabeto (sin contar espacios u otros caracteres).
   - Ejemplo: `"Hola".isalpha()` devuelve `True`, pero `"Hola 123".isalpha()` devuelve `False`.

4. **`isalnum()`:**
   - Devuelve `True` si todos los caracteres de la cadena son alfanuméricos (letras o números).
   - Ejemplo: `"Hola123".isalnum()` devuelve `True`, pero `"Hola 123".isalnum()` devuelve `False`.

5. **`isdigit()`:**
   - Devuelve `True` si todos los caracteres de la cadena son dígitos.
   - Ejemplo: `"123".isdigit()` devuelve `True`, pero `"123abc".isdigit()` devuelve `False`.

6. **`isspace()`:**
   - Devuelve `True` si todos los caracteres de la cadena son espacios en blanco.
   - Ejemplo: `"   ".isspace()` devuelve `True`, pero `"Hola Mundo".isspace()` devuelve `False`.

7. **`istitle()`:**
   - Devuelve `True` si la cadena sigue la convención de mayúsculas y minúsculas de un título.
   - Ejemplo: `"Hola Mundo".istitle()` devuelve `True`, pero `"hola mundo".istitle()` devuelve `False`.

8. **`islower()`:**
   - Devuelve `True` si todos los caracteres de la cadena están en minúsculas.
   - Ejemplo: `"hola mundo".islower()` devuelve `True`, pero `"Hola Mundo".islower()` devuelve `False`.

9. **`isupper()`:**
   - Devuelve `True` si todos los caracteres de la cadena están en mayúsculas.
   - Ejemplo: `"HOLA MUNDO".isupper()` devuelve `True`, pero `"Hola Mundo".isupper()` devuelve `False`.

Estos métodos nos ayudan mucho a realizar comprobaciones específicas en cadenas, lo que nos sirve para trabajar la validación y manipulación de datos, ya sea en archivos de texto u otros archivos.

# Segundo punto 
A la fecha que el archivo no está disponible el archivo para trabajar, sin embargo aquí dejo el código desarrollado para extraer la cantidad de vocales, cantidad de consonantes y hacer un listado de las 50 palabras que más se repiten

Para el desarrollo de este archivo, vi que una biblioteca o modulo me podrían ser de ayuda, entonces por eso las usé 're' y 'counter, collections', más que todo por comodidad y que es más facil hacer el código de esta manera.
Como mencioné anteriormente, no me fue posible cargar el archivo porque no está disponible así que tomé una frase para ejemplificar y demostrar que afortunadamente el código funciona:

```python
import re
from collections import Counter

def procesarArchivo(nombreArchivo):
    # Abrir el archivo en modo lectura
    with open(nombreArchivo, 'r', encoding='utf-8') as archivo:
        # Leer el contenido del archivo
        contenido = archivo.read()

        # Contar vocales y consonantes
        vocales = re.findall('[aeiouáéíóú]', contenido, flags=re.IGNORECASE)
        consonantes = re.findall('[bcdfghjklmnpqrstvwxyz]', contenido, flags=re.IGNORECASE)

        cantidadVocales = len(vocales)
        cantidadConsonantes = len(consonantes)

        # Tokenizar palabras y contar ocurrencias
        palabras = re.findall(r'\b\w+\b', contenido.lower())
        contadorPalabras = Counter(palabras)

        # Obtener las 50 palabras más comunes
        palabrasComunes = contadorPalabras.most_common(50)

        return cantidadVocales, cantidadConsonantes, palabrasComunes

# Reemplazar 'nombre_del_archivo.txt' con el nombre de tu archivo
archivoAProcesar = 'nombre_del_archivo.txt'

# Llamar a la función y obtener los resultados
vocales, consonantes, palabrasComunes = procesarArchivo(archivoAProcesar)

# Imprimir los resultados
print(f"Cantidad de vocales: {vocales}")
print(f"Cantidad de consonantes: {consonantes}")
print("50 palabras más comunes:")
for palabra, frecuencia in palabrasComunes:
    print(f"{palabra}: {frecuencia}")

````
El ejemplo que yo usé y que si quieres, puedes copiar y probar también:
```
La playa es un lugar hermoso. La arena, el sol y las olas crean una atmósfera única.
````
````
Si hiciste todo bien, te debería aparecer estos datos:
Cantidad de vocales: 47

Cantidad de consonantes: 49

50 palabras más comunes:

la: 2

playa: 1

es: 1

un: 1

lugar: 1

hermoso: 1

arena: 1

el: 1

sol: 1

y: 1

las: 1

olas: 1

crean: 1

una: 1

atmósfera: 1

única: 1
````

Y eso sería todo por hoy, afortunadamente ya pude dar fin a este reto, no estuvo tan pesado y dificil como los otros pero aún así tuvo su complejidad para un estudiante de Ingeniería Química que a penas se esta metiendo en el tema de python

¡Muchas gracias por pasar por aquí, feliz día!






