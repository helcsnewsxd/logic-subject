# Guía 7: _Estructuras y su lenguaje elemental asociado_

- Para las definiciones de fórmula elemental para alguno de los anteriores tipos de estructuras vistos, consideraremos solo aquellas que se puedan construir usando solo los símbolos distinguidos del tipo de estructura en cuestión más la lista de símbolos clásicos:
  - $\forall\ \exists\ \neg\ \lor\ \wedge\ \to\ \leftrightarrow\ (\ ,\ )\ =$
  - $x,y,z,w,...$
  - $a,b,c,d,...$
- Además, para el caso de las anteriores estructuras vistas (posets, reticulados complementados, reticulados acotados, etc.), los términos y fórmulas elementales son obtenidos de forma análoga que el de reticulados complementados.

## Lenguaje elemental de los posets

- Solo está distinguida la relación binaria $\leq$.
- Los _términos elementales_ serán las variables y nombres de elementos fijos
- Las _fórmulas elementales_ son las siguientes, sean $t,s$ términos elementales y $\varphi_1,\varphi_2$ fórmulas elementales:

  - $(t=s)$
  - $(t\leq s)$
  - $(\varphi_1\wedge\varphi_2)$
  - $(\varphi_1\lor\varphi_2)$
  - $(\varphi_1\leftrightarrow\varphi_2)$
  - $(\varphi_1\to\varphi_2)$
  - $\neg\varphi_1$
  - $\forall x\varphi_1\ \forall y\varphi_1\ \forall z\varphi_1$
  - $\exists x\varphi_1\ \exists y\varphi_1\ \exists z\varphi_1$

  Y solo pueden obtenerse con estas reglas.

## Lenguaje elemental de los reticulados complementados

- Tenemos tres operaciones distinguidas, denotadas con $s,i,c$, y dos elementos distinguidos, denotados con $0,1$.
- Los _términos elementales_ son, sean $t,s$ términos elementales:

  - $0,1$
  - Cada variable
  - Cada nombre de elemento fijo
  - $c(t)$
  - $(t\ s\ s)$
  - $(t\ i\ s)$

  Y solo pueden obtenerse con estas reglas.

- Las _fórmulas elementales_ son las siguientes, sean $t,s$ términos elementales y $\varphi_1,\varphi_2$ fórmulas elementales:

  - $(t=s)$
  - $(\varphi_1\wedge\varphi_2)$
  - $(\varphi_1\lor\varphi_2)$
  - $(\varphi_1\leftrightarrow\varphi_2)$
  - $(\varphi_1\to\varphi_2)$
  - $\neg\varphi_1$
  - $\forall x\varphi_1\ \forall y\varphi_1\ \forall z\varphi_1$
  - $\exists x\varphi_1\ \exists y\varphi_1\ \exists z\varphi_1$

  Y solo pueden obtenerse con estas reglas.

## Lenguajes elementales de reticulados terna y reticulados acotados

- Es totalmente análogo a los casos anteriores.

## Lenguaje elemental de grafos

- Un **grafo** es un par $(G,r)$ donde $G$ es un conjunto no vacío y $r$ es una relación binaria sobre $G$ tal que:
  - $(x,x)\notin r,\ \forall x\in G$
  - Si $(x,y)\in r$, entonces $(y,x)\in r\ \forall x,y\in G$ (es decir, $r$ es una relación simétrica respecto a $G$ )
- Los elementos de $G$ son llamados los **vértices** de $(G,r)$.
- Cuando $(x,y)\in r$ diremos que $x$ e $y$ son **adyacentes** o **están conectados**.
- Dado un grafo $(G,r)$ y $x\in G$ la **valencia** de $x$ es el cardinal del conjunto $\{y:(x,y)\in r\}$
- Diremos que un subconjunto $S\subseteq G$ es un **clique** cuando se de que $(x,y)\in r$ cada vez que $x,y$ sean elementos distintos de $S$
- Dado $n\geq 2$, un $n$-ciclo de $(G,r)$ será una sucesión $x_1,x_2,...,x_n$ la cual cumple que:
  - $x_i\neq x_j\forall i\neq j$
  - $(x_i,x_{i+1})\in r\forall i=1,...,n-1$
  - $(x_n,x_1)\in r$
- Los _términos elementales de grafos_ serán las variables y los nombres de elementos fijos.
- Las _fórmulas elementales de grafos_ son, sean $t,s$ términos elementales y $\varphi_1,\varphi_2$ fórmulas elementales:

  - $(t=s)$
  - $r(t,s)$
  - $(\varphi_1\wedge\varphi_2)$
  - $(\varphi_1\lor\varphi_2)$
  - $(\varphi_1\leftrightarrow\varphi_2)$
  - $(\varphi_1\to\varphi_2)$
  - $\neg\varphi_1$
  - $\forall x\varphi_1\ \forall y\varphi_1\ \forall z\varphi_1$
  - $\exists x\varphi_1\ \exists y\varphi_1\ \exists z\varphi_1$

  Y solo pueden obtenerse con estas reglas.

## Lenguaje elemental de grafos bicoloreados

- Dado un grafo $(G,r)$, un **coloreo** de $(G,r)$ es una asignación de colores a cada elemento de $G$ de manera que nunca dos elementos de $G$ que estén relacionados tengan el mismo color.
  - En el caso que solo usemos _dos_ colores, le llamaremos un **bicoloreo** de $(G,r)$ y será un subconjunto $R$ de $G$ el cual cumple que $\forall x,y\in G,\ (x,y)\in r\Rightarrow (x\in R\wedge y\notin R)\lor (x\notin R\wedge y\in R)$
  - Un **grafo bicoloreado** es una terna $(G,r,R)$, donde $(G,r)$ es un grafo y $R$ es un bicoloreo de $(G,r)$
    - Pensaremos a $R$ como una _relación unaria_ tal que $R(x)$ expresa $x\in R$

## Lenguaje elemental de median algebras

- Una **median algebra** es un par $(A,M)$ donde $A$ es un conjunto no vacío, $M$ es una operación $3$-aria sobre $A$ (i.e. $M:A^3\to A$ ) y se cumplen:
  1. $M(x,y,z)=M(x,z,y)\ \forall x,y,z\in A$
  2. $M(x,y,z)=M(y,z,x)\ \forall x,y,z\in A$
  3. $M(x,x,y)=x\ \forall x,y\in A$
  4. $M(M(x,y,z),u,v)=M(x,M(y,u,v),M(z,u,v))\ \forall x,y,z,u,v\in A$
- Los _términos elementales de median algebras_ son, sean $t_1,t_2,t_3$ términos elementales:

  - Cada variable
  - Cada nombre de elemento fijo
  - $M(t_1,t_2,t_3)$

  Y solo pueden obtenerse con estas reglas.

- La definición de _fórmula elemental_ es análoga a las anteriores.

## Pruebas elementales

- Los _axiomas_ de las estructuras son:
  - **Posets**:
    1. $\forall x(x\leq x)$
    2. $\forall x\forall y\forall z((x\leq y\wedge y\leq z)\to x\leq z)$
    3. $\forall x\forall y((x\leq y\wedge y\leq x)\to x=y)$
  - **Reticulados terna**:
    1. $\forall x(x\ s\ x=x)$
    2. $\forall x(x\ i\ x=x)$
    3. $\forall x\forall y(x\ s\ y=y\ s\ x)$
    4. $\forall x\forall y(x\ i\ y=y\ i\ x)$
    5. $\forall x\forall y\forall z((x\ s\ y)\ s\ z=x\ s\ (y\ s\ z))$
    6. $\forall x\forall y\forall z((x\ i\ y)\ i\ z=x\ i\ (y\ i\ z))$
    7. $\forall x\forall y(x\ s\ (x\ i\ y) = x)$
    8. $\forall x\forall y(x\ i\ (x\ s\ y) = x)$
  - **Reticulados acotados**:
    1. $\forall x(x\ s\ x=x)$
    2. $\forall x(x\ i\ x=x)$
    3. $\forall x\forall y(x\ s\ y=y\ s\ x)$
    4. $\forall x\forall y(x\ i\ y=y\ i\ x)$
    5. $\forall x\forall y\forall z((x\ s\ y)\ s\ z=x\ s\ (y\ s\ z))$
    6. $\forall x\forall y\forall z((x\ i\ y)\ i\ z=x\ i\ (y\ i\ z))$
    7. $\forall x\forall y(x\ s\ (x\ i\ y)=x)$
    8. $\forall x\forall y(x\ i\ (x\ s\ y)=x)$
    9. $\forall x(0\ s\ x=x)$
    10. $\forall x(x\ s\ 1=1)$
  - **Reticulados complementados**:
    1. $\forall x(x\ s\ x=x)$
    2. $\forall x(x\ i\ x=x)$
    3. $\forall x\forall y(x\ s\ y=y\ s\ x)$
    4. $\forall x\forall y(x\ i\ y=y\ i\ x)$
    5. $\forall x\forall y\forall z((x\ s\ y)\ s\ z=x\ s\ (y\ s\ z))$
    6. $\forall x\forall y\forall z((x\ i\ y)\ i\ z=x\ i\ (y\ i\ z))$
    7. $\forall x\forall y(x\ s\ (x\ i\ y)=x)$
    8. $\forall x\forall y(x\ i\ (x\ s\ y)=x)$
    9. $\forall x(0\ s\ x=x)$
    10. $\forall x(x\ s\ 1=1)$
    11. $\forall x(x\ s\ c(x)=1)$
    12. $\forall x(x\ i\ c(x)=0)$
  - **Grafos**:
    1. $\forall x\ \neg r(x,x)$
    2. $\forall x\forall y(r(x,y)\to r(y,x))$
  - **Grafos bicoloreados**:
    1. $\forall x\ \neg r(x,x)$
    2. $\forall x\forall y(r(x,y)\to r(y,x))$
    3. $\forall x\forall y(r(x,y)\to ((R(x)\wedge\neg R(y))\lor (\neg R(x)\wedge R(y))))$
  - **Median algebras**:
    1. $\forall x\forall y\forall z(M(x,y,z)=M(x,z,y))$
    2. $\forall x\forall y\forall z(M(x,y,z)=M(y,z,x))$
    3. $\forall x\forall y(M(x,x,y)=x)$
    4. $\forall x\forall y\forall z\forall u\forall v(M(M(x,y,z),u,v))=M(x,M(y,u,v),M(z,u,v))$
- Las **pruebas elementales** deberán poseer las siguientes características:

  1. El enunciado a probar debe ser una sentencia elemental del tipo en cuestión (sin nombres de elementos fijos).
  2. En la prueba se parte de una estructura del tipo en cuestión, fija pero arbitraria en el sentido que lo único que sabemos es que ella satisface los axiomas elementales correspondientes y además esta es la única información particular que podemos usar.
  3. Las deducciones en la prueba son muy simples y obvias de justificar con mínimas frases en castellano
  4. En la escritura de la prueba lo concerniente a la matemática misma se expresa usando solo sentencias elementales del tipo de estructura en cuestión

  Dado que en una prueba se parte de una estructura fija de la que solo se asume que satisface los axiomas elementales, la sentencia elemental probada debe ser verdadera en todas las estructuras del tipo en cuestión.
