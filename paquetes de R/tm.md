# Crear un corpus

Paquete de R para el text mining. Su estructura principal es un objeto llamado Corpus, que representa una colección de documentos, y pueden construirse de dos formas: 

- `VCorpus(x, readerControl)`: una colección volátil de documentos, alojada en la memoria, que desaparece cuando se destruye el objeto en R. 
- `PCorpus(x, readerControl, dbControl)`: una colección permanente de documentos, alojada en una base de datos, los objetos de R apuntan a estos documentos. 

Los elementos de estos constructores corresponden a :

- **x, objeto de tipo Source**: abstract input locations, like a directory, a connection, or simply an **R** vector, in order to acquire content in a uniform way. El paquete proporciona sources como DirSource, VectorSource o DataframeSource. Para ver más sources->`getSources()`![[Pasted image 20250323141509.png]]
- `readerControl = list(reader = reader(x), language = "en")`: reader construye un documento de texto a partir del source. El paquete ofrece algunos predefinidos: `readPlain(), readPDF(), readDOC()`... pero se pueden consultar los disponibles con `getReaders()`. Por otro lado, language define el idioma, en forma de código ISO 639-2. 
- `dbControl = list(dbName = "", dbType = "DB1")`: dbName el nombre del archivo de la base de datos, y dbType un tipo de base de datos del paquete filehash. 

```r
reut21578 <- system.file("texts", "crude", package = "tm")
VCorpus(DirSource(reut21578, mode = "binary"),
        list(reader = readReut21578XMLasPlain))

<<VCorpus>>
Metadata:  corpus specific: 0, document level (indexed): 0
Content:  documents: 20
```

- `writeCorpus()`: guardar los textos en un disco, exportar los datos. 

Se puede usar print(), inspect() y as.character(corpus[ [ 1 ]]) como maneras de ver los contenidos del corpus, ya que es una large list a efectos de R. 

# Transformaciones en un corpus

- `tm_map(corpus, función())`: se usa para aplicar transformaciones en forma de funciones a un corpus. Para ver las funciones de transformación disponibles, usar `getTransformations()`. ![[Pasted image 20250323141434.png]]
- `content_transformer()`; si la función a aplicar al corpus no está incluida como función de transformación en tm (son funciones de otros paquetes de R o creadas por el usuario). 
- **stemming**: consiste en reducir paralabras a su raíz básica, para que los algoritmos de ML puedan tratarlas de igual forma. Se puede usar combinado con el paquete `SnowballC,` que usa el algoritmo "snowball" para stemming, usando la función `stemDocument()`![[Pasted image 20250323141722.png]]

# Creación de una DTM

Una DTM es una matriz de documentos y términos, que lista en sus filas los documentos del corpus y en sus columnas los términos encontrados, indicando el número de veces que aparece esa palabra en cada documento.
![[Pasted image 20250323141953.png]]

Es una matriz sparse normalmente, con muchos 0. Se crea con la función `DocumentTermMatrix(corpus, list(dictionary = c("")), control = list())`. También puede crearse una TDM, por si se tienen pocos términos y muchos documentos. 

Se puede pasar una lista de palabras en forma de dictionary, para buscar palabras en concreto. 

```r
inspect(DocumentTermMatrix(reuters,list(dictionary = c("prices", "crude", "oil"))))
```

![[Pasted image 20250323143205.png]]

También se pueden pasar las transformaciones directamente al constructor de la matriz con control, y una lista de transformaciones, con tranformación = TRUE. 

Luego, este DTM se puede tratar como un data frame para hacer otras operaciones con el en R. 

- `findFreqTerms(DTM, número de veces que aparece)`: limitar los términos a un cierto número de veces que aparecen, para obtener datos más relevantes. 