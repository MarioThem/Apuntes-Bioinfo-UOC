Tras seleccionar **"Add custom track",** se pueden añadir archivos en distintos formatos, con estas lineas generales de configuración en común:

```
browser position cromosoma:inicio-final 
browser [hide/dense/pack/full] pista 1 
...
browser [hide/dense/pack/full] pista n
```

**Primera línea** sirve para configurar la visión general del navegador: en que cromosoma se centra y las posiciones de inicio y final en las que se centra (siempre en notación 0-coded).

**Siguientes líneas** configuran cada uno de los tracks predeterminados en UCSC. 

**...** -> bloques de tracks personalizados, en el siguiente formato:

```
track name=nombreN type= wiggle_0/bedGraph description=descripcion visibility=[0-4] color=R,G,B altcolor=R,G,B (solo en BedGraph)
```

Solo es necesario especificar el type si es un archivo [[BedGraph]] o [[Wiggle]], para [[GFF]] o [[BED ]]no hace falta. 