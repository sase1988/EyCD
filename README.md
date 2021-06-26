# EyCD

------

## Documentación de las operaciones realizadas

### Fuente de datos
Partimos de la fuente de datos del Entregable 1 que está en este link del repositorio, donde hicimos una limpieza previa de la base de datos (eliminamos outliers, realizamos algunas imputaciones simples y excluimos ciertas columnas):
'https://github.com/sase1988/EyCD/raw/main/melb_df_clean.csv'

### Encoding
Utilizamos _DictVetorizer_ para codificar las variables categóricas, resultando una matriz llamada *feature_matrix* de 13531 filas por 379 columnas.

### Imputación de las variables YearBuilt y BuildingArea

#### Procedimiento de imputación 1:

- Columnas base de imputación: YearBuild, BuildingArea
- Método de imputación: IterativeImputer, estimador: KNeighborsRegressor 
- Matriz de entrada: melb_data_mice (sin encoder y sin scaler)
- DataFrame Resultante: _melb_data_mice_


Distribución obtenida: no se asemeja a la distribución original.Utilizar solo las dos columnas para la imputación por KNN no es efectivo:

![image](https://user-images.githubusercontent.com/36776334/123524824-25f8ae80-d6a3-11eb-8f00-8534a9312f91.png)
![image](https://user-images.githubusercontent.com/36776334/123524827-298c3580-d6a3-11eb-9542-03f7caf76fff.png)





