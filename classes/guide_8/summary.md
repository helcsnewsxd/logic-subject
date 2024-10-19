# Guía 8: _Lógica matemática_

## Programa de lógica matemática

- En las siguientes guías se completará el concepto de lógica matemática con el siguiente programa:
  1. Modelo matemático del concepto de fórmula elemental de tipo $\tau$ (guía 9)
  2. Definición matemática de cuándo una fórmula elemental de tpo $\tau$ es verdadera en una estructura de tipo $\tau$ para una asignación dada de valores a las variables libres y a los nombres de constantes fijas de la fórmula (Tarski)
  3. Modelo matemático del concepto de prueba elemental en una teoría elemental de tipo $\tau$. Estas serán las pruebas formales de tipo $\tau$ (Fregue)
  4. Prueba matemática de que el concepto de prueba formal de tipo $\tau$ es una correcta modelización matemática de la idea de prueba elemental en una teoría elemental de tipo $\tau$ (Teoremas de Corrección y Completitud de Godel)

Para ello, primero veremos los conceptos para entenderlo.

## Tipos

- Para cada tipo de estructuras se distinguen _tres conjuntos de símbolos_ (i.e., son de tipo _palabra_):

  - Un conjunto $\mathcal{C}$ formado por los símbolos que denotan genéricamente los elementos distinguidos de las estructuras
    - Sus elementos serán los _nombres de constante_
  - Un conjunto $\mathcal{F}$ formado por los símbolos que denotan genéricamente las operaciones de las estructuras
    - Sus elementos serán los _nombres de función_
  - Un conjunto $\mathcal{R}$ formado por los símbolos que denotan genéricamente las relaciones de las estructuras
    - Sus elementos serán los _nombres de relación_

  Para cada una de ellas, también nos importa su aridad, la cual será representada con $a:\mathcal{F}\cup\mathcal{R}\to N$.

  Por ejemplo:

  - _Posets_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\emptyset\quad\mathcal{R}=\{\leq\}\quad a=\{(\leq,2)\}$
  - _Reticulados terna_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\{s,i\}\quad\mathcal{R}=\emptyset\quad a=\{(s,2),(i,2)\}$
  - _Reticulados acotados_: $\mathcal{C}=\{0,1\}\quad \mathcal{F}=\{s,i\}\quad\mathcal{R}=\emptyset\quad a=\{(s,2),(i,2)\}$
  - _Reticulados complementados_: $\mathcal{C}=\{0,1\}\quad \mathcal{F}=\{s,i,c\}\quad\mathcal{R}=\emptyset\quad a=\{(s,2),(i,2),(c,1)\}$
  - _Reticulados cuaterna_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\{s,i\}\quad\mathcal{R}=\{\leq\}\quad a=\{(s,2),(i,2),(\leq,2)\}$
  - _Median algebras_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\{M\}\quad\mathcal{R}=\emptyset\quad a=\{(M,3)\}$
  - _Grafos_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\emptyset\quad\mathcal{R}=\{r\}\quad a=\{(r,2)\}$
  - _Grafos bicoloreados_: $\mathcal{C}=\emptyset\quad \mathcal{F}=\emptyset\quad\mathcal{R}=\{r,R\}\quad a=\{(r,2),(R,1)\}$

- Un **tipo (de primer orden)** es una $4$-upla $\tau=(\mathcal{C},\mathcal{F},\mathcal{R},a)$ tal que:

  1. Hay alfabetos finitos $\Sigma_1,\Sigma_2,\Sigma_3$ tales que:
     - $\mathcal{C}\subseteq\Sigma_1^+,\quad \mathcal{F}\subseteq\Sigma_2^+,\quad \mathcal{R}\subseteq\Sigma_3^+$
     - $\Sigma_i\neq\Sigma_j\forall i\neq j$
     - $\Sigma_1\cup\Sigma_2\cup\Sigma_3$ no contiene ningún símbolo de la lista $\forall\ \exists\ \neg\ \lor\ \wedge\ \to\ \leftrightarrow\ (\ )\ ,\ \equiv\ \mathsf{X}\ \textit{0}\ \textit{1}\ \dots\ \textit{9}\ \textbf{0}\ \textbf{1}\dots\ \textbf{9}$
  2. $a:\mathcal{F}\cup\mathcal{R}\to N$ y $\forall p\in\mathcal{F}\cup\mathcal{R},\ a(p)\in N$ y es la _aridad_ de $p$.
  3. Ninguna palabra de $\mathcal{C}$ (resp. $\mathcal{F,R}$) es _subpalabra propia_ de otra palabra de $\mathcal{C}$ (resp. $\mathcal{F,R}$).

  En base a esto, algunos ejemplos de tipos son:

  - _Tipo de los posets_: $(\emptyset,\emptyset,\{\leq\},\{(\leq,2)\})$
  - _Tipo de los reticulados terna_: $(\emptyset,\{s,i\},\emptyset,\{(s,2),(i,2)\})$
  - _Tipo de los reticulados acotados_: $(\{0,1\},\{s,i\},\emptyset,\{(s,2),(i,2)\})$
  - _Tipo de los reticulados complementados_: $(\{0,1\},\{s,i,c\},\emptyset,\{(s,2),(i,2),(c,1)\})$
  - _Tipo de los reticulados cuaterna_: $(\emptyset,\{s,i\},\{\leq\},\{(s,2),(i,2),(\leq,2)\})$
  - _Tipo de las median algebras_: $(\emptyset,\{M\},\emptyset,\{(M,3)\})$
  - _Tipo de los grafos_: $(\emptyset,\emptyset,\{r\},\{(r,2)\})$
  - _Tipo de los grafos bicoloreados_: $(\emptyset,\emptyset,\{r,R\},\{(r,2),(R,1)\})$

- Consideraremos **funciones y relaciones n-arias**:
  - $\mathcal{F}_n=\{f\in\mathcal{F}:a(f)=n\}$
  - $\mathcal{R}_n=\{r\in\mathcal{R}:a(r)=n\}$

## Estructuras de tipo $\tau$

- Sea $\tau$ un tipo, una **estructura o modelo de tipo** $\tau$ será un par $\textbf{A}=(A,i)$ tal que:

  1. $A\neq\emptyset$
  2. $i$ es una función con dominio $\mathcal{C}\cup\mathcal{F}\cup\mathcal{R}$ tal que:
     1. $\forall c\in\mathcal{C},\ i(c)\in A$
     2. $\forall f\in\mathcal{F}_n\ (n\geq 1),\ i(f)$ es una operación $n$-aria
     3. $\forall r\in\mathcal{R}_n\ (n\geq 1),\ i(r)$ es una relación $n$-aria

  En este caso, $A$ es llamado el **universo** de $\textbf{A}$, e $i$ la **función interpretación** de $\mathbf{A}$ (diremos que $i(s)$ es la intepretación de $s$ en $\mathbf{A}$ ).

## Fórmulas elementales de tipo $\tau$

- Dado un tipo $\tau=(\mathcal{C,F,R},a)$, los **términos elementales de tipo** $\tau$ son, sean $t_1,\dots,t_n$ términos elementales de tipo $\tau$:

  1. Cada palabra de $\mathcal{C}$
  2. Cada variable
  3. Cada nombre de elemento fijo
  4. $f(t_1,\dots,t_n)\ \forall f\in\mathcal{F}_n\ (n\geq 1)$

  Y solo pueden obtenerse con estas reglas.

- Las **fórmulas elementales de tipo** $\tau$ son, sean $t_1,\dots,t_n$ términos elementales de tipo $\tau$ y $\varphi_1,\varphi_2$ fórmulas elementales de tipo $\tau$:

  1. $(t=s)$
  2. $r(t_1,\dots,t_n)\ \forall r\in\mathcal{R_n}\ (n\geq 1)$
  3. $(\varphi_1\wedge\varphi_2)$
  4. $(\varphi_1\lor\varphi_2)$
  5. $(\varphi_1\leftrightarrow\varphi_2)$
  6. $(\varphi_1\to\varphi_2)$
  7. $\neg\varphi_1$
  8. $\forall x\varphi_1\quad\forall y\varphi_1\quad\forall z\varphi_1\quad\dots$
  9. $\exists x\varphi_1\quad\exists y\varphi_1\quad\exists z\varphi_1\quad\dots$

  Y solo pueden obtenerse con estas reglas.

- Una **sentencia elemental de tipo** $\tau$ es una fórmula elemental de tipo $\tau$ que no tiene variables libres.
- _Valores de términos y fórmulas para una estructura dada_:
  - Dada un estructura $(A,i)$ de tipo $\tau$ y un término $t$ de tipo $\tau$, para que $t$ represente un valor de $A$, tenemos que asignarles valores concretos de $A$ a las variables libres y a los nombres de elementos fijos que figuran en $t$.
  - Dada una estructura $(A,i)$ y una fórmula elemental $\varphi$ de tipo $\tau$, para que $\varphi$ sea verdadera o falsa tenemos que asignarles valores concretos de $A$ a las variables libres y a los nombres de elementos fijos que figuran en $\varphi$, y luego a los nombres de $\mathcal{C}\cup\mathcal{F}\cup\mathcal{R}$ los interpretaremos usando la función $i$.

## Teorías y pruebas elementales

### Teorías elementales

- Una **teoría elemental** es un par $(\Sigma,\tau)$ al que $\tau$ es un tipo cualquiera y $\Sigma$ es un conjunto de sentencias elementales de tipo $\tau$, las cuales no tienen nombres de elementos fijos.

  Algunos ejemplos son:

  - _Teoría elemental de los posets_: par $(\Sigma,\tau)$ donde $\tau=(\emptyset,\emptyset,\{\leq\},\{(\leq,2)\})$ y $\Sigma$ es el conjunto formado por las siguientes tres sentencias elementales de tipo $\tau$:
    1. $\forall x\ \leq(x,x)$
    2. $\forall x\forall y\forall z\ ((\leq(x,y)\wedge\leq(y,z))\to\leq(x,z))$
    3. $\forall x\forall y\ ((\leq(x,y)\wedge\leq(y,x))\to x=y)$
  - _Teoría elemental de lo reticulados terna_: par $(\Sigma,\tau)$ donde $\tau=(\emptyset,\{s,i\},\emptyset,\{(s,2),(i,2)\})$ y $\Sigma$ es el conjunto formado por las siguientes sentencias elementales de tipo $\tau$:
    1. $\forall x\ (s(x,x)=x)$
    2. $\forall x\ (i(x,x)=x)$
    3. $\forall x\forall y\ (s(x,y)=s(y,x))$
    4. $\forall x\forall y\ (i(x,y)=i(y,x))$
    5. $\forall x\forall y\forall z\ (s(s(x,y),z)=s(x,s(y,z)))$
    6. $\forall x\forall y\forall z\ (i(i(x,y),z)=i(x,i(y,z)))$
    7. $\forall x\forall y\ (s(x,i(x,y))=x)$
    8. $\forall x\forall y\ (i(x,s(x,y))=x)$
  - _Teoría elemental de los reticulados cuaterna_: par $(\Sigma,\tau)$ donde $\tau=(\emptyset,\{s,i\},\{\leq\},\{(s,2),(i,2),(\leq,2)\})$ y $\Sigma$ es el conjunto formado por las siguientes sentencias elementales de tipo $\tau$:
    1. $A_{\leq R}=\forall x\ \leq(x,x)$
    2. $A_{\leq T}=\forall x\forall y\forall z\ ((\leq(x,y)\wedge\leq(y,z))\to\leq(x,z))$
    3. $A_{\leq A}=\forall x\forall y\ ((\leq(x,y)\wedge\leq(y,x))\to x=y)$
    4. $A_{s\text{ es }C}=\forall x\forall y\ (\leq(x,s(x,y))\wedge\leq(y,s(x,y)))$
    5. $A_{s\leq C}=\forall x\forall y\forall z\ ((\leq(x,z)\wedge\leq(y,z))\to\leq(s(x,y),z))$
    6. $A_{i\text{ es }C}=\forall x\forall y\ (\leq(i(x,y),x)\wedge\leq(i(x,y),y))$
    7. $A_{i\geq C}=\forall x\forall y\forall z\ ((\leq(z,x)\wedge\leq(z,y))\to\leq(z,i(x,y)))$
  - _Teoría elemental de los grafos_: par $(\Sigma,\tau)$ donde $\tau=(\emptyset,\emptyset,\{r\},\{(r,2)\})$ y $\Sigma$ es el conjunto formado por las siguientes sentencias elementales de tipo $\tau$:
    1. $\forall x\ \neg r(x,x)$
    2. $\forall x\forall y\ (r(x,y)\to r(y,x))$
  - _Teoría elemental de los grafos bicoloreados_: par $(\Sigma,\tau)$ donde $\tau=(\emptyset,\emptyset,\{r,R\},\{(r,2),(R,1)\})$ y $\Sigma$ es el conjunto formado por las siguientes sentencias elementales de tipo $\tau$:
    1. $\forall x\ \neg r(x,x)$
    2. $\forall x\forall y\ (r(x,y)\to r(y,x))$
    3. $\forall x\forall y\ (r(x,y)\to((R(x)\wedge\neg R(y))\lor(\neg R(x)\wedge R(y))))$

- Un **modelo de** $(\Sigma,\tau)$ es una estructura de tipo $\tau$, la cual hace verdaderos a todos los elementos de $\Sigma$.

### Pruebas elementales

- Dada una teoría elemental $(\Sigma,r)$ y una sentencia elemental $\varphi$ la cual no posea nombres de elementos fijos, una **prueba elemental de** $\varphi$ **en** $(\Sigma,r)$ será una prueba de $\varphi$ que posea las siguientes características:
  1. En la prueba se parte de una estructura de tipo $\tau$, fija pero arbitraria en el sentido que lo único que sabemos es qu ellas satisface los axiomas de $\Sigma$ (i.e. es un modelo de $(\Sigma,r)$ ) y además esta es la única información particular que podemos usar.
  2. Las deducciones en la prueba son muy simples y obvias de justificar con mínimas frases en castellano.
  3. En la escritura de la prueba lo concerniente a la matemática misma se expresa usando solo sentencias elementales de tipo $\tau$
