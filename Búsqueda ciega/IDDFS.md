# IDDFS

[Transparencias - Búsqueda ciega.pdf](./Búsqueda%20Ciega.pdf)

#### Wikipedia

[Iterative deepening depth-first search - Wikipedia](https://en.wikipedia.org/wiki/Iterative_deepening_depth-first_search)

## Propiedades

- Vas aumentando el límite de profundidad de manera dinámica.
- Cada iteración (cuando aumentas la profundidad límite) vuelve a iterar por todos los nodos anteriores ya que comparado con el último nivel expandido, es negligible.
- Complejidad temporal (imita un BFS):

$$O({ramificacion}^{profundidad})$$

- Complejidad espacial (con el espacio de un DFS):

$$O(distance_{to\ solution})$$

- Optimalidad: Sí. Encuentra el camino más corto.

## Código (C++)

```cpp
bool Graph::DLS(int src, int target, int limit)
{
    if (src == target)
        return true;

    // If reached the maximum depth, stop recursing.
    if (limit <= 0)
        return false;

    // Recur for all the vertices adjacent to source vertex
    for (auto i = adj[src].begin(); i != adj[src].end(); ++i)
       if (DLS(*i, target, limit-1) == true)
          return true;

     return false;
}

// IDDFS to search if target is reachable from v.
// It uses recursive DFSUtil().
bool Graph::IDDFS(int src, int target, int max_depth)
{
    // Repeatedly depth-limit search till the
    // maximum depth.
    for (int i = 0; i <= max_depth; i++)
       if (DLS(src, target, i) == true)
          return true;

    return false;
}
```
