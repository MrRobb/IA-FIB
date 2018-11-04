# Oct 01, 2018

> Siempre, independientemente del algoritmo, todos los sucesores deberían tener la misma probabilidad de ser generados (no escogidos).

# Simulated Annealing

> No saldrá en el examen ya que al ser probabilístico es más difícil de evaluar qué solución es mejor, dada su naturaleza estocástica.

- Si le añades aliaciones de otros materiales al cristal, este cristal puede obtener propiedades carasterísticas de estos metales.
- Inspirado en esta propiedad, el simulated annealing hace una búsqueda estocástica.
- Tenemos una función de energía que a temperaturas muy altas, la distancia entre las soluciones sea mucha, y a medida que va bajando la temperatura, las soluciones se encuentran más cerca y acaba funcionando como un Hill-Climbing, encontrando una solución local.
- A la hora de escoger uno de los operadores para aplicar al único sucesor de la iteración, tienes que tener en cuenta el número máximo de sucesores que puede generar cada operador, ya que aquellos operadores con más sucesores, van a tener menos probabilidades de ser escogidos. Por lo tanto:

$$P_{operador} = N_{operador}/N_{max}$$

## Parámetros

- Temperatura → parámetro de control
- Energía f(n) → indica la calidad de la solución.
- Función de aceptación → Permite decidir si escoger un nodo sucesor. Es una función probabilística tal que la probabilidad de elegir un sucesor está relacionada con la temperatura.
- Estrategia de enfriamiento → nº de iteraciones a realizar, cómo bajar la temperatura, y cuántos sucesores explorar por cada paso de temperatura.

    // (...)

Se puede imaginar como sacudir un terreno (función de evaluación) e ir bajando la fuerza de sacudida hasta que la solución se estabiliza.