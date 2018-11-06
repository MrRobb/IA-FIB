# BFS

[Transparencias - Búsqueda ciega.pdf](./Búsqueda%20Ciega.pdf)

[Breadth-first search - Wikipedia](https://en.wikipedia.org/wiki/Breadth-first_search)

## Propiedades
 
- **Se usa una cola**
- Es completo
- Complejidad temporal y espacial:

<p align="center">
	<a href="https://github.com/MrRobb/Artificial-Intelligence">
		<img src="http://latex2png.com/output//latex_3999d74d104ca6b710a7ac3264f88b5e.png" width=35%>
	</a>
</p>

- Optimalidad: Encuentra el estado solución que está más cerca de la raiz. Por lo tanto, si usar menos operadores significa que la solución es más óptima, entonces se podría considerar óptimo.

## Algoritmo (c++)

```cpp
void Graph::BFS(int s)
{
	// Mark all the vertices as not visited
	bool *visited = new bool[V];
	for(int i = 0; i < V; i++)
	visited[i] = false;

	// Create a queue for BFS
	list<int> queue;

	// Mark the current node as visited and enqueue it
	visited[s] = true;
	queue.push_back(s);

	// 'i' will be used to get all adjacent
	// vertices of a vertex
	list<int>::iterator i;

	while(!queue.empty())
	{
		// Dequeue a vertex from queue and print it
		s = queue.front();
		cout << s << " ";
		queue.pop_front();

		// Get all adjacent vertices of the dequeued
		// vertex s. If a adjacent has not been visited,  
		// then mark it visited and enqueue it
		for (i = adj[s].begin(); i != adj[s].end(); ++i)
		{
			if (!visited[*i])
			{
				visited[*i] = true;
				queue.push_back(*i);
			}
		}
	}
}
```
