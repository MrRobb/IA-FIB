# Branch and bound

Sep 17, 2018

[Búsqueda heurística.pdf](Busquedaheuristica-0e2124fb-1fab-46f6-b716-6f7dc15d70f2.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado



[Branch and bound - Wikipedia](https://en.wikipedia.org/wiki/Branch_and_bound)

# Propiedades



- Usa el heurístico de coste: función g() → suma de costes por moverse hacia un nodo.
- Cada operador (debería tener) un coste diferente, coste > 0
- Así puede "ordenar" la exploración según el coste y deshacerse de aquellas soluciones que implican un coste mayor que el límite permitido (ejemplo: se acabaría la batería)

# Código (pseudo c++, sí, me lo acabo de inventar)



    double g(Node n);    // devuelve el coste el coste del camino recorrido
    
    // No confundir con Bed & Breakfast
    void BnB(Problem probl, Node initial, Bound bound) {
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
        
        		// sort by g() and exclude solutions that exceed the bound
        		openned_nodes.insert(children);
        
        		// next -> opened
        		actual = openned_nodes.first();
        
        	}
        }