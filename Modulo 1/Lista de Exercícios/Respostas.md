 2. (a) Utilizando invariantes de loop, mostre que esse algoritmo funciona.
	
	Prova de corretude da função `findMinimum(int A[1..n], int idx)`:
	
	**Inicialização**: antes da primeira iteração do loop, a função recebe como entrada o índice $idx$ e inicializa a variável $min$, atribuindo a ela o valor de $idx$. Na primeira iteração do loop, o valor o elemento $A[idx]$ é comparado com o valor do elemento imediatamente subsequente $A[idx+1]$, o índice do elemento de menor valor entre eles é então armazenado na variável $min$.
	
	**Manutenção**: a cada iteração do loop, o valor de $A[min]$ é comparado com o valor de $A[j]$, o índice do menor valor é armazenado na variável $min$ e $j$ é incrementado em $1$. Por inferência, pode-se concluir que ao final de cada loop, o valor de $A[min]$ é menor ou igual a todos os demais entre $idx$ e $j$. Ou seja, $A[min] \leq A[i] \ \forall \ idx \leq i \leq j$.
	
	**Terminação**: ao final de todas as iterações do loop, $j = n$, portanto por inferência temos que $A[min] \leq A[i] \ \forall \ idx \leq i \leq n$. Dessa forma, pode-se concluir que $min$ será o índice do elemento de menor valor do subvetor $A[idx..n]$. Logo, a Função `findMinimum` retorna com sucesso o índice do elemento de menor valor entre $A[idx]$ e todos os elementos subsequentes do vetor $A$.
	
	Prova de corretude de `SelectionSort(int A[1..n])`:
	
	**Inicialização**: na primeira iteração do loop, $i=1$ e o subvetor $A[i..n]$ é o próprio vetor $A$. Dessa forma, a chamada da função `findMinimum (A, 1)` retorna índice do elemento de menor valor do vetor $A$, que é armazenado em $midx$. A função `swap (A[1], A[midx])` atribui ao primeiro elemento do vetor $A$ o menor valor dentre os elementos de $A$ e aloca na posição $A[midx]$  e  aloca o valor original de $A[1]$ na posição $A[midx]$. Por fim, $i$ é incrementado em $1$. Portanto, ao final da primeira iteração, o subvetor $A[1..i]$ está ordenado.
	
	 **Manutenção**: a cada iteração do loop, o menor valor dentre os elementos do subvetor $A[i..n]$ é alocado em na posição $A[i]$, de forma que, ao final de cada iteração o subvetor $A[1..i]$ está ordenado e contem os menores valores dentre os elementos de $A$. Portanto, ao final de cada iteração temos que $A[j] \leq A[j+1] \leq A[k] \ \forall \ 1 \leq j \leq i \ , \ i < k \leq n$.
	
	**Terminação**: ao final da ultima iteração do loop $i=n$, logo, por inferência, temos que $A[j] \leq A[j+1] \ \forall \ 1 \leq j \leq n$. Portanto, em seu último passo, a função `SelectionSort` exibe corretamente o vetor $A$ ordenado de forma crescente.
	
	(b) Qual é a função de complexidade do número de comparações de elementos no melhor e pior caso?
	
	Independente da ordenação de $A$, o algoritmo sempre realiza o mesmo número de comparações entre os elementos de A, uma vez que o algoritmo realiza todas as comparações mesmo que a lista esteja ordenada em algum passo intermediário. A função de complexidade do número de comparações é, portanto, a mesma para o melhor e o pior caso:
	$$f(n) = \sum 1+2+...+(n-1) = \frac{(n-1)n}{2}$$
	portanto, pode-se afirmar que $f(n) \in O(n^2)$.

	 
