## Operaciones funcionales

### OBJETIVO

- Utilizar una serie de funciones implementadas en kotlin para el tratamiento de información, con aproximación a programación funcional.

#### REQUISITOS

1. Haber integrado colecciones en Kotlin.
2. Saber implementar conceptos básicos de programación funcional.

#### DESARROLLO

##### Filter

Esta función de orden superior se encuentra en colecciones como listas o mapas, y filtra sólo los datos mediante un predicado, que no es más que una función lambda que toma un elemento de la colección y devuelve un Booleano, `Filter` se queda solo con los elementos que la evaluación del predicado dio `true`.

Supongamos que tenemos una lista de calificaciones y queremos filtrar únicamente las calificaciones que pasan, para esto, fijamos el 6 como el mínimo aprobatorio.

```kotlin
val calificaciones = listOf(10,8, 9 ,5,3,2,5,1,7,6,9,4,10,3,6,2,6,5)
```

esta es nuestra lista de calificaciones. De forma imperativa, podríamos haber filtrado los valores iterando la lista y con un if, agregar únicamente a los que pasaban la condición:

```kotlin
 var aprobados = mutableListOf<Int>()
    for (calificacion in calificaciones){
        if(calificacion>5){
            aprobados.add(calificacion)
        }
    }
    println(aprobados)
```

A simple vista vemos que esta opción es bastante verbosa e ineficiente, puesto que declaramos una lista mutable y en cada iteración se cambia su valor.

La aproximación funcional de este ejercicio no itera de forma explicita sobre la lista, sino que simplemente ve cuales de los elementos cumplen el predicado.

```kotlin
val aprobados = calificaciones.filter{ calificacion -> calificacion>5}
println(aprobados);
```
Podríamos tener una versión más corta de la lambda con el uso de ***it***

```kotlin
val aprobados = calificaciones.filter{ it>5}
```

con la función ***partition*** podremos separar en dos arreglos las calificaciones aprobadas de las reprobadas.

```kotlin
  val (notasAprobadas2,notasReprobadas) = calificaciones.partition { it>5}
    println(notasAprobadas2);
    println(notasReprobadas);
```

También podemos filtrar maps. 

```kotlin
val numbersMap =  mapOf("Lorenza" to 6, "Juan" to 4, "Martina" to 8, "David" to 7)
```

si quisieramos saber la calificación de alguien específico, podemos hacer lo siguiente:

```kotlin
   val notasAlumnos =  mapOf("Lorenza" to 6, "Juan" to 4, "Martina" to 8, "David" to 7)
     val porNombre = notasAlumnos.filter { (key, value) ->  key == "David"}
    println(porNombre)
```

##### Map

Esta es una *Collection Transformation* que crea colecciones a partir del resultado de operaciones hechas por una función lambda. 

`map` aplica una función a cada elemento de la colección y nos regresa la colección resultante.

Así, si tenemos una colección de precios libres y necesitamos sumarle el IVA del 16%, podemos hacer lo siguiente: 

```kotlin
    val preciosLibres = setOf(1024.0, 2408.5, 8224.33)
    val preciosFinales = preciosLibres.map { it * 1.16 }
    println(preciosFinales)
```

[`Atrás`](../Ejemplo-02) | [`Siguiente`](../Reto-02)




