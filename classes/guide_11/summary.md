# Guía 11:

## Notación declaratoria para términos

- Si $t$ es un término de tipo $\tau$, entonces escribiremos $t=_d t(v_1,\dots,v_n)$ para declarar que $v_1,\dots,v_n$ son variables distintas (con $n\geq 1$ ) y tales que toda variable que ocurre en $t$ pertenece a $\{v_1,\dots,v_n\}$ (no necesariamente $v_j$ debe ocurrir en $t$ ).

## Notación declaratoria para fórmulas

- Si $\varphi$ es una fórmula de tipo $\tau$, entonces escribiremos $\varphi=_d \varphi(v_1,\dots,v_n)$ para declarar que $v_1,\dots,v_n$ son variables distintas (con $n\geq 1$ ) y tales que $Li(\varphi)\subseteq\{v_1,\dots,v_n\}$

## Elementos definibles

- Sea $A$ un modelo de tipo $\tau$, diremos que un elemento $a$ de $A$ es **definible** en $\mathbf{A}$ si hay una fórmula $\varphi=_d\varphi(v)$ tal que $\mathbf{A}\models\varphi[a]$ y para cada $b\in A-\{a\}$ se tiene que $\mathbf{A}\not\models\varphi[b]$
  - Es decir, $a$ es el único elemento de $A$ que cumple $\mathbf{A}\models\varphi[a]$
  - En este caso, además, diremos que $\varphi$ **define** $a$ en $\mathbf{A}$
- Si $\mathbf{A}$ es un modelo de tipo $\tau$ y $a\in A$ es tal que $F(a)\neq a$, para algún isomorfismo $F:\mathbf{A}\to\mathbf{A}$, entonces $a$ **no es definible** en $\mathbf{A}$

## Manejo técnico de la notación declaratoria

- _Lectura única de términos declarados_: Sea $\tau$ un tipo cualquiera y supongamos $t\in T^\tau$, si $t=_d t(v_1,\dots,v_n)$, entonces se da una y solo una de las siguientes:
  1. $t=c$ para algún $c\in\mathcal{C}$
  2. $t=v_j$ para algún $j$
  3. $t=f(t_1,\dots,t_m)$ con $f\in\mathcal{F}_m$, $t_1,\dots,t_m\in T^\tau$ únicos
- _Carácter recursivo de la notación_ $t^\mathbf{A}[a_1,\dots,a_n]$: Sea $\tau$ un tipo cualquiera, $t\in T^\tau$, $t=_d t(v_1,\dots,v_n)$, $\mathbf{A}$ un modelo de tipo $\tau$ y $a_1,\dots,a_n\in A$, se tiene que:
  1. Si $t=c$, entonces $t^\mathbf{A}[a_1,\dots,a_n]=c^\mathbf{A}$
  2. Si $t=v_j$, entonces $t^\mathbf{A}[a_1,\dots,a_n]=a_j$
  3. Si $t=f(t_1,\dots,t_m)$ con $f\in\mathcal{F}_m$ y $t_1,\dots,t_m\in T^\tau$, entonces $t^\mathbf{A}[a_1,\dots,a_n]=f^\mathbf{A}(t_1^\mathbf{A}[a_1,\dots,a_n],\dots,t_m^\mathbf{A}[a_1,\dots,a_n])$
- _Lectura única de fórmulas declaradas_: Sea $\tau$ un tipo cualquiera, $\varphi\in F^\tau$ y $\varphi=_d\varphi(v_1,\dots,v_n)$, entonces se da una y solo una de las siguientes:
  1. $\varphi=(t\equiv s)$, con $t,s\in T^\tau$ únicos
  2. $\varphi=r(t_1,\dots,t_m)$, con $r\in\mathcal{R}_m$ y $t_1,\dots,t_m\in T^\tau$ únicos
  3. $\varphi=(\varphi_1\wedge\varphi_2)$, con $\varphi_1,\varphi_2\in F^\tau$ únicas
  4. $\varphi=(\varphi_1\lor\varphi_2)$, con $\varphi_1,\varphi_2\in F^\tau$ únicas
  5. $\varphi=(\varphi_1\to\varphi_2)$, con $\varphi_1,\varphi_2\in F^\tau$ únicas
  6. $\varphi=(\varphi_1\leftrightarrow\varphi_2)$, con $\varphi_1,\varphi_2\in F^\tau$ únicas
  7. $\varphi=\neg\varphi_1$, con $\varphi_1\in F^\tau$ única
  8. $\varphi=\forall v_j\varphi_1$, con $v_j\in\{v_1,\dots,v_n\}$ y $\varphi_1\in F^\tau$ únicas
  9. $\varphi=\forall v\varphi_1$, con $v\in Var-\{v_1,\dots,v_n\}$ y $\varphi_1\in F^\tau$ únicas
  10. $\varphi=\exists v_j\varphi_1$, con $v_j\in\{v_1,\dots,v_n\}$ y $\varphi_1\in F^\tau$ únicas
  11. $\varphi=\exists v\varphi_1$, con $v\in Var-\{v_1,\dots,v_n\}$ y $\varphi_1\in F^\tau$ únicas
- _Carácter recursivo de la notación_ $\mathbf{A}\models\varphi[a_1,\dots,a_n]$: Sea $\varphi=_d\varphi(v_1,\dots,v_n),\mathbf{A}=(A,i)$ un modelo de tipo $\tau$ y sean $a_1,\dots,a_n\in A$, entonces:
  1. Si $\varphi=(t\equiv s)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $t^\mathbf{A}[a_1,\dots,a_n]=s^\mathbf{A}[a_1,\dots,a_n]$
  2. Si $\varphi=r(t_1,\dots,t_m)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $(t_1^\mathbf{A}[a_1,\dots,a_n],\dots,t_m^\mathbf{A}[a_1,\dots,a_n])\in r^\mathbf{A}$
  3. Si $\varphi=(\varphi_1\wedge\varphi_2)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a_n]$ y $\mathbf{A}\models\varphi_2[a_1,\dots,a_n]$
  4. Si $\varphi=(\varphi_1\lor\varphi_2)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a_n]$ o $\mathbf{A}\models\varphi_2[a_1,\dots,a_n]$
  5. Si $\varphi=(\varphi_1\to\varphi_2)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\not\models\varphi_1[a_1,\dots,a_n]$ o $\mathbf{A}\models\varphi_2[a_1,\dots,a_n]$
  6. Si $\varphi=(\varphi_1\leftrightarrow\varphi_2)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a_n]$ y $\mathbf{A}\models\varphi_2[a_1,\dots,a_n]$ o $\mathbf{A}\not\models\varphi_1[a_1,\dots,a_n]$ y $\mathbf{A}\not\models\varphi_2[a_1,\dots,a_n]$
  7. Si $\varphi=(\varphi_1\leftrightarrow\varphi_2)$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si ya sea $\mathbf{A}\models\varphi_1[a_1,\dots,a_n]$ y $\mathbf{A}\models\varphi_2[a_1,\dots,a_n]$, o bien $\mathbf{A}\not\models\varphi_1[a_1,\dots,a_n]$ y $\mathbf{A}\not\models\varphi_2[a_1,\dots,a_n]$
  8. Si $\varphi=\neg\varphi_1$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\not\models\varphi_1[a_1,\dots,a_n]$
  9. Si $\varphi=\forall v_j\varphi_1$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a,\dots,a_n]\forall a\in A$
  10. Si $\varphi=\forall v\varphi_1$ con $v\notin\{v_1,\dots,v_n\}$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a_n,a]\forall a\in A$
  11. Si $\varphi=\exists v_j\varphi_1$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a,\dots,a_n]\text{ para algún }a\in A$
  12. Si $\varphi=\exists v\varphi_1$ con $v\notin\{v_1,\dots,v_n\}$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ si y solo si $\mathbf{A}\models\varphi_1[a_1,\dots,a_n,a]\text{ para algún }a\in A$
- Sea $F:\mathbf{A}\to\mathbf{B}$ un homomorfismo y $t=_d t(v_1,\dots,v_n)$, entonces $F(t^\mathbf{A}[a_1,\dots,a_n])=t^\mathbf{B}[F(a_1),\dots,F(a_n)]$ para cada $a_1,\dots,a_n\in A$
- Sea $F:\mathbf{A}\to\mathbf{B}$ un isomorfismo y $\varphi=_d\varphi(v_1,\dots,v_n)\in F^\tau$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]\iff\mathbf{B}\models\varphi[F(a_1),\dots,F(a_n)]$ para cada $a_1,\dots,a_n\in A$
- Sea $F:\mathbf{A}\to\mathbf{B}$ un homomorfismo sobre y $\varphi=_d\varphi(v_1,\dots,v_n)\in F^\tau$ tal que los símbolos $\neg\ \to\ \leftrightarrow$ no ocurren en $\varphi$, entonces $\mathbf{A}\models\varphi[a_1,\dots,a_n]$ implica $\mathbf{B}\models\varphi[F(a_1),\dots,F(a_n)]$ para cada $a_1,\dots,a_n\in A$.

## Teoremas de reemplazo

- _Teorema de reemplazo para términos_ Sean $t=_dt(w_1,\dots,w_k),s_1=_ds_1(v_1,\dots,v_n),\dots,s_k=_ds_k(v_1,\dots,v_n)$, entonces:
  - Todas las variables de $t(s_1,\dots,s_k)$ están en $\{v_1,\dots,v_n\}$
  - Si declaramos $t(s_1,\dots,s_k)=_d t(s_1,\dots,s_k)(v_1,\dots,v_n)$, entonces $\forall\mathbf{A}$ y $a_1,\dots,a_n\in A$ se tiene que $t(s_1,\dots,s_k)^\mathbf{A}[a_1,\dots,a_n]=t^\mathbf{A}[s_1^\mathbf{A}[a_1,\dots,a_n],\dots,s_k^\mathbf{A}[a_1,\dots,a_n]]$
- _Variable sustituible_: Diremos que $v$ es **sustituible** por $w$ en $\varphi$ cuando ninguna ocurrencia libre de $v$ en $\varphi$ sucede dentro de una ocurrencia de una subfórmula de la forma $Qw\psi$ en $\varphi$
  - Dado un término $t$, diremos que $v$ es **sustituible** por $t$ en $\varphi$ cuando $v$ sea sustituible en $\varphi$ por cada variable que ocurre en $t$
  - _Propiedades_:
    1. Si $\varphi$ es atómica, entonces $v$ es sustituible por $w$ en $\varphi$
    2. Si $\varphi=(\varphi_1\eta\varphi_2)$, entonces $v$ es sustituible por $w$ en $\varphi$ sii $v$ es sustituible por $w$ en $\varphi_1$ y en $\varphi_2$
    3. Si $\varphi=\neg\varphi_1$, entonces $v$ es sustituible por $w$ en $\varphi$ sii $v$ es sustituible por $w$ en $\varphi_1$
    4. Si $\varphi=Qv\varphi_1$, entonces $v$ es sustituible por $w$ n $\varphi$
    5. Si $\varphi=Qw\varphi$ y $v\in Li(\varphi_1)$, entonces $v$ **no** es sustituible por $w$ en $\varphi$
    6. Si $\varphi=Qw\varphi$ y $v\notin Li(\varphi_1)$, entonces $v$ es sustituible por $w$ en $\varphi$
    7. Si $\varphi=Qu\varphi_1$ con $u\neq v,w$, entonces $v$ es sustituible por $w$ en $\varphi$ sii $v$ es sustituible por $w$ en $\varphi_1$
- _Teorema de reemplazo para fórmulas_: Supongamos $\varphi=_d\varphi(w_1,\dots,w_k),t_1=_d(v_1,\dots,v_n),\dots,t_k=_dt_k(v_1,\dots,v_n)$ y que cada $w_j$ es sustituible por $t_j$ en $\varphi$, entonces:
  1. $Li(\varphi(t_1,\dots,t_k))\subseteq\{v_1,\dots,v_n\}$
  2. Si declaramos $\varphi(t_1,\dots,t_k)=_d\varphi(t_1,\dots,t_k)(v_1,\dots,v_n)$, entonces para cada estructura $\mathbf{A}$ y $\vec{a}\in A^n$ se tiene $\mathbf{A}\models\varphi(t_1,\dots,t_k)[\vec{a}]\iff\mathbf{A}\models\varphi[t_1^\mathbf{A}[\vec{a}],\dots,t_k^\mathbf{A}[\vec{a}]]$
