# DFS

Sep 13, 2018

[Búsqueda ciega.pdf](Busquedaciega-05fdf8d5-b7ab-4e34-85bd-ac76532ddd78.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado

---

[Depth-first search - Wikipedia](https://en.wikipedia.org/wiki/Depth-first_search)

# Propiedades

---

- **Se usa una pila**
- Es completo solamente si existe un límite de profundidad y existe una solución dentro de ese límite.
- Complejidad temporal (en caso de que no haya repeticiones):

$$O(n+m)$$

- Complejidad espacial:

$$O(n)$$

- Optimalidad: Si definimos óptimo como encontrar el camino más corto de un estado a otro, DFS no es óptimo.

# Código (c++)

---

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