# Greedy Best First

Sep 17, 2018

[Búsqueda heurística.pdf](Busquedaheuristica-0e2124fb-1fab-46f6-b716-6f7dc15d70f2.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado



[Is Greedy best-first search different from Best-first search?](https://stackoverflow.com/questions/8374308/is-greedy-best-first-search-different-from-best-first-search)

[Best-first search - Wikipedia](https://en.wikipedia.org/wiki/Best-first_search#Greedy_BFS)

# Propiedades



- Usa el heurístico que estima la distancia a la solución: función h() → distancia desde el punto actual hasta la solución.
- Por lo tanto, ordena la exploración según aquel camino que según el heurístico, está más cerca de la solución.
- El heurístico es posible que evite volver hacia atrás (expandir un nodo repetido) ya que el *greedy* siempre va a mejor o igual, si todas las soluciones son peores que la actual, el algoritmo se para.
- Cuando la puntuación es igual, dependiendo de si hemos activado el tratamiento de repetidos, se expande o no.

# Código



    double h(Node n);    // devuelve la distancia hasta la solución
    
    void GreedySearch(Problem probl, Node initial) {
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
    
    		// sort by h()
    		openned_nodes.insert(children);
    
    		// next -> opened
    		actual = openned_nodes.first();
    
    	}
    }