Clase de datos del paquete biobase de bioconductor. Sirve para trabajar con datos ómicos(de microarrays de expresión) y que esta información vaya asociada directamente con metadatos de las muestras analizadas y los genes, o incluso del propio experimento. 
![[Pasted image 20250326113716.png]]
- assayData: se accede con `exprs()`, e incluye los datos de expresión de los genes analizados en cada muestra. 
- phenoData: datos de las muestras, se accede con `pData(phenoData())`. 
- featureData: datos de las variables o genes, se accede con `featureData().` 
- experiment Data: contiene datos MIAME del experimento. 