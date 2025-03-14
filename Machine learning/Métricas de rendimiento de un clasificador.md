# Probabilidades predichas

Informan sobre lo "seguro" que está el algoritmo de clasificación con el resultado predicho. Se calculan con la función `predict()` con `type = "prob"`  

```
predict(modelo_a_usar, set_de_datos_de_test, type = "prob")
```

Por ejemplo, se puede dar la situación donde el algoritmo no haya hecho una predicción correcta, y sin embargo esté totalmente seguro de su predicción, o que haya hecho una predicción correcta, pero por las probabilidades se vea que el acierto ha sido más fruto del azar que de un buen rendimiento del modelo. 

# Matriz de confusión

<p align="justify">Los aciertos en las predicciones siempre están en la diagonal, sin importar el  número de clases utilizadas. </p>
![[Pasted image 20250314115547.png]]

En el caso de dos clases, tendríamos lo siguiente: 

![[Pasted image 20250314115910.png]]
La matriz de confusión se puede visualizar con la función `CrossTable(`) del paquete [[gmodels]].

Además, con el paquete [[caret]] , se visualizan métricas adicionales.

| Métrica       | Fórmula                                       | Explicación                                                                                                                                                                                      |
| ------------- | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Accuracy      | $\frac{VP + VN}{VP + FP + VN + FN}$           | Grado de acierto del clasificador                                                                                                                                                                |
| Tasa de error | $\frac{FP + FN}{VP + FP + VN + FN}$           | 1 - accuracy                                                                                                                                                                                     |
| Sensibilidad  | $\frac{VP}{VP+FN}$                            | Proporción de positivos clasificados como tales                                                                                                                                                  |
| Especificidad | $\frac{VN}{VN+FP}$                            | Proporción de negativos clasificados como tales                                                                                                                                                  |
| Precisión     | $\frac{VP}{VP+FP}$                            | Grado de detección de los positivos, valor predictivo positivo                                                                                                                                   |
| Recall        | Igual que sensibilidad                        | De todos los positivos, cuantos abarca como positivos                                                                                                                                            |
| F-measure     | $\frac{2*precision*recall}{recall+precision}$ | También llamado F-score, combina precisión y recall usando la media armónica. Produce una manera de comparar varios modelos usando un único número, pero debe ser usado junto con otras métricas |
# Estadístico kappa 
También es bastante útil, ya que compara las predicciones del modelo con la probabilidad de que esas predicciones se hayan dado únicamente por azar (complemento a probabilidades). 
$$
k = \frac{Pr(a) - Pr(e)}{1-Pr(e)}
$$

Donde Pr(a) es la probabilidad de aciertos del modelo, y Pr(e) es la probabilidad de aciertos por azar. 

Pr(e) se calcula: 

![[Pasted image 20250314130442.png]]

Siendo n el número total de observaciones, y los sumandos del numerador coinciden con el número de filas y columnas de la matriz de confusión (en este caso 2x2):

![[Pasted image 20250314130559.png]]

