# Convolucao_Circular
Este projeto implementa a convolução linear a partir da convolução circular utilizando os critérios de equivalência do número de amostras, além de uma implementação matricial dos mesmos.

#**Convolução linear discreta para sinais digitais**
A convolução linear é uma operação entre dois sinais ou funções que representa a saída de um sistema linear e invariante no tempo.
A convolução linear discreta entre dois sinais $x[n]$ e $h[n]$ é dada por


$$
y[n] = x[n] * h[n] = ∑_{k = -∞}^{∞} x[k] \cdot h[n-k]
$$


#**Convolução Circular**
A convolução circular é a convolução entre dois sinais que tiveram seus espectros amostrados, e então por esse fato se tornaram sinais periódicos, dessa maneira, é possível construir uma matriz de convolução circular que se aproveite desse fato para o cálculo desse tipo de convolução, que pode ser considerada igual a convolução linear caso o tamanho da convolução seja suficientemente grande.
A convolução circular entre dois sinais de tempo discreto é dada por

$$
y[n] = x[n] \circledast h[n] = ∑_{0}^{N-1} x[k] \cdot h[n-k]
$$

Sejam os suportes dos sinais $x$ e $h$ dados por

$$
sup_{x[n]} =[0,M-1]
$$

e

$$
sup_{h[n]} =[0,L-1]
$$

então para que não haja sobreposição na convolução circular, e ela se iguale a linear, é necessário que

se $N \geq M + L -1$ , a convolução circular se torna igual à linear.


#**Convolução Circular Matricial**
A operação de convolução pode ser ainda escrita no formato matricial, mostrando mais uma vez que a convolução é uma operação linear, e então temos

$$
y = Hx
$$

onde H é uma matriz de toeplitz do sinal $h[n]$, ou seja, é construída de modo que cada coluna seja um deslocamento circular do vetor que representa o sinal $h[n]$, que tem a forma:


$$
H = \begin{bmatrix}
h[0] & h[N-1] & h[N-2] & \cdots & h[1] \\
h[1] & h[0] & h[N-1] & \cdots & h[2] \\
h[2] & h[1] & h[0] & \cdots & h[3] \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
h[N-1] & h[N-2] & h[N-3] & \cdots & h[0]
\end{bmatrix}
$$

mais uam vez, se $N \geq L+M-1$, essa operação matricial implementa a convolução linear exata.
