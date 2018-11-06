# DFS

[Transparencias - Búsqueda ciega.pdf](./Búsqueda%20Ciega.pdf)

#### Wikipedia

[Depth-first search - Wikipedia](https://en.wikipedia.org/wiki/Depth-first_search)

## Propiedades

- **Se usa una pila**
- Es completo solamente si existe un límite de profundidad y existe una solución dentro de ese límite.
- Complejidad temporal (en caso de que no haya repeticiones):

<p align="center">
    <a href="https://github.com/MrRobb/Artificial-Intelligence">
        <img src="http://latex2png.com/output//latex_4d1f61e1a99e07a737bd98c88d97ff0b.png" width=15%>
    </a>
</p>

- Complejidad espacial:

<p align="center">
    <a href="https://github.com/MrRobb/Artificial-Intelligence">
        <img src="http://latex2png.com/output//latex_6188448ce1a84f11c7af1bb372ab58df.png" width=7%>
    </a>
</p>

- Optimalidad: Si definimos óptimo como encontrar el camino más corto de un estado a otro, DFS no es óptimo.

## Código (C++)

```cpp
void Graph::DFSUtil(int v, bool visited[])
{
    // Mark the current node as visited and
    // print it
    visited[v] = true;
    cout << v << " ";

    // Recur for all the vertices adjacent
    // to this vertex
    list<int>::iterator i;
    for (i = adj[v].begin(); i != adj[v].end(); ++i)
        if (!visited[*i])
            DFSUtil(*i, visited);
}

// DFS traversal of the vertices reachable from v.
// It uses recursive DFSUtil()
void Graph::DFS(int v)
{
    // Mark all the vertices as not visited
    bool *visited = new bool[V];
    for (int i = 0; i < V; i++)
        visited[i] = false;

    // Call the recursive helper function
    // to print DFS traversal
    DFSUtil(v, visited);
}
```
