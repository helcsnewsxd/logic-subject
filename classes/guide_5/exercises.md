# Guía 5: ejercicios

## Ejercicio 1

Queremos demostrar la propiedad que dice que: Si $(L,s,i,0,1)$ es un reticulado acotado, entonces $0\ i\ x=0\ \forall x\in L$.

Para ello, notemos que por def. tenemos que $0\ s\ x=x\ \forall x\in L$. Luego, por def. del orden parcial asociado, esto significa que $0\leq x$. Sin embargo, dado que $\leq=\{(x,y):x\ s\ y=y\}=\{(x,y):x\ i\ y=x\}$, entonces $0\ i\ x=0$, por lo que se demuestra. $\blacksquare$

## Ejercicio 1,5

### Item A

Falso. No se define de ese modo el reticulado acotado.

### Item B

Falso. Para que esto fuera verdad, debería ser $(L,i,s,1,0)$ (i.e., con el orden inverso).

### Item C

Falso. $0$ es el elemento mínimo, cuyo tipo puede ser cualquier cosa (conjunto, número, etc).

## Ejercicio 2

Queremos demostrar la propiedad que dice que: Si $(L,s,i,0,1)$ es un reticulado acotado y $S_1,S_2$ son subuniversos de $(L,s,i,0,1)$, entonces $S_1\cap S_2$ es un subuniverso de $(L,s,i,0,1)$.

Para demostrar esto, primero veamos que es fácil ver que $S_1\cap S_2$ es cerrado bajo $s,i$ dado que $S_1,S_2$ son subuniversos de $(L,s,i,0,1)$ y, por ende, también de $(L,s,i)$. Luego, por propiedad sabemos que $S_1\cap S_2$ es subuniverso de $(L,s,i)$, por lo que por def. es cerrado bajo $s,i$.

Ahora, queda ver que $0,1\in S_1\cap S_2$. Como $S_1,S_2$ son subuniversos, entonces por def. tenemos que $0,1\in S_1\wedge 0,1\in S_2$. Luego, es claro que $0,1\in S_1\cap S_2$.

Viendo esto, entonces, $S_1\cap S_2$ es cerrado bajo $s,i$ y $0,1\in S_1\cap S_2$, por lo que $S_1\cap S_2$ es un subuniverso de $(L,s,i,0,1)$ por def. y se demuestra. $\blacksquare$

## Ejercicio 3

Puede ser el diamante y considerar un par de entre los $3$ elementos del medio. Es decir, por ejemplo, $(\{1,2,3,5,30\},mcm,mcd,1,30)$ con $a=2$ y $b=3,b'=5$ dado que $2\ s\ 3=2\ s\ 5=30$ y $2\ i\ 3=2\ i\ 5=1$.

## Ejercicio 4

Queremos demostrar la propiedad que dice que: Sea $(L,s,i,0,1)$ un reticulado acotado, si $1$ es un complemento de $a$, entonces $a=0$. Del mismo modo, si $a$ es un complemento de $0$, entonces $a=1$.

Para ello, vamos a ver cada caso por separado:

- $a$ complemento de $1$: Tenemos por def. que $a\ s\ 1=1$, por lo que por def. del orden parcial, $a\leq 1$. Como $\leq=\{(x,y):x\ s\ y=y\}=\{(x,y):x\ i\ y=x\}$, entonces $a\ i\ 1=a$. Sin embargo, por def. de complemento también sabemos que $a\ i\ 1=0$, por lo que llegamos a $a\ i\ 1=a=0$. Luego, $a=0$ y se demuestra. $\blacksquare$
- $a$ complemento de $0$: Tenemos por def. que $a\ i\ 0=0$, por lo que por def. alternativa del orden parcial, $0\leq a$. Luego, por def. del orden parcial, $0\ s\ a=a$. Sin embargo, por def. de complemento también sabemos que $a\ s\ 0=1$, por lo que llegamos a $a\ s\ 0=a=1$. Luego, $a=1$ y se demuestra. $\blacksquare$

Con todo ello, demostramos ambos casos. $\blacksquare$

## Ejercicio 5

Las posibles operaciones unarias dependen únicamente de los tres elementos del "medio" y sus elecciones de pares (son $2^3=8$ posibilidades):

- $g=\{(30,1),(1,30),(2,3),(3,2),(5,2)\}$
- $g=\{(30,1),(1,30),(2,3),(3,2),(5,3)\}$
- $g=\{(30,1),(1,30),(2,3),(3,5),(5,2)\}$
- $g=\{(30,1),(1,30),(2,3),(3,5),(5,3)\}$
- $g=\{(30,1),(1,30),(2,5),(3,2),(5,2)\}$
- $g=\{(30,1),(1,30),(2,5),(3,2),(5,3)\}$
- $g=\{(30,1),(1,30),(2,5),(3,5),(5,2)\}$
- $g=\{(30,1),(1,30),(2,5),(3,5),(5,3)\}$

## Ejercicio 6

Consideramos el reticulado complementado $(\{1,2,3,5,30\},mcm,mcd,f,1,30)$ con $f=\{(30,1),(1,30),(2,3),(3,2),(5,2)\}$ y $S=\{1,3,5,30\}$. Luego, es claro que $S$ no cumple porque no es cerrado por $f$.

## Ejercicio 7

Trivial considerando $(\{1,2,3,5,30\},mcm,mcd,f_1,1,30)$ y $(\{1,2,3,5,30\},mcm,mcd,f_2,1,30)$ con:

- $f_1=\{(1,30),(30,1),(2,3),(3,2),(5,2)\}$
- $f_2=\{(1,30),(30,1),(2,5),(3,5),(5,3)\}$

Luego, si $F$ se define tal que $F(x)=x\ \forall x\in\{1,2,3,5,30\}$, entonces es trivial ver que es un homomorfismo dado que es un isomorfismo porque es el mismo reticulado acotado.

Sin embargo, al ser distintas las funciones de complementos, no se cumple que $F(f_1(2))=f_2(F(2))$ dado que $F(f_1(2))=F(3)=3$ pero $f_2(F(2))=f_2(2)=5$.

## Ejercicio 7,5

Queremos demostrar el lema que dice: Si $(L,s,i,0,1)$ es un reticulado acotado y distributivo, entonces todo elemento tiene a lo sumo un complemento. Es decir, si $x\ s\ u=x\ s\ v=1$ y $x\ i\ u=x\ i\ v=0$, entonces $u=v\ \forall x,u,v\in L$.

Para demostrar esto, sencillamente tenemos que ver que, sean $x,u,v\in L$ tales que:

$$
\begin{aligned}
    x\ s\ u=x\ s\ v=1\\
    x\ i\ u=x\ i\ v=0
\end{aligned}
$$

entonces se cumple que:

$$
\begin{aligned}
    u&=u\ i\ 1\\
    &=u\ i\ (x\ s\ v)\\
    &=(u\ i\ x)\ s\ (u\ i\ v)&\text{distributividad}\\
    &=0\ s\ (u\ i\ v)\\
    &=u\ i\ v\\
    \\
    u&=u\ s\ 0\\
    &=u\ s\ (x\ i\ v)\\
    &=(u\ s\ x)\ i\ (u\ s\ v)&\text{distributividad}\\
    &=1\ i\ (u\ s\ v)\\
    &=u\ s\ v
\end{aligned}
$$

Luego, con ello, entonces llegamos a que $u\leq v\wedge v\leq u$, por lo que $u=v$ y se demuestra. $\blacksquare$

## Ejercicio 8

Queremos demostrar el lema que dice que: Sea $(B,s,i,^c,0,1)$ un álgebra de Boole, $\forall x,y\in B, y=(y\ i\ x)\ s\ (y\ i\ x^c)$.

Para demostrar esto, notemos que:

$$
\begin{aligned}
    (y\ i\ x)\ s\ (y\ i\ x^c)&=y\ i\ (x\ s\ x^c)&\text{distributividad}\\
    &=y\ i\ 1&\text{def. reticulado complementado}\\
    &=y
\end{aligned}
$$

Por lo que se demuestra la igualdad para todo $x,y\in B$. $\blacksquare$

## Ejercicio 9

Queremos demostrar el teorema que dice que: Sea $(L,s,i,^c,0,1)$ un álgebra de Boole y sean $a,b\in L$, se tiene que

1. $(a\ i\ b)^c=a^c\ s\ b^c$
2. $(a\ s\ b)^c=a^c\ i\ b^c$
3. $a^{cc}=a$
4. $a\ i\ b=0\iff b\leq a^c$
5. $a\leq b\iff b^c\leq a^c$

Para demostrarlo, digamos $a,b\in L$ y veamos cada uno de los casos:

### Propiedad 1

Notemos que:

$$
\begin{aligned}
    (a^c\ s\ b^c)\ s\ (a\ i\ b)&=(a^c\ s\ b^c\ s\ a)\ i\ (a^c\ s\ b^c\ s\ b)&\text{distributividad}\\
    &=(1\ s\ b^c)\ i\ (a^c\ s\ 1)\\
    &=1\ i\ 1=1\\
    \\
    (a^c\ s\ b^c)\ i\ (a\ i\ b)&=(a^c\ i\ a\ i\ b)\ s\ (b^c\ i\ a\ i\ b)&\text{distributividad}\\
    &=(0\ i\ b)\ s\ (0\ i\ a)\\
    &=0\ s\ 0=0
    \\
\end{aligned}
$$

Luego, por def. tenemos que $a^c\ s\ b^c$ es el complemento de $a\ i\ b$. Ahora, como sabemos por lema $10$ que en un reticulado acotado y distributivo todo elemento tienen a lo sumo un complemento (y nosotros estamos trabajando con un Álgebra de Boole, es decir, un reticulado complementado distributivo), entonces tenemos que es único. Luego, queda claro que $(a\ i\ b)^c=a^c\ s\ b^c$ y se demuestra. $\blacksquare$

### Propiedad 2

Se demuestra de igual modo que la anterior notando que:

$$
\begin{aligned}
    (a^c\ i\ b^c)\ s\ (a\ s\ b)&=(a^c\ s\ a\ s\ b)\ i\ (b^c\ s\ a\ s\ b)&\text{distributividad}\\
    &=(1\ s\ b)\ i\ (a\ s\ 1)\\
    &=1\ i\ 1=1\\
    \\
    (a^c\ i\ b^c)\ i\ (a\ s\ b)&=(a^c\ i\ b^c\ i\ a)\ s\ (a^c\ i\ b^c\ i\ b)&\text{distributividad}\\
    &=(b^c\ i\ 0)\ s\ (a^c\ i\ 0)\\
    &=0\ s\ 0=0
\end{aligned}
$$

Luego, es claro que por def. $a^c\ i\ b^c$ es el complemento de $a\ s\ b$. Ahora, por lema $10$ sabemos que es único, por lo que $(a\ s\ b)^c=a^c\ i\ b^c$ y se demuestra. $\blacksquare$

### Propiedad 3

Notemos que es claro que $a$ y $a^{cc}$ son complementos de $a^c$. Luego, por lema $10$ sabemos que tiene $1$ solo complemento, por lo que $a=a^{cc}$ y se demuestra. $\blacksquare$

### Propiedad 4

Para demostrarlo, vamos a tener que ver ambos lados de la doble implicación. Primero, _miremos la ida_: Tenemos $a\ i\ b=0$. Con ello:

$$
\begin{aligned}
    b&=b\ i\ 1\\
    &=b\ i\ ((a\ i\ b)\ s\ (a\ i\ b)^c)&\text{def. complemento}\\
    &=b\ i\ (0\ s\ (a\ i\ b)^c)&\text{supuesto}\\
    &=b\ i\ (a\ i\ b)^c\\
    &=b\ i\ (a^c\ s\ b^c)&\text{prop. 1 del teorema}\\
    &=(b\ i\ a^c)\ s\ (b\ i\ b^c)&\text{distributividad}\\
    &=(b\ i\ a^c)\ s\ 0\\
    &=b\ i\ a^c
\end{aligned}
$$

Luego, como $b=b\ i\ a^c$, por def. dual/alternativa del orden parcial $\leq$, tenemos que $b\leq a^c$ y se demuestra la ida. $\blacksquare$

Ahora, _vamos a demostrar la vuelta_: Tenemos $b\leq a^c$. Luego, por def. alternativa del orden $\leq$, esto significa que $b\ i\ a^c=b$. Con ello, veamos que:

$$
\begin{aligned}
    a\ i\ b&=a\ i\ (b\ i\ a^c)&\text{lo visto antes}\\
    &=(a\ i\ a^c)\ i\ b\\
    &=0\ i\ b\\
    &=0
\end{aligned}
$$

Luego, llegamos a que $a\ i\ b=0$ y se demuestra la vuelta también. $\blacksquare$

Con todo ello, habiendo demostrado ida y vuelta, se prueba la propiedad por completo. $\blacksquare$

### Propiedad 5

Para demostrar esta propiedad, tenemos que ver tanto la ida como la vuelta. Para ello, veamos cada parte.

Consideremos _la ida_, entonces $a\leq b$, por lo que $a=a\ i\ b$. Con ello, notemos que esto implica que $a^c=(a\ i\ b)^c\overset{prop. 1}{=}a^c\ s\ b^c$, por lo que por def. del orden parcial, $b^c\leq a^c$ y se demuestra. $\blacksquare$

Ahora, consideremos _la vuelta_. Entonces $b^c\leq a^c$, por lo que por def. dual del orden parcial, $a^c\ i\ b^c=b^c$. Luego, esto significa que $b^{cc}=(a^c\ i\ b^c)^c\overset{prop. 1}{=}a^{cc}\ s\ b^{cc}$ y por prop. 3 llegamos a que $b=a\ s\ b$, por lo que por def. del orden parcial tenemos que $a\leq b$, demostrándose la vuelta. $\blacksquare$

Habiendo probado ambos casos, se demuestra la propiedad en su completitud. $\blacksquare$

## Ejercicio 10

Para las primeras cuatro propiedades vamos a considerar $(\{1,2,3,5,30\},mcm,mcd,f_1,1,30)$ donde $f_1=\{(1,30),(30,1),(2,3),(3,2),(5,2)\}$. Luego, notemos que:

1. $(3\ i\ 5)^c=1^c=30\neq 3^c\ s\ 5^c=2\ s\ 2=2$
2. $(3\ s\ 5)^c=30^c=1\neq 3^c\ i\ 5^c=2\ i\ 2=2$
3. $5^{cc}=2^c=3\neq 5$
4. $3\ i\ 5=0$ pero $3\nleq 5^c=2$

Y para la última propiedad consideraremos el reticulado complementado $(\{1,2,5,6,25,150\},mcm,mcd,f_2,1,150)$ donde $f_2=\{(1,150),(150,1),(5,2),(2,5),(6,25),(25,6)\}$. Luego:

5. $5\leq 25$ pero $25^c=6\nleq 5^c=2$

Con ello, se muestra un contraejemplo para cada una de las propiedades del teorema si se quiere aplicar a un reticulado complementado cualquiera que no sea Álgebra de Boole (i.e., no distributivo).
