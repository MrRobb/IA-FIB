# IDA*

Sep 20, 2018

[Búsqueda heurística.pdf](Busquedaheuristica-0e2124fb-1fab-46f6-b716-6f7dc15d70f2.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado



[Iterative deepening A* - Wikipedia](https://en.wikipedia.org/wiki/Iterative_deepening_A*)

# Propiedades



- Para reducir memoria voy aumentando la profundidad = f().
- **Poda según la función f()** (aka. profundidad) no sobre los niveles. Por lo tanto, voy haciendo un DFS podando según la función f()
- Voy bajando hasta que la f() supera la profundidad límite explicitada. En ese momento, cambio de rama.

# Código



    double h(Node n);    // devuelve la distancia hasta la solución
    double g(Node n);    // devuelve el coste el coste del camino recorrido
    double f(Node n);    // f() = g() + h()
    
    void IDAstar(Problem probl, Node initial, int limit) {
    
    	// Initial depth
    	auto actual = initial;
    	auto depth = f(initial);
    	
    	while (!isGoal(actual) && depth < limit) {
    		// Initialize
    		auto opened_nodes = getOpened();
    		auto closed_nodes = getClosed();
    
    		// Initial node
    		opened_nodes.insert(initial);
    		actual = opened_nodes.first();
    
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
    
    		depth++;
    	}	
    }