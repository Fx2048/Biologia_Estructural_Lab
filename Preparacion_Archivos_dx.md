
### 1. Prepara tu estructura en formato PDB

Asegúrate de tener el archivo de tu proteína en formato PDB y que esté limpio (sin cadenas innecesarias o átomos no relevantes).

### 2. Configura el archivo de entrada para APBS

Necesitas crear un archivo de entrada para APBS (por ejemplo, `apbs.in`) que defina parámetros como el tamaño de la malla, la concentración de iones, y los métodos de cálculo de la superficie electrostática.

Un ejemplo de archivo de entrada para calcular la superficie electrostática podría verse así:

```text
read
    moleculetype = pdb
    file = /path/to/your/protein.pdb
end

elec
    mg-auto
    dime  65 65 65
    pdie 2.0
    sdie 78.5
    temp 298.0
    ion_conc 0.150
end
```

Aquí debes asegurarte de reemplazar `/path/to/your/protein.pdb` por la ruta correcta de tu archivo PDB.

### 3. Ejecuta APBS

Ejecuta el comando de APBS en la terminal para calcular el potencial electrostático:

```bash
apbs /path/to/your/apbs.in
```

Esto generará un archivo de salida con los resultados, que generalmente está en formato DX.

### 4. Visualiza la superficie electrostática en PyMOL

```

Esto debería mostrarte la superficie electrostática de tu proteína, donde se pueden ver las regiones cargadas positivamente (normalmente en azul) y negativamente (en rojo).
