# IDDFS

[Transparencias - Búsqueda ciega.pdf](./Búsqueda%20Ciega.pdf)

#### Wikipedia

[Iterative deepening depth-first search - Wikipedia](https://en.wikipedia.org/wiki/Iterative_deepening_depth-first_search)

## Propiedades

- Vas aumentando el límite de profundidad de manera dinámica.
- Cada iteración (cuando aumentas la profundidad límite) vuelve a iterar por todos los nodos anteriores ya que comparado con el último nivel expandido, es negligible.
- Complejidad temporal (imita un BFS):

<p align="center">
    <a href="https://github.com/MrRobb/IA-FIB">
        <img src="http://latex2png.com/output//latex_3999d74d104ca6b710a7ac3264f88b5e.png" width=35%>
    </a>
</p>

- Complejidad espacial (con el espacio de un DFS):

<p align="center">
    <a href="https://github.com/MrRobb/IA-FIB">
        <img src="http://latex2png.com/output//latex_55cc3151b73185158270706e9b3c790c.png" width=30%>
    </a>
</p>

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
