Con una unica función, wordcloud(), permite crear nubes de palabras para mostrar la frecuencia de las palabras en unos documentos, estando las más frecuentes con una fuente más grande y viceversa. 
```r
wordcloud(words,freq,scale=c(4,.5),min.freq=3,max.words=Inf,
	random.order=TRUE, random.color=FALSE, rot.per=.1,
	colors="black",ordered.colors=FALSE,use.r.layout=FALSE,
	fixed.asp=TRUE, ...)
```
![[Pasted image 20250324105035.png]]