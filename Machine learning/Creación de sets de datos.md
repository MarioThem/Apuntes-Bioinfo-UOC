Para validar correctamente un modelo de ML, es necesario enfrentarlo a datos que no ha "visto" nunca. Para ello, existen distintos métodos:

# Método holdout

Es el procedimiento de dividir los datos en sets de entrenamiento y sets de prueba. El set de entrenamiento se usa normalmente para generar el modelo, y el set de prueba para validarlo. En general, se usa 1/3 de los datos para prueba y 2/3 para el entrenamiento, y los datos son asignados al azar entre ambos sets. 

Sin embargo, es mejor aun crear un tercer set, el set de validación, que asegura que no escojamos simplemente el modelo que mejor funcione para el set de entrenamiento, si no el que mejor funcione en general. 

![[Pasted image 20250318104237.png]]

Sin embargo, si una clase es minoritaria en los datos, esta puede estar más presente en un set u otro. Por ello, se usa el muestreo aleatorio estratificado. 

![[Pasted image 20250318104532.png]]

Esto se puede hacer en R mediante la función `createDataPartition()` del paquete [[caret]].

# Validación cruzada

Para que los sets de datos sean aún más representativos, se usa este método. 
Se dividen los datos en k particiones(normalmente 10) llamadas folds. Estos serían 10 sets de validación que consistirian en el 10% de los datos cada uno. Los otros sets de 90% serían los usados 10 veces para el entrenamiento y la prueba. Las métricas de rendimiento se aplican como las medias de las métricas del modelo para cada uno de estos folds. El gold standard sería realizar este proceso repetidas veces (repited k-fold CV). 
Los folds se pueden crear con la función `createFolds()` del paquete  [[caret]]
![[Pasted image 20250318111543.png]]

# Muestreo bootstrap

Consiste en generar particiones mediante muestreo al azar con reemplazamiento, de tal forma que se puede generar la misma partición varias veces. Estas particiones se usan para el entrenamiento, y el set de prueba se selecciona de las particiones no utilizadas. Esto utiliza menos datos para entrenar(ya que la probabilidad de que un ejemplo se incluya al azar es del 63,2 %), pero es más util para sets de datos pequeños, donde no hay tantos datos como para poder dividirlos bien como hace la validación cruzada. Se hace mediante la función `createRsample()` del paquete [[caret]]

![[Pasted image 20250318111634.png]]
