# Hill Climbing

Sep 27, 2018

[Búsqueda local.pdf](Busquedalocal-a229d311-a389-4c7b-94cc-324ed147f11b.pdf)

- [x]  Apuntes al día
- [x]  Tema terminado



# Tipos



- Escalada simple → saltamos a cualquier solución mejor que la actual.
- Escalada máxima pendiente (steepest-ascent hill climbing, gradient search) → se escoge la solución con la mejor pendiente.

# Propiedades



- Solo explora descendientes mejores.
- No usa backtracking.
- Es determinístico, si se repite con la misma solución inicial da el mismo resultado.

## Talones de Aquiles

- Máximos locales
- Meseta (todos los vecinos son iguales)
- Cresta (la pendiente de la función sube y baja)

## Soluciones

- Random Restarting Hill Climbing (reiniciar la búsqueda con una solución inicial diferente)
- Beam Search (hacer backtracking)
- Simulated Annealing (aplicar más de un paso antes de moverse (dame mis sucesores y dame los sucesores de mis sucesores))
- Hill Climbing en paralelo (lo divides en sectores)

# Código


```cpp
    bool isWorse(Sol n1, Sol n2); // devuelve si n1 es peor que n2
    
    Sol actual = getInicial();
    bool end = false;
    
    while (!end) {
    	auto children = getChildren(actual);
    	children = sort(children.begin(), children.end(), isWorse);
    	children = eliminaPeoresQueActual(children);
    	
    	if (children.empty()) {
    		end = true;
    	}
    	else {
    		actual = getBest(children);
    	}
    }
