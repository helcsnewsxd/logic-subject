---
geometry: margin=3cm
---

# Guía 4: Reticulados terna

## Definición y propiedades iniciales

- De las propiedades de $s,i$ de un reticulado par $(L,\leq)$ vamos a considerar:
  - Reflexividad: $x\ s\ x=x\ i\ x=x\ \forall x\in L$
  - Conmutatividad: $x\ s\ y=y\ s\ x\wedge x\ i\ y=y\ i\ x\ \forall x,y\in L$
  - Asociatividad: $x\ s\ (y\ s\ z)=(x\ s\ y)\ s\ z\wedge x\ i\ (y\ i\ z)=(x\ i\ y)\ i\ z\ \forall x,y,z\in L$
  - Absorción: $x\ s\ (x\ i\ y)=x=x\ i\ (x\ s\ y)\ \forall x,y\in L$
- **Reticulado terna**: un reticulado terna es una terna $(L,s,i)$ tal que $L$ es un conjunto no vacío y $s,i$ son dos operaciones binarias sobre $L$ que cumplen las propiedades de reflexividad, conmutatividad, asociatividad y absorción.
  - En este caso, decimos que $L$ es el universo de $(L,s,i)$
- **Teorema de Dedekind**: Sea $(L,s,i)$ un reticulado terna, la relación binaria sobre $L$ definida por $x\leq y\iff x\ s\ y=y$ es un orden parcial sobre $L$ para el cual se cumple que $sup(\{x,y\})=x\ s\ y$ e $inf(\{x,y\})=x\ i\ y\ \forall x,y\in L$.
  - Nos dice que a _nivel de información_ es lo mismo tener un reticulado par que un reticulado terna

## Orden asociado a un reticulado terna

- **Definición**: Llamaremos a $\leq=\{(x,y):x\ s\ y=y\}$ el _orden parcial asociado_ a $(L,s,i)$ y $(L,\leq)$ será llamado el _poset asociado_ a $(L,s,i)$.
  - Notar que también tenemos que $\leq=\{(x,y):x\ i\ y=x\}$
- _Propiedades_:
  - Si $(L,s,i)$ es un reticulado terna, entonces $(L,i,s)$ también lo es.

## Reticulados terna distributivos

- **Definición**: Un reticulado terna $(L,s,i)$ se llamará _distributivo_ cuando cumpla que $x\ i\ (y\ s\ z)=(x\ i\ y)\ s\ (x\ i\ z)\ \forall x,y,z\in L$ ( $Dis_1$ )

## Subreticulados terna

- **Conjunto cerrado bajo operación**: Si $f$ es una operación $n$-aria sobre $A$ y $S\subseteq A$, entonces diremos que $S$ es _cerrado bajo_ $f$ cuando se de que $f(a_1,...,a_n)\in S$ cada vez que $a_1,...,a_n\in S$.
- **Subreticulado terna**: Dados reticulados terna $(L,s,i)$ y $(L',s',i')$, diremos que $(L,s,i)$ es un subreticulado terna de $(L',s',i')$ si se dan las siguientes condiciones:
  1. $L\subseteq L'$
  2. $L$ es cerrado bajo las operaciones $s'$ e $i'$
  3. $s=s'|_{L^2}$ e $i=i'|_{L^2}$
- **Subuniverso**: Sea $(L,s,i)$ un reticulado terna, un conjunto $S\subseteq L$ es llamado subuniverso de $(L,s,i)$ si es no vacío y cerrado bajo las operaciones $s$ e $i$.
  - Notar que los subuniversos de $(L,s,i)$ son los universos de los subreticulados terna de $(L,s,i)$.
- _Propiedades_:
  - Si $(L,s,i)$ es un reticulado terna y $S_1,S_2$ son subuniversos de $(L,s,i)$ tal que $S_1\cap S_2\neq\emptyset$, entonces $S_1\cap S_2$ es un subuniverso de $(L,s,i)$
  - Sea $(L,s,i)$ un reticulado terna y sea $\leq$ su orden asociado, si $S\subseteq L$ es no vacío con $(S,\leq\cap S^2)$ reticulado par con operaciones de supremo e ínfimo $\hat{s},\hat{i}$, entonces $(S,\hat{s},\hat{i})$ es un subreticulado terna de $(L,s,i)$.

## Homomorfismo e isomorfismo de reticulados terna

- **Homomorfismo**: Sean $(L,s,i)$ y $(L',s',i')$ reticulados terna, una función $F:L\to L'$ será llamada un homomorfismo de $(L,s,i)$ en $(L',s',i')$ si $\forall x,y\in L$ se cumple que $F(x\ s\ y)=F(x)\ s'\ F(y)$ y que $F(x\ i\ y)=F(x)\ i'\ F(y)$.
  - Escribiremos "Sea $F:(L,s,i)\to(L',s',i')$ un homomorfismo" para expresarlo.
- **Isomorfismo**: Un homomorfismo de $(L,s,i)$ en $(L',s',i')$ será llamado isomorfismo de $(L,s,i)$ en $(L',s',i')$ cuando sea biyectivo y su inversa también sea un homomorfismo.
  - Escribiremos $(L,s,i)\cong(L',s',i')$ cuando exista un isomorfismo de $(L,s,i)$ en $(L',s',i')$.
- _Propiedades_:
  - _Importantísima de isomorfismos_: Si $F:(L,s,i)\to(L',s',i')$ es un homomorfismo biyectivo, entonces $F$ es un isomorfismo
    - Es decir, no hace falta chequear que $F^{-1}$ sea un homomorfismo para ver que $F$ es un isomorfismo.
  - Sean $(L,s,i)$ y $(L',s',i')$ reticulados terna y sea $F:(L,s,i)\to(L',s',i')$ un homomorfismo, entonces $I_F$ es un subuniverso de $(L',s',i')$.
  - _Isomorfismo de reticulados terna equivale a isomorfismo de posets_: Sean $(L,s,i)$ y $(L',s',i')$ reticulados terna y sean $(L,\leq)$ y $(L',\leq')$ los posets asociados, si $F:L\to L'$ es una función, entonces $F$ es un isomorfismo de $(L,s,i)$ en $(L',s',i')\iff F$ es un isomorfismo de $(L,\leq)$ en $(L',\leq)$
  - _Homomorfismo suryectivo mantiene distributividad_: Si $F:(L,s,i)\to(L',s',i')$ es un homomorfismo suryectivo y $(L,s,i)$ es distributivo, entonces $(L',s',i')$ es distributivo.
    - En particular, si $(L,s,i)\cong(L',s',i')$, entonces o ambos son distributivos, o ambos son no distributivos.
  - _Homomorfismo suryectivo mantiene máximo (análogo para mínimo)_: Sea $F:(L,s,i)\to(L',s',i')$ un homomorfismo suryectivo y $a$ un elemento máximo de $(L,s,i)$, entonces $F(a)$ es un elemento máximo de $(L',s',i')$.

## Congruencias de reticulados terna

- **Congruencia**: Sea $(L,s,i)$ un reticulado terna, una congruencia sobre $(L,s,i)$ será una relación de equivalencia $\theta$ sobre $L$ la cual cumpla que $x\theta x'\wedge y\theta y'\Rightarrow (x\ s\ y)\theta (x'\ s\ y')\wedge (x\ i\ y)\theta (x'\ i\ y')$.
  - Por ello, podemos definir en forma no ambigua sobre $L/\theta$ dos operaciones binarias $\overset{\sim}{s},\overset{\sim}{i}$ tales que $x/\theta\ \overset{\sim}{s}\ y/\theta=(x\ s\ y)/\theta$ y $x/\theta\ \overset{\sim}{i}\ y/\theta=(x\ i\ y)/\theta$.
- **Cociente**: La terna $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$ es llamada el cociente de $(L,s,i)$ sobre $\theta$ y la denotaremos con $(L,s,i)/\theta$
  - **Orden parcial**: Denotaremos con $\overset{\sim}{\leq}$ al orden parcial asociado al reticulado terna $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$
- _Propiedades_:
  - _El cociente de un reticulado terna es un reticulado terna_: Sea $(L,s,i)$ un reticulado terna y sea $\theta$ una congruencia de $(L,s,i)$, entonces $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$ es un reticulado terna.
  - _Relación entre orden parcial asociado al cociente y congruencia_: Sea $(L,s,i)$ un reticulado terna y sea $\theta$ una congruencia de $(L,s,i)$, entonces $x/\theta\overset{\sim}{\leq}y/\theta\iff y\theta(x\ s\ y)\ \forall x,y\in L$.
  - _Cociente mantiene máximo (análogo con el mínimo)_: Sea $(L,s,i)$ un reticulado terna con máximo $1$, entonces si $\theta$ es una congruencia sobre $(L,s,i)$, $1/\theta$ es el máximo de $(L,s,i)/\theta$.
  - _Única congruencia con máximo y mínimo congruentes_: Sea $(L,s,i)$ un reticulado terna con máximo $1$ y mínimo $0$. Sea $\theta$ una congruencia sobre $(L,s,i)$. Si $(0,1)\in\theta$, entonces $\theta=L^2$.
  - _El núcleo de un homomorfismo es una congruencia_: Si $F:(L,s,i)\to(L',s',i')$ es un homomorfismo, entonces $ker(F)$ es una congruencia sobre $(L,s,i)$
  - _La proyección canónica de una congruencia es un homomorfismo_: Sea $(L,s,i)$ un reticulado terna y sea $\theta$ una congruencia sobre $(L,s,i)$, entonces $\pi_\theta$ es un homomorfismo de $(L,s,i)$ en $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$ y $ker(\pi_\theta)=\theta$.
  - Sea $\theta$ una congruencia del reticulado terna $(L,s,i)$, si $c\in L/\theta$ entonces:
    - $c$ es un subuniverso de $(L,s,i)$
    - $c$ es un subconjunto convexo de $(L,s,i)$. Es decir que $\forall x,y,z\in L,((x,y\in\wedge x\leq z\leq y)\Rightarrow z\in c)$
  - Sea $(L,s,i)$ un reticulado terna y $S$ un subuniverso de $(L,s,i)$ con $\theta$ congruencia de $(S,s|_{S^2},i|_{S^2})$, entonces hay una congruencia $\delta$ de $(L,s,i)$ tal que $\theta=\delta\cap S^2$
  - _El cociente de un reticulado terna distributivo es distributivo_: Sea $(L,s,i)$ un reticulado terna distributivo y $\theta$ una congruencia de $(L,s,i)$, entonces $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$ es distributivo.
  - _Se mantiene el orden parcial asociado entre el reticulado terna y su cociente_: Sea $(L,s,i)$ un reticulado terna, $\theta$ una congruencia de $(L,s,i)$ y $(L/\theta,\overset{\sim}{s},\overset{\sim}{i})$ el reticulado terna cociente, entonces dados $c,c'\in L/\theta$ tenemos que $c\overset{\sim}{\leq}c'\iff\exists x\in c,y\in c':x\leq y$.
