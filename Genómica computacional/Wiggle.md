BIGWIG es un formato comprimido de wiggle (WIG). Se utiliza para representar valores continuos, pero, al contrario que [[BedGraph]], no es necesario especificar todos los valores, solo el inicio. 

Cuando la distancia entre las anotaciones es variable, se usa variableStep:


```
variableStep chrom=cromosoma

coordenada valor

...

variableStep chrom=cromosoma span=largo(por defecto es 1)

coordenada valor
```

![[Pasted image 20250315123057.png]]

En cambio, si la distancia entre las anotaciones es fija, se usa el fixedstep:

```
fixedStep chrom=cromosoma start=inicio span=largo step=paso 
coordenada valor(se puede poner solo valor)
```
