# Tipos de problema a tratar: 

- De identificación de biomarcadores que caractericen la diferencia entre dos grupos. 
- De descubrimiento de grupos (por ejemplo, caracterización molecular del cáncer)
- Estudios predictivos, elaboración de modelos de predicción. 

# Fases del proceso
![[Pasted image 20250324130351.png]]

1.  Diseño experimental del estudio: randomización, replicación, escoger controles adecuados...
2.  Generación de los datos: secuenciación, microarrays...
3.  Control de calidad de los datos (de bajo nivel): secuenciacion por ejemplo con FastQC. 
4. Preprocesado de los datos: transformación de los datos para poder utilizarlos en los análisis. ![[Pasted image 20250324130557.png]]![[Pasted image 20250324130547.png]]
5. Análisis exploratorio: ver como son los datos, en algunos casos junto al preprocesado, para poder corregir posibles defectos. 
6. Cuando no hagan falta correcciones adicionales, se pasa al análisis estadístico. Puede ser construir y analizar un predictor o comparar variables y grupos. 
7. Analisis de significación biológica: ayuda a interpretar los resultados del estudio de genes. 