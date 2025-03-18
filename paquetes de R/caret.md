#machinelearning #evaluación #entrenamiento #mejora
- `confusionMatrix()`: genera la matriz de confusión y algunas medidas adicionales
![[Pasted image 20250314125152.png]]
- `createDataPartition():` genera índices de los datos para crear particiones de los mismos mediante muestreo aleatorio estratificado. 

```
in_train <- createDataPartition(datos$columna, p = proporción de los datos a muestrear, list = TRUE(si queremos que esté en formato lista))
datos_entrenamiento <- datos[in_train, ]
datos_prueba <- datos[-in_train, ]
```
- `createFolds()`: genera folds para validación cruzada, forma de lista de números de columnas.  

```
folds <- createFolds(datos$columna, k = 10)
datos_entrenamiento <- datos[-folds, ]
datos_prueba <- datos[folds, ]
```

Este proceso se repite 10 veces, algo que se puede lograr mediante la función `lapply()` por ejemplo. 

- `createRsample()`: creación de particiones por muestreo bootstrap, por muestreo al azar simple. 