# EyCD

------

## Documentación de las operaciones realizadas

### Fuente de datos
Partimos de la fuente de datos del Entregable 1 que está en este link del repositorio, donde hicimos una limpieza previa de la base de datos (eliminamos outliers, realizamos algunas imputaciones simples y excluimos ciertas columnas):
'https://github.com/sase1988/EyCD/raw/main/melb_df_clean.csv'

### Encoding
Utilizamos _DictVetorizer_ para codificar las variables categóricas, resultando una matriz llamada **feature_matrix** de 13531 filas por 379 columnas.

### Imputación de las variables YearBuilt y BuildingArea

#### Procedimiento de imputación 1 (el que se ofrecia como ejemplo en la Notebook):

- Columnas base de imputación: YearBuild, BuildingArea
- Método de imputación: IterativeImputer, estimador: KNeighborsRegressor 
- Matriz de entrada: melb_data_mice (sin encoder y sin scaler)
- DataFrame Resultante: _melb_data_mice_


Distribución obtenida: no se asemeja a la distribución original.Utilizar solo las dos columnas para la imputación por KNN no es efectivo:

![image](https://user-images.githubusercontent.com/36776334/123524824-25f8ae80-d6a3-11eb-8f00-8534a9312f91.png)
![image](https://user-images.githubusercontent.com/36776334/123524827-298c3580-d6a3-11eb-9542-03f7caf76fff.png)

#### Procedimiento de imputación 2:

Escalado de variables: Para imputar por KNN es necesario escalar los valores. Esto debería haberse hecho incluso en el caso del procedimiento 1, pero aún asi los resultados con ese método no habrian variado porque el problema es la cantidad de columnas que se usan. En este caso, vamos a usar todas las columnas de **feature_matrix** para la imputación, con lo cual el escalado es fundamental.

- Metodo de ecalado:  MinMaxScaler()
- Matriz Escalada: _scaled_
- Columnas base de imputación: todas
- Método de imputación: IterativeImputer, estimador: KNeighborsRegressor (Vecinos cercanos: 5)- 
- Matriz de entrada: scaled
- Matriz de salida: scaled_mice

Se re-escalan las variables YearBuilt y BuildingArea su rango original para graficar su distribución:

![image](https://user-images.githubusercontent.com/36776334/123525142-124e4780-d6a5-11eb-889e-43042a3d62ab.png)
![image](https://user-images.githubusercontent.com/36776334/123525148-1712fb80-d6a5-11eb-934e-c20873f99b82.png)





