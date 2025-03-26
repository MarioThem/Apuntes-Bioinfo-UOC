
- **Métodos del componente principal**: se usan para resumir y visualizar la información contenida en grandes sets de datos, existiendo de varios tipos:![[Pasted image 20250326104210.png]]
	1. PCA: análisis de componentes principales, para analizar sets de datos con variables continuas (por ejemplo, expressionsets).  
		- https://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/112-pca-principal-component-analysis-essentials/
		- https://uw.pressbooks.pub/appliedmultivariatestatistics/chapter/eigenanalysis/
		- https://uw.pressbooks.pub/appliedmultivariatestatistics/chapter/pca/
	2. CA: analisis de correspondencia, para analizar la asociación entre dos variables categóricas. 
		- https://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/113-ca-correspondence-analysis-in-r-essentials/
	3. MCA: análisis de correspondencia múltiple, para analizar un dataset con más de dos variables categóricas. 
		- https://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/114-mca-multiple-correspondence-analysis-in-r-essentials/
	4. FAMD: análisis de factores de datos mixtos(variables categóricas y variables continuas). 
		- https://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/115-famd-factor-analysis-of-mixed-data-in-r-essentials/
	5. MFA: análisis de factores múltiples, para analizar un data set que contiene variables estructuradas en grupos. 
		- https://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/116-mfa-multiple-factor-analysis-in-r-essentials/
-  **Métodos de clustering**:  es un método de aprendizaje automático no supervisado, de reconocimiento de patrones e identificación de grupos en los datos. 
	-  https://www.datanovia.com/en/blog/cluster-analysis-in-r-practical-guide/
	- https://www.datanovia.com/en/blog/types-of-clustering-methods-overview-and-quick-start-r-code/
- **Visualizaciones gráficas:** 
	- Gráficos base de R: ![[Pasted image 20250326110629.png]]
	-  lattice: y ~ x, grupo, datos...![[Pasted image 20250326111058.png]] 
	- paquete ggplot: data + aes(variables x e y, color, tamaño, forma...) + geom(geometria, tipo de gráfico).  Se puede usar el paquet esquisse también. ![[Pasted image 20250326110948.png]]
	![[Pasted image 20250326111222.png]]
	![[Pasted image 20250326111231.png]]