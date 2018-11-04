# A*

Sep 17, 2018

[Búsqueda heurística.pdf](Busquedaheuristica-0e2124fb-1fab-46f6-b716-6f7dc15d70f2.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado

---

[A* search algorithm - Wikipedia](https://en.wikipedia.org/wiki/A*_search_algorithm)

![](https://upload.wikimedia.org/wikipedia/commons/8/85/Weighted_A_star_with_eps_5.gif)

# Propiedades

---

$$f(n) = g(n) + h(n)$$

- Intenta minimizar el coste y minimizar la distancia hacia la solución.
- A* no sabe g* (el coste exacto) porque aunque llegue a un nodo, no sabe si en el futuro podrá llegar al mismo nodo con un g menor.
- En caso de empate se debería escoger la menor h() ya que se supone que está más cerca de la solución.

# Código

---

    double h(Node n);    // devuelve la distancia hasta la solución
    double g(Node n);    // devuelve el coste el coste del camino recorrido
    double f(Node n);    // f() = g() + h()
    
    void Astar(Problem probl, Node initial) {
    	// Initialize
    	auto opened_nodes = getOpened();
    	auto closed_nodes = getClosed();
    	
    	// Initial node
    	opened_nodes.insert(initial);
    	auto actual = opened_nodes.first();
    	
    	// Traverse nodes
    	while (!isGoal(actual) && !opened_nodes.empty()) {
    
    		// opened -> closed
    		opened_nodes.popFirst();
    		closed_nodes.insert(actual);
    
    		// generate successors
    		auto children = getSuccessors(actual);
    		children = treatRepeated(children, opened_nodes, closed);
    
    		// sort by f()
    		openned_nodes.insert(children);
    
    		// next -> opened
    		actual = openned_nodes.first();
    
    	}
    }