# Oct 22, 2018

# Satisfacción de restricciones

1. Listar las restricciones:
    1. IMPORTANTE: Hay restricciones que no salen en el texto. Aquellas que son de sentido común (restricciones explícitas e implícitas (del dominio))
        1. Ejemplo: Todo avión necesita un piloto y copiloto
        2. Regla para cuando solo existe uno: si existe en uno y existe en otro, uno y otro son el mismo.
2. Hacer la representación del estado
    1. Todas las variables tienen que tener como mínimo 1 valor (porque sino el algoritmo no hace nada ya que para cuando le asigna un valor a cada variable)
    2. Puedo representar TODAS las restricciones
    3. No hay restricciones reflexivas
3. Hacer las relaciones binarias entre los nodos
    1. Comprobar que no hay reflexivas, si hay, volver a hacer la representación

# Restricciones n-arias

Son restricciones que se aplican a más de 2 nodos. Como por ejemplo un sumatorio.