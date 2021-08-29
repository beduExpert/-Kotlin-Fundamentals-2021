 	
## Operaciones funcionales

### OBJETIVO 

- Utilizar funciones de orden superior implementadas en estructuras de datos de Kotlin.
- Poner en práctica principios de programación funcional básica.

#### REQUISITOS 

1. Haber cursado el [Ejemplo 3](../Ejemplo-03)

#### DESARROLLO

La recursión es un concepto muy importante en programación especialmente cuando se habla de programación funcional, consiste en definir una función en términos de si misma mediante una llamada a ella dentro de su mismo cuerpo. 

Un ejemplo clásico de funciones recursivas es la función `factorial` que recibe un número natural y se define como sigue

```
factorial 0 = 1
factorial n = n * (factorial n - 1)
```

1. Define la función factorial en Kotlin.
2. Usando `map` define una lista que contenga los factoriales de los números del 0 al 15.
3. A partir de la lista obtenida en el inciso anterior, construye dos listas una con los factoriales múltiplos de 3 y otra con los que no lo son.

[`Atrás`](../Ejemplo-02) | [`Siguiente`](../Readme.md)