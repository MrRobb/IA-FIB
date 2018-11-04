# Oct 11, 2018

# Ejemplo: Algoritmo genético

- No siempre cruzo los genes → entropía inversa
- No siempre un individuo pasa a la siguiente generación (normalmente se descarta la mitad) → entropía

# Representaciones

- p grupos con un ID de contenedor cada uno
    - id puede identificar un contenedor que no exista
    - overflow del contenedor
- c grupos con un paquete cada uno
    - hell no.
- c grupos con p bits cada uno (0 → no asignado, 1 → asignado)
    - 1 paquete en 0 contenedores
    - 1 paquete en +1 de un contenedor
    - overflow del contenedor

# Solución inicial

Es importante añadir un elemento estocástico para que hay la mayor variación posible entre los individuos. Si es posible, intentar que la generación genere siempre soluciones (aunque sean malas).

# Operadores

## Cruce

- Las no-soluciones se "checkean/penalizan" en la función de evaluación.

## Mutación

- La probabilidad de mutación:
    - no debe ser muy alta → te cambiaría las soluciones buenas.
    - no debe ser muy baja → nunca encontraría soluciones fuera del espacio de soluciones con el que puede llegar con las soluciones iniciales.

> Es importante siempre controlar la cantidad de no-soluciones que son capaces de generar los diversos operadores.

# Función de evaluación

- Es importante penalizar las no-soluciones.
