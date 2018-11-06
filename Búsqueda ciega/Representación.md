# Representación

Sep 10, 2018

[Búsqueda ciega.pdf](Busquedaciega-05fdf8d5-b7ab-4e34-85bd-ac76532ddd78.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado



# Resolución de problemas



Para resolver un problema necesitamos 2 cosas:

- Representación del problema
- Estrategia (algoritmos) para abordarlo

# Representación del estado



## Tipos de representación

Hay varios tipos de representaciones de problemas:

- Como un **espacio de estados**: El problema se divide en un conjunto de pasos hacia la resolución.
- Como una **jerarquía de subproblemas**: El problema se puede descomponer en subproblemas.

## Elementos:

![](Busquedadiagrama-8df5c4b5-876b-4470-8421-32fb35a3b535.png)

**Estado inicial:** conjunto de **características iniciales** del problema.

**Estado objetivo:** conjunto de **condiciones que se deben cumplir** para resolver el problema.

**Operadores:** Son el conjunto de acciones que tenemos disponibles en un estado para pasar a otro. Definen la accesibilidad de un estado a otro. Es decir, **nos permiten saltar de un estado a otro, transformarlo.**

## Objetivos:

> Nuestro trabajo es decidir qué partes del problema son relevantes para la resolución del problema, y cómo guardarlas. (si no se guardan solo las partes relevantes, la capacidad de la memoria afectará a la resolución)

> También debemos decidir qué acciones podemos realizar en cada estado intentando minimizar la ramificación del grafo de estados.

> En resumen, cuanto menos guardemos en la representación, mejor. Y cuantas menos acciones tengamos, mejor. Siempre y cuando, nuestra solución se encuentre dentro de estos espacios.

# Solución



## Tipos

- Secuencia de pasos para llegar al estado final
- Estado final en si

## ¿Cuál quiero?

- Una
- La mejor (normalmente, difícil de computar)
- Todas

## Extras

- Coste (depende del problema es relevante o no)

# Descripción de un problema



- Descripción del **espacio** de estados → qué se guarda
- Estado **inicial**
- Estado **final** (o condiciones que cumple)
- **Operadores** de cambio → condiciones para poderse aplicar + función de transformación
- Especificar el tipo de **solución** → path vs. estado final + una vs. todas vs. best