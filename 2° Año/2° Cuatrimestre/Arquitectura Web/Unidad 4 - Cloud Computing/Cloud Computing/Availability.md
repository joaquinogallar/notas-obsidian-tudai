# Qué es?
La probabilidad de que un recurso de [[IT (Tecnologías de la Información)]] pueda ser accedido. En general se basa en un periodo de **tiempo**.

# Formula
$$
\text{Disponibilidad} = \left( 1 - \frac{\text{Tiempo caído}}{\text{Tiempo total}} \right) \times 100
$$

Si se proporciona un **porcentaje de probabilidad de caída**, primero es necesario calcular el tiempo de caída multiplicando ese porcentaje por el tiempo total. Es decir, se debe dividir la probabilidad de caída entre 100 y luego multiplicar el resultado por el tiempo total. Por ejemplo si la probabilidad de que se caiga 12hs es del 20% en 1 año:
$$
\begin{aligned}
\frac{20}{100} &= 0.2 \\
0.2 \times 12 &= 2.4 \, \text{hs} \\
&2.4hs =\text{Tiempo caído}
\end{aligned}
$$

