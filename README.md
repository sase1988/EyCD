# EyCD

------

## Documentación de las operaciones realizadas

### Fuente de datos
Partimos de la fuente de datos del Entregable 1 que está en este link del repositorio, donde hicimos una limpieza previa de la base de datos (eliminamos outliers, realizamos algunas imputaciones simples y excluimos ciertas columnas):
'https://github.com/sase1988/EyCD/raw/main/melb_df_clean.csv'

### Encoding
Utilizamos _DictVetorizer_ para codificar las variables categóricas, resultando una matriz llamada *feature_matrix* de 13531 filas por 379 columnas.

### Imputación de las variables YearBuild y BuildingArea







