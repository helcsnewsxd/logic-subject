---
geometry: margin=3cm
---

# Guía 1: Relaciones de equivalencia y particiones

## Relaciones de equivalencia

- **Relación binaria**: sea $A$ un conjunto, $R$ es una relación binaria sobre $A$ si es un subconjunto de $A^2$
  - Si $R$ es una relación binaria sobre $A$ y $A\subseteq B$, entonces $R$ es una relación binaria sobre $B$
  - _Propiedades que puede tener_ (a destacar):
    - _Reflexividad_: $xRx\ \forall x\in A$
    - _Transitividad_: $xRy\wedge yRz\Rightarrow xRz\ \forall x,y,z\in A$
    - _Simetría_: $xRy\Rightarrow yRx\ \forall x,y\in A$
    - _Antisimetría_: $xRy\wedge yRx\Rightarrow x=y\ \forall x,y\in A$
- **Relación de equivalencia**: sea $A$ un conjunto, $R$ es una relación de equivalencia sobre $A$ si es una relación binaria sobre $A$, la cual es reflexiva, transitiva y simétrica (con respecto a $A$).
- **Clases de equivalencia**: sea $R$ una relación de equivalencia sobre $A$ y $a\in A$, definimos la clase de equivalencia de $a$ con respecto a $R$ como $a/R=\{ b\in A:aRb\}$
  - **Cociente de $A$ por $R$**: $A/R=\{ a/R:a\in A\}$
  - **Proyección canónica (respecto de $R$)**: $\pi_R:A\to A/R$ con $\pi_R(a)=a/R\ \forall a\in A$.
  - _Propiedades_:
    - Sea $R$ una relación de equivalencia sobre $A$, y $a,b\in A$, entonces:
      - $a\in a/R$
      - $aRb\Leftrightarrow a/R=b/R$
      - $a/R\cap b/R=\emptyset\lor a/R=b/R$
    - Sea $R$ una relación de equivalencia sobre $A\neq\emptyset$, entonces $|A/R|=1\iff R=A^2$

## Correspondencia entre relaciones de equivalencia y particiones

- **Partición**: dado un conjunto $A$, una partición de $A$ es un conjunto $\mathcal{P}$ tal que:
  1. Cada elemento de $\mathcal{P}$ es un subconjunto no vacío de $A$
  2. Si $S_1,S_2\in\mathcal{P}$ con $S_1\neq S_2$, entonces $S_1\cap S_2=\emptyset$
  3. $A=\{ a:a\in S\text{ para algún }S\in\mathcal{P}\}$
  - Podemos definir una relación binaria asociada a $\mathcal{P}$ como $R_\mathcal{P}=\{ (a,b)\in A^2:a,b\in S\text{ para algún }S\in\mathcal{P}\}$
- _Correspondencia_:
  - _Propiedades_: sea $A$ un conjunto, entonces:
    - Sea $\mathcal{P}$ una partición de $A$, entonces $R_\mathcal{P}$ es una relación de equivalencia sobre $A$
    - Sea $R$ una relación de equivalencia sobre $A$, entonces $A/R$ es una partición de $A$
  - **Teorema**: sea $A$ un conjunto cualquiera, y sean $Part=\{\text{particiones de }A\}, ReEq=\{\text{relaciones de equivalencia de }A\}$, entonces las funciones:
    $$
    \begin{aligned}
        Part&\to ReEq&\quad ReEq&\to Part\\
        \mathcal{P}&\to R_\mathcal{P}&\quad R&\to A/R
    \end{aligned}
    $$
    son biyecciones una inversa de la otra.
    - Es decir, a nivel de información es lo mismo tener una relación de equivalencia sobre $A$ que una partición de $A$.

## Funciones con dominio $A/R$

- Sea $R$ una relación de equivalencia sobre $A$, entonces la definición de una función de tipo $f:A/R\to B$ puede no ser una función, porque el valor que toma para una clase de equivalencia, puede ser cualquiera de los representantes.
- _Ejemplos_:
  - _Caso ambiguo_: si tenemos $R$ relación de equivalencia sobre $\mathbb{R}$ y definimos $f:\mathbb{R}/R\to\mathbb{R}$ como $f(r/R)=r^2$, entonces _no es una función_ dado que si se cumple, por ejemplo, $2R6$, entonces $2^2=f(2/R)=f(6/R)=6^2$, lo cual es absurdo.
  - _Caso inambiguo_: sea $F:A\to B$, entonces $f(a/ker(F))=F(a)$ define en forma inambigua una función $f$ de tipo $A/ker(F)\to B$, la cual es inyectiva. En caso de que $F$ sea sobreyectiva, $f$ será también sobreyectiva, por lo que sería una biyección.
    - Recordemos que $ker(F)=\{(a,b)\in A^2:f(a)=f(b)\}$
