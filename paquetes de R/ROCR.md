#machinelearning #evaluación 

Utiliza objetos de tipo predicción, que se crean con dos argumentos:

- Los valores reales de cada observación. 
- La probabilidad estimada de la clase positiva. 


```
pred <- prediction(predictions = probabilidad de las clases, labels = valores reales para cada observación)
```

Este objeto puede ser examinado con funciones del paquete. Por ejemplo, para crear una curva ROC:

```
perf <- performance(pred, measure = "tpr", x.measure="fpr")
plot(perf, main = "ROC curve for SMS spam filter", col = "blue", lwd = 3)
abline(a=0,b=1,lwd=2,lty=2)
```

Que daría lugar a: 
![[Pasted image 20250314131656.png]]

Para calcular el AUC, sería:

```
perf.auc <- performance(pred, measure = "auc")
str(perf.auc)
unlist(perf.auc@y.values) 
```

Se hace unlist porque es un objeto de tipo S4, y str para ver los slots del objeto. 