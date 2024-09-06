# Guía 2: Posets e isomorfismos

## Órdenes parciales

- **Orden parcial**: una relación binaria $R$ sobre un conjunto $A$ es un orden parcial sobre $A$ si es reflexiva, transitiva y antisimétrica respecto de $A$.
  - El orden parcial se denota con $\leq$
  - $\lt=\{(a,b)\in A^2:a\leq b\wedge a\neq b\}$
  - **Cubrir**: $\prec=\{(a,b)\in A^2:a\lt b\wedge\nexists z|a\lt z\lt b\}$
    - Cuando se de $a\prec b$, diremos que $b$ cubre a $a$ (respecto de $\leq$ ).
  - **Tapar**: Dado un poset $(P,\leq)$ y $a,b\in P$, diremos que $b$ tapa a $a$ cuando $a\lt b\wedge b\leq c\forall c\in P:a\leq c$
    - Si $b$ tapa a $a$, entonces $b$ cubre a $a$. _Pero no se cumple la recíproca_
  - **Poset denso**: un poset $(P,\leq)$ es denso si $\forall a,b\in P:a\lt b\Rightarrow\exists c\in P:a\lt c\wedge c\lt b$
- **Orden total**: un orden total sobre $A$ es un orden parcial $\leq$ sobre $A$ que cumple $x\leq y\lor y\leq x\forall x,y\in A$.
- **Poset (conjunto parcialmente ordenado)**: Un poset es un par $(P,\leq)$ donde $P$ es un conjunto no vacío y $\leq$ es un orden parcial sobre $P$
- **Conjunto totalmente ordenado**: es un par $(P,\leq)$ donde $P$ es un conjunto no vacío y $\leq$ es un orden total sobre $P$
  - Todo conjunto totalmente ordenado es un poset

## Diagramas de Hasse

- Dado un poset $(P,\leq)$ con $P$ finito, el diagrama de Hasse se hace siguiendo estas instrucciones:
  1. Asociar en forma inyectiva a cada $a\in P$ un punto $p_a$ del plano
  2. Trazar un segmento de recta uniendo los puntos $p_a$ y $p_b$, cada vez que $a\prec b$
  3. Realizar lo indicado en los puntos (1) y (2) en tal forma que
     1. Si $a\prec b$, entonces $p_a$ está por debajo de $p_b$
     2. Si un punto $p_a$ ocurre en un segmento del diagrama, entonces lo hace en alguno de sus extremos

## Elementos maximales, máximos, minimales y mínimos

- **Máximo y mínimo**: Sea $(P,\leq)$ un poset, diremos que $a\in P$ es un elemento máximo de $(P,\leq)$ si $b\leq a\forall b\in P$. Análogamente se define el mínimo.
  - Hay a lo sumo un máximo o mínimo (pero puede no haber)
  - El máximo se denota con $1$ y el mínimo con $0$.
- **Maximal y minimal**: Sea $(P,\leq)$ un poset, diremos que $a\in P$ es un elemento maximal de $(P,\leq)$ si $\nexists b\in P:a\lt b$. De forma análoga se define el minimal.
  - No siempre hay maximales o minimales en un poset
  - Todo máximo (resp. mínimo) es un elemento maximal (resp. minimal) del poset
  - Si un poset no tiene elementos maximales, entonces es infinito

## Supremos e ínfimos

### Supremos

- **Cota superior**: Sea $(P,\leq)$ un poset y dado $S\subseteq P$, diremos que $a\in P$ es cota superior de $S$ en $(P,\leq)$ cuando $b\leq a\forall b\in S$.
- **Supremo**: Un elemento $a\in P$ es supremo de $S$ en $(P,\leq)$ cuando:
  1. $a$ es cota superior de $S$ en $(P,\leq)$
  2. $\forall b\in P$, si $b$ es cota superior de $S$ en $(P,\leq)$, entonces $a\leq b$
  - Se denotará, en caso que exista, con $sup(S)$
  - _Propiedades_:
    - Hay a lo sumo un supremo (no siempre existe)
    - En caso de existir, $sup(\emptyset)$ en $(P,\leq)$ es el mínimo de $(P,\leq)$
    - Si $a=sup(S)$, entonces $a=sup(S\cup\{a\})$
    - Si $a\in P$, entonces $a$ es máximo de $(P,\leq)\iff a=sup(P)$
    - Sea $S\subseteq P$ y $b\in P$, si $a=sup(S)$ y existe $sup(\{a,b\})$, entonces $sup(S\cup\{b\})=sup(\{a,b\})$
  - _Ejemplo de supremo_: Considerando el poset $(\mathbb{N},D)$ donde $D=\{(x,y)\in\mathbb{N}^2:x|y\}$, dados $x,y\in\mathbb{N}$, se tiene que $mcm(x,y)$ es el supremo de $\{x,y\}$ en $(\mathbb{N}, D)$

### Ínfimos

- **Cota inferior**: Sea $(P,\leq)$ un poset, dado $S\subseteq P$, diremos que un elemento $a\in P$ es cota inferior de $S$ en $(P,\leq)$ cuando $a\leq b\forall b\in S$.
- **Ínfimo**: Un elemento $a\in P$ será llamado ínfimo de $S$ en $(P,\leq)$ cuando:
  1. $a$ es cota inferior de $S$ en $(P,\leq)$
  2. $\forall b\in P$, si $b$ es cota inferior de $S$ en $(P,\leq)$, entonces $b\leq a$
  - Se denotará, en caso de que exista, $inf(S)$
  - _Propiedades_:
    - Hay a lo sumo un ínfimo (no siempre existe)
    - En caso de existir, el ínfimo de $\emptyset$ es el máximo del poset
  - _Ejemplo de ínfimo_: Sea el poset $(\mathbb{N}, D)$ donde $D=\{(x,y)\in\mathbb{N}^2:x|y\}$, dados $x,y\in\mathbb{N}$ se tiene que $mcd(x,y)$ es el ínfimo de $\{x,y\}$ en $(\mathbb{N}, D)$

## Homomorfismos e isomorfimos

- **Homomorfismo**: Sean $(P,\leq)$ y $(P',\leq')$ posets, una función $F:P\to P'$ será llamada homomorfismo de $(P,\leq)$ en $(P',\leq')$ si $\forall x,y\in P$ se cumple que $x\leq y\Rightarrow F(x)\leq' F(y)$.
  - Escribiremos $F:(P,\leq)\to(P',\leq')$ para expresar que $F$ es un homomorfismo de $(P,\leq)$ en $(P',\leq')$
  - _Propiedades_: Suponiendo que $F$ es suryectiva, entonces
    - Si $(P,\leq)$ es un conjunto totalmente ordenado, $(P',\leq')$ también lo es
    - Si $(P,\leq)$ tiene un elemento máximo/mínimo, entonces $(P',\leq')$ también
- **Isomorfismo**: Una función $F:P\to P'$ será llamada un isomorfismo de $(P,\leq)$ en $(P',\leq')$ si $F$ es biyectiva, $F$ es un homomorfismo de $(P,\leq)$ en $(P',\leq')$ y $F^{-1}$ es un homomorfismo de $(P',\leq')$ en $(P,\leq)$.
  - Escribiremos $(P,\leq)\cong (P',\leq')$ cuando exista un isomorfismo entre $(P,\leq), (P',\leq')$ y, en este caso, diremos que son isomorfos
- _Propiedades_:
  - **Lema (isomorfismos conservan todas las propiedades matemáticas)**: Sean $(P,\leq),(P',\leq')$ posets y $F$ un isomorfismo de $(P,\leq)$ en $(P',\leq')$:
    - $\forall x,y\in P, x\lt y\iff F(x)\lt' F(y)$
    - $\forall x\in P$, $x$ es máximo (resp. mínimo) de $(P,\leq)$ $\iff$ $F(x)$ es máximo (resp. mínimo) de $(P',\leq')$
    - $\forall x\in P$, $x$ es maximal (resp. minimal) en $(P,\leq)\iff F(x)$ es maximal (resp. minimal) en $(P',\leq')$
    - $\forall x,y,z\in P,z=sup\{x,y\}\iff F(z)=sup\{F(x),F(y)\}$
    - $\forall x,y,z\in P,z=inf\{x,y\}\iff F(z)=inf\{F(x),F(y)\}$
    - $\forall x,y\in P,x\prec y\iff F(x)\prec' F(y)$
      - Esto garantiza que si dos posets finitos son isomorfos, entonces pueden representarse con el mismo diagrama de Hasse
  - El isomorfismo conserva las siguientes propiedades:
    - Que el poset sea denso
    - La cantidad de máximos/mínimos/maximales/minimales
    - $x$ es tapado por $y\iff$ $F(x)$ es tapado por $F(y)$
