https://github.com/Electrostatics/apbs/tree/main/tools




## 🧬 Documentación de comandos PyMOL – Visualización de Superficie Electrostática

Antes cargar el pdb de la proteìna

### 🔹 **1. Cargar la proteína y el mapa de potencial electrostático**

```python
load /home/brigitte/Descargas/p99ocut1nc.pqr, protein
load /home/brigitte/Descargas/p99ocut1nc.pqr.dx, electro_map
```

* `protein`: nombre del objeto de la proteína.
* `electro_map`: nombre del mapa electrostático generado por APBS.

---

### 🔹 **2. Mostrar la superficie de la proteína**

```python
show surface, protein
```

---

### 🔹 **3. Ajustar transparencia para visualizar el mapa superpuesto**

```python
set transparency, 0.3, protein
```

---

### 🔹 **4. Crear isosuperficies para visualizar regiones con potencial definido**

```python
isomesh mesh_pos, electro_map, level=1.0
isomesh mesh_neg, electro_map, level=-1.0
```

* Estas superficies representan regiones con potencial +1.0 y -1.0 kT/e respectivamente.

---

### 🔹 **5. Colorear las superficies según el signo del potencial**

```python
color blue, mesh_pos
color red, mesh_neg
```

* Azul para cargas positivas.
* Rojo para cargas negativas.

---

### 🔹 **6. Exportar una imagen de la escena**

```python
png surface1.png
```

* Guarda una imagen PNG de la visualización actual.

---

### 🔹 **7. Extra: Visualización de otras estructuras (PDB)**

```python
fetch 1i5z
fetch 3hif
align 3hif, ecoli-linker, cycles=0
```

* `fetch` descarga estructuras del PDB.
* `align` alinea dos estructuras.
* `select`, `wizard measurement` y otros comandos fueron usados para selección de residuos y mediciones.

---

