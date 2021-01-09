## PRÁCTICA 2.- Countries V2

Enlace a la API: https://countries-274616.ew.r.appspot.com/

Ejercicios aportados por Enzo Puyol (https://github.com/EnzoPujol) (¡¡¡MUCHAS GRACIAS AMIGO!!!)

## A.- Paises (Country)

### 1.- Obtener lista de todos los países con "Country"

Las propiedades que se mostrarán.
* area
* capital
* name
* nativeName

### 2.- Obtener lista de todos los países "Country" con nombre (name) original o no (haciendo uso de directiva include)
Lista de los países mostrando toda la información disponible dependiendo de si queremos añadir el nombre (name) originak o no. Todo depende de la directiva **"include"**. Recordar que la directiva se añadía en una propiedad al final con "@include(if: <valor_boolean>)" y que en la query variables tenemos que pasar ese argumento

### 3 - Obtener una lista de todas las zonas temporales - husos horarios (Timezone) junto a la lista de los países que forman partes de ellas.
En este caso queremos obtener la lista de todos los husos horarios / zonas horarias junto con la lista con los datos básicos, ese será el mínimo que se requiere para obtener el ejercicio concluido, pero si se quiere añadir alguna información más de manera extra, podéis hacerlo

Las propiedades que se mostrarán serán las siguientes:
* name (del timezone)
* Lista de paises que corresponden a ese zona horario

4 - Agregar al inciso anterior la obtención de los idiomas
oficiales de cada país.

5 - Agregar al inciso anterior la directiva include para los países,
y la directiva skip para los idiomas de cada país.

6 - Ordenar los idiomas oficiales por orden ascendente.

7 - Implementar el uso de Fragment en la obtención tanto de los
países como de los idiomas oficiales.


#Para cada uno de los incisos, los elementos a devolver de cada
objeto son a elección, mira bien la documentación para saber un poco más ;) 

