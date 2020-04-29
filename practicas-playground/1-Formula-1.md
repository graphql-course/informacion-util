## PRÁCTICA 1.- API Formula 1

Enlace a la API: https://f1-graphql.herokuapp.com/

## A.- Temporadas (seasonsList)

### 1.- Obtener lista de todas las temporadas seasonsList

Las propiedades que se mostrarán.
* year
* url
* urlMobile

### 2.- Obtener lista de todas las temporadas seasonsList con URL Mobile o no (haciendo uso de directiva include)
Lista de temporadas mostrando toda la información disponible dependiendo de si queremos añadir la url del móvil o no. Todo depende de la directiva **"include"**. Recordar que la directiva se añadía en una propiedad al final con "@include(if: <valor_boolean>)" y que en la query variables tenemos que pasar ese argumento

Ejemplo:

```
QUERY
query getList($show: Boolean!){
  characters {
    id
    name
    actor @include(if: $show)
    votes
  }
}
QUERY VARIABLES
{
  "show": false //En este caso solo mostraría id, name y votes
}
```

### 3.- Obtener lista de todas las temporadas seasonsList con URL Mobile o no (haciendo uso de directiva skip)
Lista de temporadas mostrando toda la información disponible dependiendo de si queremos añadir la url del móvil o no. Todo depende de la directiva **"skip"**. Recordar que la directiva se añadía en una propiedad al final con "@skip(if: <valor_boolean>)" y que en la query variables tenemos que pasar ese argumento. Es lo mismo que el anterior, pero en este caso será trabajando de manera inversa en los valores del Query Variables.

Ejemplo: 
```
QUERY
query getList($hide: Boolean!){
  characters {
    id
    name
    actor @skip(if: $hide)
    votes
  }
}
QUERY VARIABLES
{
  "hide": true //En este caso solo mostraría id, name y votes
}
```
### 4.- Obtener lista de todo las temporadas seasonsList haciendo uso de un Fragment para añadir la información de la temporada

Vamos a empezar a practicar con elementos que nos van a permitir tener consultas más limpias. Haremos uso de los Fragments basándonos en el ejercicio 1 donde obtenemos la lista de todas las temporadas. Es simplemente refactorizar dentro de un Fragment la información.

Pasar de algo así:
```
{
  characters {
    id
    name
    actor
    votes
  }
}

```
A esto:
```
{
  characters {
    ...CharacterObject
  }
}
fragment CharacterObject on Character {
  id
  name
  actor
  votes
}
```
Como veís, el objeto Character, que tiene las propiedades id, name, actor, votes,... lo hemos añadido como un Fragment y ahora imaginaros que voy a hace consulta de 2 personajes especificos, pues gracias a ello, tendré que pone menos información.

Por ejemplo, haciendo uso de este elemento si hacemos las consultas especificas:
Pasar de algo así:
```
{
  character(id: "1" {
    id
    name
    actor
    votes
  }
  character(id: "2" {
    id
    name
    actor
    votes
  }
}

```
A esto:
```
{
  character(id: "1") {
    ...CharacterObject
  }
  character(id: "2") {
    ...CharacterObject
  }
}
fragment CharacterObject on Character {
  id
  name
  actor
  votes
}
```
Consiguiendo el mismo resultado y como podéis apreciar, escribiendo bastante menos información. Ahí se ve realmente la utilidad de usar Fragment.
...

### 5.- Combinar el uso del Fragment con la directiva include

Cogemos el ejercicio #2 y lo modificamos para hacer uso con un Fragment.

### 6.- Combinar el uso del Fragment con la directiva skip
Cogemos el ejercicio #3 y lo modificamos para hacer uso con un Fragment.

Resultado: 

## B.- Pilotos (drivers, historyDrivers, driversYear, driversCount)

### 1.- Obtener número de pilotos

Una consulta que nos devolverá el número de pilotos. Fijaros bien dentro de la documentación.

### 2.- Obtener pilotos del año 2019

Las propiedades que se mostrarán.
* id
* url
* urlMobile
* name
* dateOfBirth
* nationality
* code
* permanentNumber

### 3.- Obtener pilotos del año 2018

Mostrar las mismas propiedades, únicamente cambia el año

### 4.- Obtener pilotos de los años 2012 al 2016

Mostrar las mismas propiedades, únicamente cambia el año. Ejecutar varias consulas en la misma query.

Ejemplo:
```
{
  character(id: "1" {
    id
    name
    actor
    votes
  }
  character(id: "2" {
    id
    name
    actor
    votes
  }
}
```

### 5.- Obtener pilotos de la ronda 5 del año 2018


### 6.- Obtener pilotos de la ronda 1 del año 2019

### 7.- Añadir el uso del Fragment en las consultas anteriores de este apartado.

### 8.- Combinar el uso del Fragment con la directiva include usando la B-2

Asignamos la directiva "include" para mostrar el "code" e "id" del piloto cuando le decimos que si. Tenemos que añadir la directiva en esas propiedades y hacer uso del Query Variables.

Cogemos el ejercicio #2 y lo modificamos para hacer uso con un Fragment.

### 9.- Combinar el uso del Fragment con la directiva include usando la B-2

Asignamos la directiva "include" para mostrar el "code" e "id" del piloto cuando le decimos que si. Tenemos que añadir la directiva en esas propiedades y hacer uso del Query Variables.

Cogemos el ejercicio #2 y lo modificamos para hacer uso con un Fragment.

### 10.- Crear vuestras Queries con las diferentes variantes que os he dado y usando las definiciones del Schema

Como repaso, os dejo que libremente intentéis ejecutar diferentes queries (no tengáis miedo a probar y "romper" el playground, que es como se aprende) y posteriormente que los compartáis en el apartado de preguntas y respuestas o mediante el grupo **"GraphQL - Español"**.

**Enunciado preparado el 02/05/2020**