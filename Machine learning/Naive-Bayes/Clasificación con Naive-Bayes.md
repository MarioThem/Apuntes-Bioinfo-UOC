
Si existen varios factores, el algoritmo asume que las probabilidades de que ocurra un evento o no dependiendo de que ocurran o no estos factores son independientes entre sí, por lo tanto: 

$$
P(C_L|F_1,...,F_n) = \frac{1}{Z}p(C_L)\prod_{i=1}^{n}p(F_i|C_L)
$$
La probabilidad de que ocurra un nivel L de la clase C, en base a los factores Fn, es igual al producto de las probabilidades de que ocurra cada factor Fn y ese nivel de la clase C, multiplicado todo por la probabilidad del nivel de esa clase, y aplicando un factor de escalado Z (que sería $P(C_L|F_n) + P(C_L|F_n)^{c}$).