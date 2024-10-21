---
geometry: margin=3cm
---

# Guía 9: _Modelo matemático de la sintaxis elemental_

## Variables

- Definiremos como conjunto concreto de **variables** al conjunto $Var$ de palabras del alfabeto $\{\mathsf{X},\textit{0,1,}\dots,\textit{9},\textbf{0,1,}\dots,\textbf{9}\}$ definido como:
  $$Var=\{\textsf{X}\textbf{1},\textsf{X}\textbf{2},\dots,\textsf{X}\textbf{9},\textsf{X}\textit{1}\textbf{0},\textsf{X}\textit{1}\textbf{1},\textsf{X}\textit{1}\textbf{2},\dots,\textsf{X}\textit{1}\textbf{9},\textsf{X}\textit{2}\textbf{0},\textsf{X}\textit{2}\textbf{1},\dots\}$$
  - Denotaremos con $x_i$ al $i$-ésimo elemento de $Var\ \forall x\in N$

## Términos

- Dado un tipo $\tau$, definamos recursivamente los conjuntos de palabras $T_k^{\tau}$, con $k\geq 0$, de la siguiente manera:
  $$
  \begin{aligned}
      T_0^{\tau} &= Var\cup\mathcal{C} \\
      T_{k+1}^{\tau} &= T_k^{\tau}\cup\{f(t_1,\dots,t_n):f\in\mathcal{F}_n,n\geq 1\text{ y }t_1,\dots,t_n\in T_k^{\tau}\}
  \end{aligned}
  $$
- Sea $T^{\tau}=\cup_{k\geq 0} T_k^{\tau}$, los elementos de $T^{\tau}$ serán llamados **términos de tipo** $\tau$.
  - Un término $t$ es llamado **cerrado** si $x_i$ no es subpalabra de $t$ para cada $i\in N$. Definamos $T_c^{\tau}=\{t\in T^{\tau}:t\text{ es cerrado}\}$
- _Propiedades_:
  - _Menú para términos_: Supongamos $t\in T_k^\tau$ con $k\geq 1$. Entonces se da alguna de las siguientes:
    1. $t\in Var\cup\mathcal{C}$
    2. $t=f(t_1,\dots,t_n)$ con $f\in\mathcal{F}_n,\ n\geq 1$ y $t_1,\dots,t_n\in T_{k-1}^\tau$
  - Si $t\in T^\tau-(Var\cup\mathcal{C})$ entonces $|t|\geq 4$
  - Si $t\in T^\tau$ es tal que en $t$ ocurre el símbolo $)$, entonces $t=f(t_1,\dots,t_n)$ con $f\in\mathcal{F}_n,\ n\geq 1$ y $t_1,\dots,t_n\in T^\tau$
  - Si $t\in T^\tau$ y $[t]_i=)$, con $i<|t|$, entonces $[t]_{i+1}=,$ o $[t]_{i+1}=)$
  - En un término nunca puede ocurrir la palabra $(,$
  - Si un término comienza con $\mathsf{X}$, entonces debe ser una variable

### Unicidad de la lectura de términos

- Notemos que en la definición de tipo se exige que nunca un nombre de constante sea subpalabra de otro nombre de constante, lo cual garantiza que nunca puede ser un nombre de constante un tramo inicial o final propio de otro nombre de constante. Lo que _sí_ puede suceder es que un tramo final propio de un nombre de constante $c$ sea un tramo inicial propio de otro nombre de constante $d$. En tal caso, solemos decir que las palabras $c$ y $d$ es _mordizquean_.
  - _Mordizqueo de Términos_: Sean $s,t\in T^\tau$ y supongamos que hay palabras $x,y,z$ con $y\neq\varepsilon$ tales que $s=xy$ y $t=yz$. Entonces $x=z=\varepsilon$ o $s,t\in\mathcal{C}$.
    - En particular, si un término es tramo inicial o final de otro término, entonces dichos términos son iguales.
- Sea $\tau$ un tipo, si $t_1,t_2,s_1,s_2\in T^\tau$ y $t_1t_2=s_1s_2$, entonces $t_1=s_1$ y $t_2=s_2$
- _Lectura única de términos_: Dado $t\in T^\tau$, se da una de las siguientes:

  1. $t\in Var\cup\mathcal{C}$
  2. Hay únicos $n\geq 1,\ f\in\mathcal{F}_n,\ t_1,\dots,t_n\in T^\tau$ tales que $t=f(t_1,\dots,t_n)$

  Este teorema es importante porque nos permite definir recursivamente funciones con dominio contenido en $T^\tau$

### Ocurrencias y subtérminos

- _Ocurrencias de términos en términos_: Sean $r,s,t\in T^\tau$:
  1. Si $s\neq t=f(t_1,\dots,t_n)$ y $s$ ocurre en $t$, entonces dicha ocurrencia sucede dentro de algún $t_j,\ j=1,\dots,n$
  2. Si $r,s$ ocurren en $t$, entonces dichas ocurrencias son disjuntas o una ocurre dentro de otra. En particular, las distintas ocurrencias de $r$ en $t$ son disjuntas.
  3. Si $t'$ es el resultado de reemplazar una ocurrencia de $s$ en $t$ por $r$, entonces $t'\in T^\tau$

## Fórmulas

- Sea $\tau$ un tipo, las palabras de alguna de las siguientes dos formas:
  $$
  \begin{aligned}
      (t\equiv s), &\text{ con }t,s\in T^\tau \\
      r(t_1,\dots,t_n), &\text{ con }r\in\mathcal{R}_n,\ n\geq 1,\ t_1,\dots,t_n\in T^\tau
  \end{aligned}
  $$
  serán llamadas **fórmulas atómicas de tipo** $\tau$.
- Dado un tipo $\tau$, definimos recursivamente los conjuntos de palabras $F_k^\tau$, con $k\geq 0$, de la siguiente manera:
  $$
  \begin{aligned}
    F_0^\tau &= \{\text{fórmulas atómicas de tipo }\tau\} \\
    F_{k+1}^\tau &= F_k^\tau\cup\{\neg\varphi:\varphi\in F_k^\tau\}\cup\{(\varphi\lor\psi):\varphi,\psi\in F_k^\tau\}\cup \\
    &\qquad\{(\varphi\wedge\psi):\varphi,\psi\in F_k^\tau\}\cup\{(\varphi\to\psi):\varphi,\psi\in F_k^\tau\}\cup \\
    &\qquad\{(\varphi\leftrightarrow\psi):\varphi,\psi\in F_k^\tau\}\cup\{\forall v\varphi:\varphi\in F_k^\tau\text{ y }v\in Var\}\cup\\
    &\qquad\{\exists v\varphi:\varphi\in F_k^\tau\text{ y }v\in Var\}
  \end{aligned}
  $$
- Sea $F^\tau=\cup_{k\geq 0}F_k^\tau$, los elementos de $F^\tau$ serán llamados **fórmulas de tipo** $\tau$.
- _Propiedades_:
  - _Menú para fórmulas_: Supongamos $\varphi\in F_k^\tau$, con $k\geq 1$. Entonces $\varphi$ es de alguna de las siguientes formas:
    $$
    \begin{aligned}
        \varphi &= (t\equiv s)\quad\text{con }t,s\in T^\tau\\
        \varphi &= r(t_1,\dots,t_n)\quad\text{ con }r\in\mathcal{R}_n,\ t_1,\dots,t_n\in T^\tau\\
        \varphi &= (\varphi_1\eta\varphi_2)\quad\text{ con }\eta\in\{\wedge,\lor\to,\leftrightarrow\},\ \varphi_1,\varphi_2\in F_{k-1}^\tau\\
        \varphi &= \neg\varphi_1\quad\text{ con }\varphi_1\in F_{k-1}^\tau\\
        \varphi &= Qv\varphi_1\quad\text{ con }Q\in\{\forall,\exists\},\ v\in Var,\ \varphi_1\in F_{k-1}^\tau
    \end{aligned}
    $$
  - Sea $\varphi\in F^\tau$, entonces:
    1. Si $\varphi'=$ resultado de remover en $\varphi$ cada ocurrencia del símbolo $\neg$ entonces $\varphi'\in F^\tau$
    2. Si $\varphi'=$ resultado de reemplazar cada ocurrencia de la variable $x_1$ en $\varphi$ por $x_2$, entonces $\varphi'\in F^\tau$
    3. Si $\varphi'=$ resultado de reemplazar algunas ocurrencias de la variable $x_1$ en $\varphi$ por $x_2$, entonces $\varphi'\in F^\tau$

### Unicidad de la lectura de fórmulas

- _Mordisqueo de fórmulas_: Si $\varphi,\psi\in F^\tau$ y $x,y,z$ son tales que $\varphi=xy,\psi=yz,y\neq\varepsilon$, entonces $z=\varepsilon,\ x\in(\{\neg\}\cup\{Qv:Q\in\{\forall,\exists\}\text{ y }v\in Var\})^*$. En particular, ningún tramo inicial propio de una fórmula es una fórmula.
- _Lectura única de fórmulas_: Dada $\varphi\in F^\tau$ se da una y solo una de las siguientes:

  1. $\varphi = (t\equiv s)\quad\text{con }t,s\in T^\tau$
  2. $\varphi = r(t_1,\dots,t_n)\quad\text{ con }r\in\mathcal{R}_n,\ t_1,\dots,t_n\in T^\tau$
  3. $\varphi = (\varphi_1\eta\varphi_2)\quad\text{ con }\eta\in\{\wedge,\lor\to,\leftrightarrow\},\ \varphi_1,\varphi_2\in F^\tau$
  4. $\varphi = \neg\varphi_1\quad\text{ con }\varphi_1\in F^\tau$
  5. $\varphi = Qv\varphi_1\quad\text{ con }Q\in\{\forall,\exists\},\ v\in Var,\ \varphi_1\in F^\tau$

  Más aún, en estos casos las descomposiciones son únicas.

- Si $\psi_1,\psi_2,\varphi_1,\varphi_2\in F^\tau$ y $\psi_1\psi_2=\varphi_1\varphi_2$, entonces $\psi_1=\varphi_1$ y $\psi_2=\varphi_2$
- Si $(\alpha\wedge\beta),\ \beta\in F^\tau$, entonces $\alpha\in F^\tau$

### Subfórmulas

- Una fórmula $\varphi$ será llamada una **subfórmula (propia)** de una fórmula $\psi$, cuando $\varphi$ (sea no igual a $\psi$ y) sea subpalabra de $\psi$.
- _Ocurrencias de fórmulas en fórmulas_: Sea $\tau$ un tipo:
  1. Las fórmulas atómicas no tienen subfórmulas propias.
  2. Si $\varphi$ ocurre propiamente en $(\psi\eta\phi)$, entonces tal ocurrencia es en $\psi$ o en $\phi$.
  3. Si $\varphi$ ocurre propiamente en $\neg\psi$, entonces tal ocurrencia es en $\psi$
  4. Si $\varphi$ ocurre propiamente en $Qx_k\psi$, entonces tal ocurrencia es en $\psi$
  5. Si $\varphi_1,\varphi_2$ ocurren en $\varphi$, entonces dichas ocurrencias son disjuntas o una contiene a la otra
  6. Si $\lambda'$ es el resultado de reemplazar alguna ocurrencia de $\varphi$ en $\lambda$ por $\psi$, entonces $\lambda'\in F^\tau$

### Variables libres

- Se define recursivamente la relación $v$ **ocurre libremente en** $\varphi$ **a partir de** $i$, donde $v\in Var,\ \varphi\in F^\tau$ y $i\in\{1,\dots,|\varphi|\}$, de la siguiente manera:
  1. Si $\varphi$ es atómica, entonces $v$ ocurre libremente en $\varphi$ a partir de $i$ sii $v$ ocurre en $\varphi$ a partir de $i$
  2. Si $\varphi=(\varphi_1\eta\varphi_2)$, entonces $v$ ocurre libremente en $\varphi$ a partir de $i$ sii se da alguna de las siguientes:
     1. $v$ ocurre libremente en $\varphi_1$ a partir de $i-1$
     2. $v$ ocurre libremente en $\varphi_2$ a partir de $i-|(\varphi_1\eta|$
     3. Si $\varphi=\neg\varphi_1$, entonces $v$ ocurre libremente en $\varphi$ a partir de $i$ sii $v$ ocurre libremente en $\varphi_1$ a partir de $i-1$
     4. Si $\varphi=Qw\varphi_1$, entonces $v$ ocurre libremente en $\varphi$ a partir de $i$ sii $v\neq w$ y $v$ ocurre libremente en $\varphi_1$ a partir de $i-|Qw|$
- Dados $v\in Var,\ \varphi\in F^\tau,\ i\in\{1,\dots,|\varphi|\}$, diremos que $v$ **ocurre acotadamente en** $\varphi$ **a partir de** $i$ cuando $v$ ocurre en $\varphi$ a partir de $i$ y $v$ no ocurre libremente en $\varphi$ a partir de $i$
- Dada una fórmula $\varphi$, sea
  $$Li(\varphi)=\{v\in Var:\text{hay un }i\text{ tal que }v\text{ ocurre libremente en }\varphi\text{ a partir de }i\}$$
  Los elementos de $Li(\varphi)$ serán llamados **variables libres de** $\varphi$.
- Una **sentencia** será una fórmula $\varphi$ tal que $Li(\varphi)=\emptyset$. Usaremos $S^\tau$ para denotar el conjunto de las sentencias de tipo $\tau$
- _Propiedades_: Sea $\tau$ un tipo:
  1. $Li((t\equiv s))=\{v\in Var:v\text{ ocurre en }t\text{ o }v\text{ ocurre en }s\}$
  2. $Li(r(t_1,\dots,t_n))=\{v\in Var:v\text{ ocurre en algún }t_i\}$
  3. $Li(\neg\varphi)=Li(\varphi)$
  4. $Li((\varphi\eta\psi))=Li(\varphi)\cup Li(\psi)$
  5. $Li(Qx_j\varphi)=Li(\varphi)-\{x_j\}$

### Modelo matemático de las fórmulas elementales de tipo $\tau$

- Si $\tau=(\mathcal{C,F,R},a)$ es un tipo, diremos que $\tau'$ es una **extensión de** $\tau$ **por nombres de constante** si $\tau'$ es de la forma $(\mathcal{C',F,R},a)$ con $\mathcal{C'}$ tal que $\mathcal{C}\subseteq\mathcal{C'}$
