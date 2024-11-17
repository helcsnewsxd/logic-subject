---
header-includes:
  - \usepackage{enumitem}
  - \setlistdepth{20}
  - \renewlist{itemize}{itemize}{20}
  - \renewlist{enumerate}{enumerate}{20}
  - \setlist[itemize]{label=$\cdot$}
  - \setlist[itemize,1]{label=\textbullet}
  - \setlist[itemize,2]{label=--}
  - \setlist[itemize,3]{label=*}
geometry: margin=0.5in
output:
  rmarkdown::pdf_document:
    keep_tex: yes
---

# Guía 14: Teorema de Completitud

## Teorema del filtro primo

- **Definición**: Un _filtro_ de un reticulado terna $(L,s,i)$ será un subconjunto $F\subseteq L$ tal que:
  1. $F\neq\emptyset$
  2. $x,y\in F\Rightarrow x\ i\ y\in F$
  3. $x\in F$ y $x\leq y\Rightarrow y\in F$
- **Filtro generado por** $\mathbf{S}$:
  - Dado un conjunto $S\subseteq L$, consideraremos $[S)=\{y\in L:y\geq s_1\ i\ \dots\ i\ s_n,\text{ para algunos }s_1,\dots,s_n\in S,n\geq 1\}$
  - _Lema_: Supongamos $S$ no vacío. Entonces $[S)$ es un filtro. Más aún, si $F$ es un filtro y $F\supseteq S$, entonces $F\supseteq[S)$. Es decir, $[S)$ es el menor filtro que contiene a $S$.
  - Llamaremos a $[S)$ el _filtro generado_ por $S$
- **Cadena**: Sea $(P,\leq)$ un poset. Un subconjunto $C\subseteq P$ será llamado una _cadena_ si $\forall x,y\in C,\ (x\leq y\lor y\leq x)$
- **Lema de Zorn**: Sea $(P,\leq)$ un poset y supongamos que cada cadena de $(P,\leq)$ tiene al menos una cota superior. Entonces hay un elemento maximal en $(P,\leq)$
- **Filtro primo**: Un filtro $F$ de un reticulado terna $(L,s,i)$ será llamado _primo_ cuando se cumplan:
  1. $F\neq L$
  2. $x\ s\ y\in F\Rightarrow(x\in F\lor y\in F)$
- **Teorema del Filtro Primo**: Sea $(L,s,i)$ un reticulado terna distributivo y $F$ un filtro. Supongamos $x_0\in L-F$. Entonces hay un filtro primo $P$ tal que $x_0\notin P$ y $F\subseteq P$

## Teorema de Rasiova Sikorski

- **Teorema**: Sea $(B,s,i,\ ^c,0,1)$ un álgebra de Boole. Sea $a\in B,a\neq 0$. Supongamos que $(A_1,A_2,\dots)$ es una infinitupla de subconjuntos de $B$ tal que existe $\inf(A_j)$, para cada $j=1,2\dots$. Entonces hay un filtro primo $P$ el cual cumple:
  1. $a\in P$
  2. $P\supseteq A_j\Rightarrow P\ni\inf(A_j)$ para cada $j=1,2,\dots$

## Lema del ínfimo

- **Lema**: Sea $T=(\Sigma,\tau)$ una teoría y supongamos que $\tau$ tiene una cantidad infinita de nombres de constante que no ocurren en las sentencias de $\Sigma$. Entonces para cada fórmula $\varphi=_d\varphi(v)$, se tiene que en el álgebra de Lindembaum $\mathcal{A}_T$:

  $$
  [\forall v\varphi(v)]_T=\inf(\{[\varphi(t)]_T:t\in T_c^\tau\})
  $$

## Lema de coincidencia

- **Lema**: Sean $\tau$ y $\tau'$ dos tipos cualesquiera y sea $\tau_\cap=(\mathcal{C}_\cap,\mathcal{F}_\cap,\mathcal{R}_\cap,a_\cap)$ donde
  $$
  \begin{aligned}
      \mathcal{C}_\cap &= \mathcal{C}\cap\mathcal{C}' \\
      \mathcal{F}_\cap &= \{f\in\mathcal{F}\cap\mathcal{F}':a(f)=a'(f)\} \\
      \mathcal{R}_\cap &= \{r\in\mathcal{R}\cap\mathcal{R}':a(r)=a'(r)\} \\
      a_\cap &= a|_{\mathcal{F}_\cap\cup\mathcal{R}_\cap}
  \end{aligned}
  $$
  Entonces $\tau_\cap$ es un tipo tal que $T^{\tau_\cap}=T^\tau\cap T^{\tau'}$ y $F^{\tau_\cap}=F^\tau\cap F^{\tau'}$. Sean $\mathbf{A}$ y $\mathbf{A}'$ modelos de tipo $\tau$ y $\tau'$ respectivamente. Supongas que $A=A'$ y que $c^\mathbf{A}=c^{\mathbf{A}'}$ para cada $c\in\mathcal{C}_\cap$, $f^\mathbf{A}=f^{\mathbf{A}'}$ para cada $f\in\mathcal{F}_\cap$ y $r^\mathbf{A}=r^{\mathbf{A}'}$ para cada $r\in\mathcal{R}_\cap$. Entonces:
  1. Para cada $t=_d t(\vec{v})\in T^{\tau_\cap}$ se tiene que $t^\mathbf{A}[\vec{a}]=t^{\mathbf{A}'}[\vec{a}]$ para cada $\vec{a}\in A^n$
  2. Para cada $\varphi=_d\varphi(\vec{v})\in F^{\tau_\cap}$ se tiene que $\mathbf{A}\vDash\varphi[\vec{a}]$ sii $\mathbf{A}'\vDash\varphi[\vec{a}]$
  3. Si $\Sigma\cup\{\varphi\}\subseteq S^{\tau_\cap}$, entonces $(\Sigma,\tau)\vDash\varphi$ sii $(\Sigma,\tau')\vDash\varphi$

## Lema de enumeración

- **Lema**: Sea $\tau$ un tipo. Hay una infinitupla $(\gamma_1,\gamma_2,\dots)\in F^{\tau N}$ tal que:
  1. $|Li(\gamma_j)|\leq 1$ para cada $j=1,2,\dots$
  2. Si $|Li(\gamma)|\leq 1$ entonces $\gamma=\gamma_j$ para algún $j\in N$

## Lema de tipos parecidos

- **Lema**: Sean $\tau=(\mathcal{C},\mathcal{F},\mathcal{R},a)$ y $\tau'=(\mathcal{C}',\mathcal{F}',\mathcal{R}',a')$ tipos. Entonces:
  1. Si $\mathcal{C}\subseteq\mathcal{C}',\mathcal{F}\subseteq\mathcal{F}',\mathcal{R}\subseteq\mathcal{R}'$ y $a=a'|_{\mathcal{F}\cup\mathcal{R}}$, entonces $(\Sigma,\tau)\vdash\varphi$ implica $(\Sigma,\tau')\vdash\varphi$
  2. Si $\mathcal{C}\subseteq\mathcal{C}',\mathcal{F}=\mathcal{F}',\mathcal{R}=\mathcal{R}'$ y $a=a'$, entonces $(\Sigma,\tau')\vdash\varphi$ implica $(\Sigma,\tau)\vdash\varphi$ cada vez que $\Sigma\cup\{\varphi\}\subseteq S^\tau$

## Teorema de Completitud

- **Teorema**: Sea $T=(\Sigma,\tau)$ una teoría de primer orden. Si $T\vDash\varphi$, entonces $T\vdash\varphi$
- **Corolario**: Toda teoría consistente tiene un modelo
- **Corolario - Teorema de Compacidad**: Sea $(\Sigma,\tau)$ una teoría. Entonces:
  1. Si $(\Sigma,\tau)$ es tal que $(\Sigma_0,\tau)$ tiene un modelo para cada subconjunto finito $\Sigma_0\subseteq\Sigma$, entonces $(\Sigma,\tau)$ tiene un modelo
  2. Si $(\Sigma,\tau)\vDash\varphi$, entonces hay un subconjunto finito $\Sigma_0\subseteq\Sigma$ tal que $(\Sigma_0,\tau)\vDash\varphi$

## Interpretación semántica del álgebra de Lindenbaum

- **Definición**: Sea $T=(\Sigma,\tau)$ una teoría. Dada $\varphi\in S^\tau$ definamos $\text{Mod}_T(\varphi)=\{\mathbf{A}:\mathbf{A}\text{ es modelo de }T\text{ y }\mathbf{A}\vDash\varphi\}$
- **Lema**: Dadas $\varphi,\psi\in S^\tau$ se tiene:
  1. $[\varphi]_T\leq^T[\psi]_T$ sii $\text{Mod}_T(\varphi)\subseteq\text{Mod}_T(\psi)$
  2. $[\varphi]_T=[\psi]_T$ sii $\text{Mod}_T(\varphi)=\text{Mod}_T(\psi)$
  3. $[\varphi]_T<^T[\psi]_T$ sii $\text{Mod}_T(\varphi)\subsetneqq\text{Mod}_T(\psi)$
