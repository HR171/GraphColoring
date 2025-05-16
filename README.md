# Graph Coloring Solver

Este repositorio contiene una implementación en Python de varios métodos heurísticos y exactos para resolver el **Graph Coloring Problem** sobre instancias en formato DIMACS.

---

## 📂 Estructura del repositorio

```plaintext
/ (raíz)
│
├── DIMACS/            # Instancias .col en formato DIMACS
├── main.py               # Script principal que ejecuta los algoritmos
├── requirements.txt      # Dependencias de Python
├── README.md             # Este archivo
```

---

## 📝 Descripción

La tarea de *graph coloring* consiste en asignar colores a los vértices de un grafo de modo que no haya dos vértices adyacentes con el mismo color, minimizando el número total de colores.

Esta implementación incluye:

* **Greedy Coloring**: heurística constructiva ordenando vértices por grado descendente.
* **Local Search (First Improvement)**: refinamiento de la solución inicial buscando el primer vecino que reduzca el número de colores.
* **Backtracking con poda y timeout**: exploración exacta limitada por un tiempo máximo, con técnicas de poda y forward‑checking.

---

## 🛠️ Requisitos

* Python 3.8 o superior

Instale las dependencias con:

```bash
pip install -r requirements.txt
```

El fichero `requirements.txt` debe contener al menos:

```txt
networkx
```

---

## 🚀 Uso

Ejecute el script principal estando dentro de la ruta donde está la carpeta de las instancias y el codigo main.py:

*En la consola se mostrarán por cada instancia:*

* Resultado de Greedy, Local y Backtracking (si aplica).
* Número de colores usado y tiempo de ejecución.
* Validación de solución (si es factible).

---

## 🎯 Formato de instancias

Las instancias deben cumplir el formato DIMACS (.col):

```txt
c Comentarios (líneas que empiezan con `c`)
 p edge N M        # N vértices, M aristas (métricas dirigidas)
 e u v             # cada línea define una arista entre u y v
```

*Nx.Graph* de NetworkX ignora duplicados, por lo que puede listarse cada `e u v` en ambas direcciones.

---

## 📈 Ejemplos de resultados

| Instancia     | Greedy (colores) | Local (colores) | Backtracking | Óptimo conocido |
| ------------- | ---------------- | --------------- | ------------ | --------------- |
| david.col     | 11               | 11              | Skipped      | 11              |
| queen6\_6.col | 9                | 9               | 7            | 7               |
| le450\_5a.col | 11               | 11              | Skipped      | 5               |


---

## 📚 Referencias

* DIMACS Challenge Graph Coloring: [http://dimacs.rutgers.edu/Challenges/](http://dimacs.rutgers.edu/Challenges/)
* Trick, M. *Graph Coloring Instances*, CMU: [https://mat.tepper.cmu.edu/COLOR/instances.html](https://mat.tepper.cmu.edu/COLOR/instances.html)

---

> **Autor:** Equipo 1 Grupo 006 Horario Jueves N1-N3
> **Universidad Autónoma de Nuevo León — FIME**
> **Proyecto**: Temas Selectos de Optimización (Semetre Enero Junio 2025)

---
