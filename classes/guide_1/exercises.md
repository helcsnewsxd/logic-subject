# Guía 1: ejercicios

## Ejercicio 1

### Item A

**Verdadero**. Para ello, veamos cada afirmación:

- $R=\emptyset$ es una relación binaria sobre $X$: sí, dado que $\emptyset\subseteq X^2$
- $R$ es transitiva, simétrica y antisimétrica respecto a $X$: sí, dado que al ser vacío, no hay relaciones entre los elementos de $X$, por lo que no hay elementos que no cumplan con las propiedades.

### Item B

**Falso**. Se puede ver por contraejemplo considerando $X=\{ 1,2,3\}$ y $R=\{ (1,2), (2,1), (1,3)\}$. Luego, es claro que:

- No es antisimétrica, dado que $1R2\wedge 2R1$ pero $1\neq 2$
- No es simétrica, dado que $1R3\not\Rightarrow 3R1$

### Item C

**Verdadero**. Se puede notar dado que si $R=A^2$, entonces:

- Es reflexiva porque $\forall x\in A, (x,x)\in R$
- Es transitiva porque, en particular, $(x,y)\in R\forall x,y\in A$
- Es simétrica porque, en particular, $(x,y)\in R\forall x,y\in A$

Luego, entonces, por definición, es una relación de equivalencia.

### Item D

**Falso**. Dado que si $A\neq\emptyset$, entonces no cumple con la reflexividad.

### Item E

**Verdadero**. Es trivial de ver.

### Item F

**Falso**. Lo veamos por contraejemplo. Por (c) sabemos que $R=\mathbb{N}^2$ es una relación de equivalencia sobre $\mathbb{N}$. Luego, $R$ **no** es una relación de equivalencia sobre $\mathbb{N}-\{1\}$, porque no es una relación binaria sobre $\mathbb{N}-\{1\}$, dado que $\mathbb{N}^2\not\subseteq (\mathbb{N}-\{1\})^2$.

## Ejercicio 2

Sea $R$ una relación de equivalencia sobre $A$ y sea $a\in A$, entonces tenemos que $a/R=\{ b\in A:aRb\}$ por definición. Luego, como $R$ es una relación de equivalencia, por definición es reflexiva, por lo que se cumple $aRa$. Finalmente, y en base a la definición de $a/R$, tenemos que $a\in a/R$. $\blacksquare$

## Ejercicio 3

Sea $R$ una relación de equivalencia sobre $A$ y sean $a,b\in A$, vamos a ver los dos casos del sí y solo sí:

- $aRb\Rightarrow a/R=b/R$: si $aRb$, entonces $\forall x\in b/R$ se cumple $bRx$, por lo que por transitividad $aRx$; lo que significa que $x\in a/R$. Luego, por reflexividad sabemos que $bRa$, por lo que de forma análoga sale que $\forall x\in a/R, x\in b/R$. Finalmente, esto significa que $a/R=b/R$. $\blacksquare$
- $aRb\Leftarrow a/R=b/R$: por $(2)$, sabemos que $b\in b/R$. Luego, como $a/R=b/R, b\in a/R$, por lo que por definición de $a/R$, $aRb$. $\blacksquare$

Finalmente, entonces, se demuestra que $aRb\iff a/R=b/R$.

## Ejercicio 4

Sea $R$ una relación de equivalencia sobre $A$ y sean $a,b\in A$, veamos los dos casos:

- Supongamos que $a/R\neq b/R$, entonces por $(3)$ tenemos que _no se cumple_ $aRb$. Luego, queda claro que $\nexists x\in A:x\in a/R\wedge x\in b/R$, dado que eso significaría que $aRx$ y $bRx$, por lo que por simetría tendríamos $xRb$ y, por transitividad, $aRb$ llegando a un absurdo. Luego, entonces, si no se cumple la igualdad entre $a/R$ y $b/R$, entonces estos no comparten ningún elemento. Es decir, $a/R\cap b/R=\emptyset$.
- Supongamos que $a/R\cap b/R\neq\emptyset$, entonces $\exists x\in A: x\in a/R\wedge x\in b/R$. Luego, por lo mismo que antes, esto significaría $aRb$, por lo que por $(3)$ se cumple que $a/R=b/R$.

Finalmente, entonces, esto significa que se cumple siempre que $a/R\cap b/R=\emptyset\lor a/R=b/R$. $\blacksquare$

## Ejercicio 5

Si consideramos $R=\{ (x,y)\in\mathbb{Z}^2:5|x-y\}$, entonces $\mathbb{Z}/R$ tiene $5$ clases de equivalencia que son los $5$ conjuntos de números separados según su resto en la división por $5$.

Es decir, $\mathbb{Z}/R=\{ \{5k:k\in\mathbb{Z}\}, \{5k+1:k\in\mathbb{Z}\}, \{5k+2:k\in\mathbb{Z}\}, \{5k+3:k\in\mathbb{Z}\}, \{5k+4:k\in\mathbb{Z}\}\}$.

## Ejercicio 6

Sea $R=\{ (x,y)\in\mathbb{N}^2:x,y\leq 6\}\cup\{ (x,y)\in\mathbb{N}^2:x,y\gt 6\}$, entonces podemos ver que:

- Es una relación binaria sobre $\mathbb{N}$, dado que $R\subseteq\mathbb{N}^2$
- Es reflexiva porque $\forall x\in\mathbb{N}:x\le 6, (x,x)\in R$ y $\forall y\in\mathbb{N}:y\gt 6, (y,y)\in R$, lo cual significa que $\forall z\in\mathbb{N}, (z,z)\in R$
- Es transitiva porque si $\exists x,y,z\in\mathbb{N}:xRy\wedge yRz$, entonces o bien $x,y,z\le 6$, o bien $x,y,z\gt 6$, lo que significa que, en ambos casos, se cumple $xRz$
- Es simétrica porque si $\exists x,y\in\mathbb{N}:xRy$, entonces o bien $x,y\le 6$, o bien $x,y\gt 6$, lo que significa que, en ambos casos, se cumple $yRx$

Luego, demostramos que $R$ es una relación de equivalencia sobre $\mathbb{N}$. $\blacksquare$

Respecto a $\mathbb{N}/R$, es sencillo notar que tiene $2$ clases de equivalencias, dado que $\mathbb{N}/R=\{ \{x\in\mathbb{N}:x\le 6\}, \{x\in\mathbb{N}:x\gt 6\}\}$.

## Ejercicio 7

### Item A

**Verdadero**. Sea $R$ una relación de equivalencia sobre $A\neq\emptyset$, entonces veamos que:

$$|A/R|=1\iff \forall a,b\in A, a/R=b/R\overset{(3)}{\iff}\forall a,b\in A, aRb\iff R=A^2$$

Por lo que se demuestra que $|A/R|=1\iff R=A^2$. $\blacksquare$

### Item B

**Falso**. Si $R$ es una relación de equivalencia sobre $A$, entonces $A/R=\{ a/R:a\in A\}$

### Item C

**Falso**. Sea $R$ una relación de equivalencia sobre $A=\{ 1,2,3,4,5\}$, entonces $|\{i/R:i\in A\}|=|A/R|$. Luego, si $R=A^2$, por $(a)$ tenemos que $|A/R|=1\neq 5$.

### Item D

**Falso**. Sea $R=\{ (x,y)\in A^2:x=y\}=\{ (x,x):x\in A\}$ una relación de equivalencia sobre $A$, entonces tenemos que $a/A=\{ a\}\forall a\in A$. Luego, esto significa que $A/R=\{ a/A:a\in A\}=\{ \{a\}:a\in A\}\neq A$. $\blacksquare$

### Item E

**Falso**. Digamos $R=\mathbb{N}^2$ una relación de equivalencia sobre $\mathbb{N}$ y $C=\{ 1\}\subseteq\mathbb{N}$. Luego, es claro que $C\not\subseteq A/R$ dado que $A/R=\{\{x:x\in\mathbb{N}\}\}$.

## Ejercicio 8

### Item A

Sea $R$ una relación de equivalencia sobre $A$, entonces veamos que:

$$\begin{aligned}
    ker(\pi_R)&\overset{\text{def. }ker}{=}\{ (a,b)\in A:\pi_R(a)=\pi_R(b)\}\\
    &\overset{\text{def. }\pi_R}{=}\{ (a,b)\in A:a/R=b/R\}\\
    &\overset{(3)}{=}\{ (a,b)\in A:aRb\}\\
    &=R
\end{aligned}$$

por lo que se demuestra que $ker(\pi_R)=R$. $\blacksquare$

### Item B

Sea $R$ una relación de equivalencia sobre $A$, entonces veamos que:

$$\begin{aligned}
    \pi_R\text{ es inyectiva}&\overset{\text{def.}}{\iff}\forall x,y\in A,(\pi_R(x)=\pi_R(y)\Rightarrow x=y)\\
    &\overset{\text{def. }\pi_R}{\iff}\forall x,y\in A,(x/R=y/R\Rightarrow x=y)\\
    &\overset{(3)}{\iff}\forall x,y\in A, (xRy\Rightarrow x=y)\\
    &\iff \nexists x,y\in A:(xRy\wedge x\neq y)\\
    &\iff R=\{ (x,x):x\in A\}=\{ (x,y)\in A^2:x=y\}
\end{aligned}$$

por lo que se demuestra que $\pi_R$ es inyectiva si y solo si $R=\{ (x,y)\in A^2:x=y\}$. $\blacksquare$

## Ejercicio 9

Sean $\mathcal{P}$ una partición de $A$ y $a\in A$, por definición sabemos que $\exists S\in\mathcal{P}:a\in S$ y que $\forall S'\neq S\in\mathcal{P}, S\cap S'=\emptyset$, por lo que, entonces $a\notin S'$. Luego, se demuestra que $S$ es único. $\blacksquare$

## Ejercicio 10

### Item A

Sea $\mathcal{P}$ una partición de $A$, definimos $R_\mathcal{P}=\{(a,b)\in A^2:a,b\in S\text{ para algún }S\in\mathcal{P}\}$. Luego, notemos que:

- Es una relación binaria sobre $A$, dado que $R_\mathcal{P}\subseteq A^2$
- Es reflexiva porque $\forall x\in A, xR_\mathcal{P}x$, dado que $x\in S$ para algún $S\in\mathcal{P}$
- Es transitiva porque $\forall x,y,z\in A:xR_\mathcal{P}y\wedge yR_\mathcal{P}z$ tenemos que $x,y\in S$ y $y,z\in S$ para algún $S\in\mathcal{P}$. Luego, como $x,z\in S$, entonces $xR_\mathcal{P}z$
- Es simétrica porque $\forall x,y\in A:xR_\mathcal{P}y$ implica que $x,y\in S$ para algún $S\in\mathcal{P}$, por lo que $y,x\in S$ y, por lo tanto, $yR_\mathcal{P}x$

Finalmente, entonces, se demuestra que $R_\mathcal{P}$ es una relación de equivalencia sobre $A$. $\blacksquare$

### Item B

Sea $R$ una relación de equivalencia sobre $A$, entonces notemos para $A/R=\{a/R:a\in A\}$ que:

- $\forall a\in A, a/R\subseteq A$ (por def.) y $a/R\neq\emptyset$ (dado que $a\in a/R$)
- $\forall a,b\in A:a/R\neq b/R, a/R\cap b/R=\emptyset$ por $(4)$
- $\bigcup_{a\in A}a/R=A$

Finalmente, entonces, por definición, se demuestra que $A/R$ es una partición de $A$. $\blacksquare$

## Ejercicio 11

### Item A

**Impreciso**. $\mathcal{P}$ si es una partición de $X$, entonces no es una relación binaria sobre $X$ y, menos, una relación de equivalencia. Luego, $x/\mathcal{P}$ no tiene sentido.

### Item B

**Impreciso**. No tiene sentido lo escrito. En particular, una partición de $X$ es un conjunto de conjuntos de elementos de $X$.

### Item C

**Falso**. $\{1,3\},\{2,4\},\{5,6\}$ **no** es una partición de $\{1,2,3,4,5,6\}$ porque no es un conjunto. Para que lo sea, debería ser $\{\{1,3\},\{2,4\},\{5,6\}\}$.

### Item D

**Verdadero**. Porque $X$ es un conjunto de elementos de $X$ y $\mathcal{P}$ es un conjunto de conjuntos de elementos de $X$.

### Item E

**Verdadero**. Bajo el mismo criterio que $(d)$, dado que $A/R$ con $R$ relación de equivalencia, es una partición de $A$.

### Item F

**Verdadero**. Esto se nota por que al ser biyección, se necesita que tanto $A$ y $A/R$ tengan la misma cardinalidad. Luego, $A/R$ tiene que ser de la forma $\{\{a:a\in A\}\}$, lo que significa que $R=\{(x,x):x\in A\}$.

## Ejercicio 12

### Item A

**Falso**. Porque la partición que se hace con $\mathbb{Z}/R$ con $R=\{(x,y)\in\mathbb{Z}:2|x-y\}$ es la de números impares por un lado y números pares por el otro. Es decir, $\mathbb{Z}/R=\{\{2k:k\in\mathbb{Z}\},\{2k+1:k\in\mathbb{Z}\}\}$. Luego, tendríamos, por ejemplo, que $1=f(0/R)=f(2/R)=\frac{1}{5}$, lo cual es absurdo.

### Item B

**Impreciso**. Porque no es una función, dado que si la consideramos como $f$ en el caso de $(a)$, entonces $0=f(0/R)=f(2/0)=2$, lo cual es absurdo.

## Ejercicio 13

Si tenemos $F:\mathbb{N}\to\{0,1,2,3\}$ dada por $F(n)=n\mod 4$, entonces notemos que $ker(F)=\{(x,y)\in\mathbb{N}^2:x\mod 4=y\mod 4\}$, por lo que para $n\in\mathbb{N}$ se cumple que $n/ker(F)=\{x\in\mathbb{N}:x\mod 4=n\mod 4\}$ (es decir, es el conjunto de números con mismo resto módulo $4$ que $n$).

Teniendo esto en mente, si consideramos $f:A/ker(F)\to\mathbb{N}$ como $f(n/ker(F))=F(n)$, tenemos que esta es una función dado que la invariante de cada grupo de la partición es, justamente, su resto módulo $4$. $\blacksquare$

Respecto a las preguntas de inyectividad o suryectividad, tenemos para $f$ que:

- Es inyectiva porque si $\exists n,m\in\mathbb{N}:f(n/ker(F))=f(m/ker(F))$, entonces $F(n)=F(m)$, por lo que $n\mod 4=m\mod 4$, lo que significa que $n/ker(F)=m/ker(F)$
- No es suryectiva porque $Im(f)=\{0,1,2,3\}\neq\mathbb{N}$

## Ejercicio 14

### Item A

Sea $F:A\to B$ una función sobreyectiva, entonces veamos que $ker(F)$ es una relación de equivalencia sobre $A$ respecto a los valores de $Im(F)=B$ (al ser sobreyectiva). Es decir, $ker(F)=\{(a,b)\in A^2:F(a)=F(b)\}$.

Ahora, esto significa que $a/ker(F)=\{x\in A:F(x)=F(a)\}$, por lo que si consideramos $f:A/ker(F)\to B$ como $f(a/ker(F))=F(a)$, tenemos que es una función porque la invariante de cada grupo de la partición $A/ker(F)$ es, justamente, el valor de $F$ en ese grupo. $\blacksquare$

### Item B

Ahora, si queremos ver si $f$ es biyectiva, notemos que, a diferencia del ejercicicio $(13)$, acá definimos $f:A/ker(F)\to B$. Luego, teniendo esto en cuenta, veamos que:

- Es inyectiva porque si $\exists a,b\in A:f(a/ker(F))=f(b/ker(F))$, entonces $F(a)=F(b)$, por lo que $a/ker(F)=b/ker(F)$ dado que cada grupo de $A/ker(F)$ tiene un único valor de $F$
- Es sobreyectiva porque $Im(f)=Im(F)=B$, dado que $F$ es sobreyectiva

Con ello, entonces, se demuestra que $f$ es biyectiva. $\blacksquare$