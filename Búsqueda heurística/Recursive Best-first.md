# Recursive Best-first

Sep 20, 2018

[Búsqueda heurística.pdf](Busquedaheuristica-0e2124fb-1fab-46f6-b716-6f7dc15d70f2.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado

---

[Best-first search - Wikipedia](https://en.wikipedia.org/wiki/Best-first_search)

![](Screenshot2018-10-07at00-af8e3a7b-5691-46ae-ba6d-abdffa03daed.53.15.png)

# Propiedades

---

- Permite que el coste espacial se mantenga lineal al no tener que guardar mas que los nodos que pertenecen al camino actual y sus hermanos en cada nivel.
- Usa la función heurística h()
- Cuando hace una llamada recursiva (cuando baja de nivel) se guarda la segunda mejor opción.
- Cuando vuelve arriba, actualiza el valor del nodo según los valores de la h() de sus descendientes.

# Código

---

    double h(Node n);    // devuelve la distancia hasta la solución
    
    void RBF(Node actual, float coste_alt, float& coste_new, Solut& solution) {
    	if (isGoal(actual)) {
    		solution.insert(actual);
    	}
    	else {
    		auto children = getSuccessors(actual);
    		if (children.IsEmpty()) {
    			coste_new = INFINITY;
    			solution.vacia();
    		}
    		else {
    			bool end = false;
    			while (!end) {
    				auto best = children.getBest();
    				if (best.coste() > coste_alt) {
    					end = true;
    					solution.vacia();
    					coste_new = coste_alt;
    				}
    				else {
    					auto best2 = children.getBest2();
    					RBF(best, min(best2.coste(), coste_alt), coste_new, solution);
    					if (solution.IsVacia()) {
    						best.setCoste(coste_new);
    					}
    					else {
    						solution.insert(best);
    						end = true;
    					}
    				}
    			}
    		}
    	}
    }