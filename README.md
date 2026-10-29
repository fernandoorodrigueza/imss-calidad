# IMSS: estado de conservación

Página estática para GitHub Pages. Lee `datos.xlsx` y construye:
- tarjetas grandes para Equipo, Instalaciones e Inmueble;
- gráficas circulares tipo dona para bueno/malo/regular;
- barras apiladas para comparar 2022 y 2023;
- selector de nivel de atención;
- carga de Excel para vista previa local y detección básica de inconsistencias.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub, por ejemplo `imss-calidad`.
2. Sube `index.html` y `datos.xlsx` a la raíz del repositorio.
3. En **Settings → Pages**, selecciona **Deploy from a branch**, rama `main` y carpeta `/(root)`. Guarda.
4. Espera a que GitHub publique el sitio y abre la URL que te indique.

## Actualizar los datos

La página busca `datos.xlsx` junto a `index.html`. Para actualizar el sitio público:
1. Actualiza el Excel manteniendo la estructura de columnas y filas.
2. En el repositorio de GitHub, abre `datos.xlsx` y reemplázalo por la versión nueva (Add file → Upload files también sirve).
3. Confirma el cambio. GitHub Pages servirá los nuevos datos al volver a cargar la página.

El botón **Cargar Excel** sirve para probar un archivo en tu navegador; no sube el archivo a GitHub ni modifica el sitio público. Para publicar una actualización hay que reemplazar `datos.xlsx` en el repositorio, o automatizar esa subida con un flujo autenticado.

## Estructura esperada del Excel

Se espera la estructura del archivo original:
- columna A: nombre del nivel (por ejemplo, `1er nivel`, `2o nivel`, `3er nivel`);
- columna C: año (2022 o 2023);
- columna D: categoría (`equipo`, `instalaciones`, `inmueble`);
- columnas E, F y G: porcentajes `bueno`, `malo`, `regular`.

No cambies la posición de estas columnas sin adaptar el código. El archivo de ejemplo tiene 6 columnas visibles en Excel, pero el parser espera las categorías y porcentajes en sus columnas originales: revisa que el encabezado y los valores no se hayan movido al editar.

## Nota de validación

El archivo original contiene al menos un valor que parece inconsistente: para `2o nivel`, `instalaciones`, año 2023, `regular` figura como `103`, lo que produce un porcentaje fuera de rango y una suma que no cuadra. La página lo señala automáticamente; **no lo corrige por su cuenta**. Verifica el informe fuente antes de publicar ese dato.
