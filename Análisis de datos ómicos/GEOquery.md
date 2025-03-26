Paquete para descargar datos de experimentos de GEO(Gene Expression Omnibus). Los elementos de GEO están compuestos por una serie de identificadores que se refieren a distintas partes de sus datos: 
![[Pasted image 20250326115325.png]]
- GSExxxx: ID de serie, relaciona varias muestras usadas en el estudio e identifica el estudio en su conjunto. Se accede con `getGEO()`, que arroja una lista de GSE, cada uno con su expressionSet. Se accede al [[ExpressionSet de Biobase]] con la notación [ [ ] ]
- GDSxxxx: ID de Dataset de GEO, colección realizada por GEO de muestras estadísticamente y biologicamente significativas. Se accede con `getGEO()`, que arroja un objeto de clase GDS. `Meta(gds)` sirve para ver los metadatos del objeto. Se puede convertir a un [[ExpressionSet de Biobase]] con la función `GDS2eSet(gds,do.log2=FALSE)`
- GSMxxx: ID de muestra, información de cada muestra individual. 
- GPLxxx: ID de plataforma, describe el sistema usado para obtener los datos. 