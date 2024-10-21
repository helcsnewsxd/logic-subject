---
geometry: margin=3cm
---

# Guía 10: _Modelo matemático del valor de verdad de una fórmula_

## El valor de un término en una estructura

- Sea $\mathbf{A}=(A,i)$ una estructura de tipo $\tau$. Una **asignación de** $\mathbf{A}$ será un elemento de $A^N=\{\text{infinituplas de elementos de }A\}$.
- Si $\vec{a}=(a_1,a_2,\dots)$ es una asignación, entonces diremos que $a_j$ es el **valor** que $\vec{a}$ le asigna a la variable $x_j$.
- Dada una estructura $\mathbf{A}$ de tipo $\tau$, un término $t\in T^\tau$ y una asignación $\vec{a}=(a_1,a_2,\dots)\in A^N$ definamos recursivamente $t^\mathbf{A}[\vec{a}]$ de la siguiente manera:
  1. Si $t=x_i\in Var$, entonces $t^\mathbf{A}[\vec{a}]=a_i$
  2. Si $t=c\in\mathcal{C}$, entonces $t^\mathbf{A}[\vec{a}]=i(c)$
  3. Si $t=f(t_1,\dots,t_n)$, con $f\in\mathcal{F}_n,\ n\geq 1,\ t_1,\dots,t_n\in T^\tau$, entonces $t^\mathbf{A}[\vec{a}]=i(f)(t_1^\mathbf{A}[\vec{a}],\dots,t_n^\mathbf{A}[\vec{a}])$
- El elemento $t^\mathbf{A}[\vec{a}]$ será llamado el **valor de** $t$ **en la estructura** $\mathbf{A}$ **para la asignación** $\vec{a}$.
- Dada una asignación $\vec{a}\in A^N$ y $a\in A$, con $\downarrow_i^a(\vec{a})$ denotaremos la asignación que resulta de reemplazar en $\vec{a}$ el $i$-ésimo elemento por $a$.
- _Propiedades_:
  - Sea $\mathbf{A}$ una estructura de tipo $\tau$ y sea $t\in T^\tau$. Supongamos que $\vec{a},\vec{b}$ son asignaciones tales que $a_i=b_i$, cada vez que $x_i$ ocurra en $t$. Entonces $t^\mathbf{A}[\vec{a}]=t^\mathbf{A}[\vec{b}]$
  - Sea $\tau$ un tipo, $t\in T^\tau$ y $t'$ el resultado de reemplazar toda ocurrencia de $x_i$ en $t$ por $x_l$, la cual no ocurre en $t$. Entonces para cualquier estructura $\mathbf{A}$, cualquier asignación $\vec{a}\in A^N$ y cualquier $a\in A$, se tiene que $t'^\mathbf{A}[\downarrow_l^a(\vec{a})]=t^\mathbf{A}[\downarrow_i^a(\vec{a})]$

## La relación $\models$

- Definiremos recursivamente la relación $\mathbf{A}\models\varphi[\vec{a}]$, donde $\mathbf{A}$ es una estructura de tipo $\tau$, $\vec{a}$ es una asignación y $\varphi\in F^\tau$. Escribiremos $\mathbf{A}\not\models\varphi[\vec{a}]$ para expresar que no se da $\mathbf{A}\models\varphi[\vec{a}]$.
  1. Si $\varphi=(t\equiv s)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff t^\mathbf{A}[\vec{a}]=s^\mathbf{A}[\vec{a}]$
  2. Si $\varphi=r(t_1,\dots,t_m)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff(t_1^\mathbf{A}[\vec{a}],\dots,t_m^\mathbf{A}[\vec{a}])\in i(r)$
  3. Si $\varphi=(\varphi_1\wedge\varphi_2)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\models\varphi_1[\vec{a}]$ y $\mathbf{A}\models\varphi_2[\vec{a}]$
  4. Si $\varphi=(\varphi_1\lor\varphi_2)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\models\varphi_1[\vec{a}]$ y $\mathbf{A}\models\varphi_2[\vec{a}]$
  5. Si $\varphi=(\varphi_1\to\varphi_2)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\not\models\varphi_1[\vec{a}]$ y $\mathbf{A}\models\varphi_2[\vec{a}]$
  6. Si $\varphi=(\varphi_1\leftrightarrow\varphi_2)$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff$ ya sea se dan $\mathbf{A}\models\varphi_1[\vec{a}]$ y $\mathbf{A}\models\varphi_2[\vec{a}]$ o se dan $\mathbf{A}\not\models\varphi_1[\vec{a}]$ y $\mathbf{A}\not\models\varphi_2[\vec{a}]$
  7. Si $\varphi=\neg\varphi_1$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\not\models\varphi_1[\vec{a}]$
  8. Si $\varphi=\forall x_i\varphi_1$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff$ para cada $a\in A$ se da que $\mathbf{A}\models\varphi_1[\downarrow_i^a(\vec{a})]$
  9. Si $\varphi=\exists x_i\varphi_1$, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff$ hay un $a\in A$ tal que $\mathbf{A}\models\varphi_1[\downarrow_i^a(\vec{a})]$
- Cuando se de $\mathbf{A}\models\varphi[\vec{a}]$ diremos que la estructura $\mathbf{A}$ satisface $\varphi$ en la asignación $\vec{a}$ y en tal caso diremos que $\varphi$ es verdadera en $\mathbf{A}$ para la asignación $\vec{a}$. Cuando no se de $\mathbf{A}\models\varphi[\vec{a}]$ diremos que la estructura $\mathbf{A}$ no satisface $\varphi$ en la asignación $\vec{a}$ y en tal caso diremos que $\varphi$ es falsa en $\mathbf{A}$ para la asignación $\vec{a}$.
  - También hablaremos del **valor de verdad** de $\varphi$ en $\mathbf{A}$ para la asignación $\vec{a}$ el cual será igual a $1$ si se da $\mathbf{A}\models\varphi[\vec{a}]$ y $0$ en caso contrario.
- _Propiedades_:
  - Sea $\mathbf{A}$ una estructura de tipo $\tau$, $\vec{a}$ una asignación y $\varphi\in F^\tau$. Entonces no puede suceder que $\mathbf{A}\models\varphi[\vec{a}]$ y $\mathbf{A}\models\neg\varphi[\vec{a}]$.
    - En particular, esto nos dice que $\mathbf{A}\not\models(\varphi\wedge\neg\varphi)[\vec{a}]$ y que se da ya sea $\mathbf{A}\models\varphi[\vec{a}]$ o $\mathbf{A}\models\neg\varphi[\vec{a}]$
  - Supongamos que $\vec{a},\vec{b}$ son asignaciones tales que si $x_i\in Li(\varphi)$, entonces $a_i=b_i$. Entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\models\varphi[\vec{b}]$
  - Si $\varphi$ es una sentencia, entonces $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\models\varphi[\vec{b}]$, cualesquiera sean las asignaciones $\vec{a},\vec{b}$.
    - En base a esto, el valor de verdad de una sentencia $\varphi$ en una estructura dada $\mathbf{A}$ para una asignación $\vec{a}$ no depende de $\vec{a}$. Es decir, tiene el mismo valor para todas las asignaciones.
    - En estos casos podemos definir que $\varphi$ es **verdadera** en $\mathbf{A}$ (y escribiremos $\mathbf{A}\models\varphi$ ), o que $\varphi$ es **falsa** en $\mathbf{A}$ (y escribiremos $\mathbf{A}\not\models\varphi$ )
    - Una sentencia de tipo $\tau$ será llamada **universalmente válida** si es verdadera en cada modelo de tipo $\tau$.
  - Sean $\varphi,\phi,\psi$ sentencias de tipo $\tau$, las siguientes son universalmente válidas:
    1. $\forall x_1\exists x_2(x_1\equiv x_2)$
    2. $(\varphi\to(\psi\to\varphi))$
    3. $(((\varphi\to\psi)\wedge(\varphi\to(\psi\to\phi)))\to(\varphi\to\phi))$
    4. _Strong responsability property_: $(((\varphi\wedge\psi)\to\phi))\to((\varphi\to\phi)\lor(\psi\to\phi))$

## Equivalencia de fórmulas

- Dadas $\varphi,\psi\in F^\tau$ diremos que $\varphi$ y $\psi$ son **equivalentes** cuando se de la siguiente condición: $\mathbf{A}\models\varphi[\vec{a}]\iff\mathbf{A}\models\psi[\vec{a}]$ para cada modelo de tipo $\tau,\mathbf{A}$ y cada $\vec{a}\in A^N$
  - Escribiremos $\varphi\sim\psi$ cuando $\varphi$ y $\psi$ sean equivalentes
  - Nótese que $\{(\varphi,\psi)\in F^\tau\times F^\tau:\varphi\sim\psi\}$ es una relación de equivalencia sobre $F^\tau$
- _Propiedades_:
  - Si $Li(\phi)\cup Li(\psi)\subseteq\{x_{i_1},\dots,x_{i_n}\}$, entonces $\phi\sim\psi\iff$ la sentencia $\forall x_{i_1}\dots\forall x_{i_n}(\phi\leftrightarrow\psi)$ es universalmente válida.
  - Si $\phi_i\sim\psi_i,\ i=1,2$, entonces $\neg\phi_1\sim\neg\psi_1,\ (\phi_1\eta\phi_2)\sim(\psi_1\eta\psi_2)$ y $Qv\phi_1\sim Qv\psi_1$
  - Si $\phi\sim\psi$ y $\alpha'$ es el resultado de reemplazar en una fórmula $\alpha$ algunas (posiblemente 0) ocurrencias de $\phi$ por $\psi$, entonces $\alpha\sim\alpha'$.
  - Sea $\tau$ un tipo. Para $\varphi\in F^\tau$, si $\varphi'=$ resultado de reemplazar en $\varphi$ toda ocurrencia de $\forall x_1\forall x_2\exists$ por $\forall x_2\forall x_1\exists$, entonces $\varphi'\sim\varphi$
  - Sea $\tau$ un tipo. Sea $\alpha\in F^\tau$, si $\alpha'$ es el resultado de remover de $\alpha$ una ocurrencia de la palabra $\neg\neg$ entonces $\alpha'$ es equivalente a $\alpha$.

## Homomorfismos

- Dado un modelo de tipo $\tau,\ \mathbf{A}=(A,i),\ \forall s\in\mathcal{C}\cup\mathcal{F}\cup\mathcal{R}$, usaremos $s^\mathbf{A}$ para denotar a $i(s)$
- Sean $\mathbf{A}$ y $\mathbf{B}$ modelos de tipo $\tau$, una función $F:A\to B$ será un **homomorfismo** de $\mathbf{A}$ en $\mathbf{B}$ si se cumplen las siguientes:
  1. $F(c^\mathbf{A})=c^\mathbf{B}\ \forall c\in\mathcal{C}$
  2. $F(f^\mathbf{A}(a_1,\dots,a_n))=f^\mathbf{B}(F(a_1),\dots,F(a_n))\ \forall f\in\mathcal{F}_n,\ a_1,\dots,a_n\in A$
  3. $(a_1,\dots,a_n)\in r^\mathbf{A}$ implica $(F(a_1),\dots,F(a_n))\in r^\mathbf{B},\ \forall r\in\mathcal{R}_n,\ a_1,\dots,a_n\in A$
- Un **isomorfismo** de $\mathbf{A}$ en $\mathbf{B}$ es un homomorfismo de $\mathbf{A}$ en $\mathbf{B}$ si es biyectivo y su inversa es un homomorfismo de $\mathbf{B}$ en $\mathbf{A}$.
  - Diremos que $F:\mathbf{A}\to\mathbf{B}$ es un homomorfismo para expresar que $F$ es un _homomorfismo_ de $\mathbf{A}$ en $\mathbf{B}$
  - Diremos que $F:\mathbf{A}\to\mathbf{B}$ es un isomorfismo para expresar que $F$ es un _isomorfismo_ de $\mathbf{A}$ en $\mathbf{B}$
  - Diremos que los modelos $\mathbf{A,B}$ son _isomorfos_ ( $\mathbf{A\cong\mathbf{B}}$ ) cuando haya un isomorfismo $F$ de $\mathbf{A}$ en $\mathbf{B}$
- _Propiedades_:
  - Supongamos $\mathcal{R}=\emptyset$. Sea $F:\mathbf{A}\to\mathbf{B}$ un homomorfismo biyectivo. Entonces $F$ es un isomorfismo.
  - Sea $F:\mathbf{A}\to\mathbf{B}$ un homomorfismo. Entonces $F(t^\mathbf{A}[(a_1,a_2,\dots)]=t^\mathbf{B}[(F(a_1),F(a_2),\dots)])$ para cada $t\in T^\tau,\ (a_1,a_2,\dots)\in A^N$
  - Supongamos que $F:\mathbf{A}\to\mathbf{B}$ es un isomorfismo. Sea $\varphi\in F^\tau$, entonces $A\models\varphi[(a_1,a_2,\dots)]\iff\mathbf{B}\models\varphi[(F(a_1),F(a_2),\dots)]$ para cada $(a_1,a_2,\dots)\in A^N$.
    - En particular $\mathbf{A}$ y $\mathbf{B}$ satisfacen las mismas sentencias de tipo $\tau$.
