# IMSS | Estado de conservación

## Archivos
- `index.html`: sitio web y visualizaciones.
- `datos.xlsx`: libro con una hoja por comparativo.

## Publicación
Sube ambos archivos a la raíz del repositorio de GitHub. En Settings → Pages configura Deploy from a branch, `main` y `/(root)`.

## Actualización
Para actualizar los datos, reemplaza `datos.xlsx` en GitHub por el nuevo libro, conservando los nombres de las hojas y la estructura de las tablas. No hay carga de Excel desde la página.

## Estructura de cada hoja
- Columna A: nivel de atención (se puede dejar vacía en filas consecutivas del mismo nivel).
- Columna B: año.
- Columna C: categoría (equipo, instalaciones o inmueble; se puede dejar vacía en la fila consecutiva del mismo rubro).
- Columnas D, E y F: porcentajes bueno, malo y regular.

Cada hoja representa un comparativo y debe contener los datos de los dos años para los tres niveles y las tres categorías. La página detecta los años a partir de los datos y genera los botones con los nombres de las hojas.

Las gráficas circulares muestran el año más reciente de la hoja seleccionada; las barras apiladas muestran ambos años. La leyenda metodológica solicitada aparece debajo de las gráficas.
