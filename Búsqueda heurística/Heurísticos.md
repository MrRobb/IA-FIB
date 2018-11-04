# Heurísticos

---

# Admisibilidad

---

- Se puede garantizar la **optimalidad** del algoritmo.
- Si el heurístico h(n) no es admisible, no tiene sentido utilizar A*.

$$\forall n : \ 0 \leq h(n) \leq h^*(n)$$

# Comparar 2 heurísticos

---

Para saber si un heurístico está **más informado** que otro, se debe cumplir que:

$$\forall n\ |\ 0 \le h2(n) \lt h1(n) \le h^*(n)$$

# Consistencia

---

- Se puede garantizar que el algoritmo **nunca reabrirá los nodos** cerrados ya que escogerá directamente la solución óptima. Y por tanto, no es necesario guardarlos.
- Le pide al heurístico que cumpla la **desigualdad triangular**. Que se comporte como una "distancia". Que ir directo, sea más rápido que ir por más nodos.
- Cuando el heurístico es consistente, la función **f() nunca decrece**.

$$h(x) ≤ c(x, y) + h(y)\ |\ for\ every\ edge (x, y)$$

![](https://upload.wikimedia.org/wikipedia/commons/2/2b/Heuristics_Comparison.png)