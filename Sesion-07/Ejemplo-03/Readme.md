## Casts

### OBJETIVO

- Utilizar los distintos tipos de modificación de tipo de datos de un valor en kotlin 
- Lidiar con los errores en el casting

#### REQUISITOS

1. Haber leído los ejercicios 1 y 2 de esta unidad

#### DESARROLLO

### Smart Casts y operador is

El operador ***is*** permite saber si una variable tiene un tipo de dato asignado o no.

```kotlin
    if (obj !is String) { 
        println("Not es una String")
    }
```

Ahora, creamos una funcion que arroje un resultado numérico con base en su tipo de dato:

```kotlin
fun imprimirNumerico(x: Any) {
    when (x) {
        is Int -> println(x + 1)
        is String -> println(x.length + 1)
        is Boolean -> if(x) println(1) else println(0)
    }
}
```

Para probar el código utilizamos: 

```kotlin
imprimirNumerico(20)
imprimirNumerico("Bedu")
imprimirNumerico(true)
```

Si observamos el código anterior, x es cualquier tipo de valor, pero en el when siempre regresamos un valor entero. En los 3 casos se toma la variable x con un tipo propio, no como su tipo predefinido Any, esto se debe a que el operador is hace un casting automático, por eso lo llaman Smart Cast. Estos smart casts tienen sus limitaciones, pero es bastante util.

### Unsafe Cast

Si queremos hacer un cast de un objeto Any nullable con valor nulo a un String, nos dará error porque null no puede ser convertido a una cadena de texto


```kotlin
val obj2: Any? = null
val str: String = obj2 as String  
```

esto nos traerá el siguiente error:

> Exception in thread "main" kotlin.TypeCastException: null cannot be cast to non-null type kotlin.String

### Safe cast

A diferencia del anterior, si se quiere castear un valor nulo, podemos utilizar un safe cast para que en todo caso, a nuestra variable se le asigne un valor nulo:

```kotlin
val str: String? = obj2 as? String
println(str)
```

[`Atrás`](../Reto-02) | [`Siguiente`](../Readme.md)



