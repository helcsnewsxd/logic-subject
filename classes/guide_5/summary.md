---
geometry: margin=3cm
---

# Guía 5: Reticulados acotados, complementados y distributivos, y Álgebras de Boole

## Reticulados acotados

- **Definición**: Por un reticulado acotado entenderemos una $5$-upla $(L,s,i,0,1)$ tal que $(L,s,i)$ es un reticulado terna, $0,1\in L$, y además $\forall x\in L, 0\ s\ x=x\wedge x\ s\ 1=1$.

### Orden asociado

- **Definición**: Dado un reticulado acotado $(L,s,i,0,1)$ llamaremos a $\leq=\{(x,y):x\ s\ y=y\}$ el orden parcial asociado a $(L,s,i,0,1)$ y $(L,\leq)$ será llamado el poset asociado a $(L,s,i,0,1)$.
  - Notar que $\leq=\{(x,y):x\ i\ y=x\}$
- _Propiedades_:
  - Si $(L,s,i,0,1)$ es un reticulado acotado, entonces $0\ i\ x=0\wedge 1\ i\ x=x\ \forall x\in L$

### Subreticulado acotado

- **Definición**: Dados reticulados acotados $(L,s,i,0,1)$ y $(L',s',i',0',1')$, diremos que $(L,s,i,0,1)$ es un subreticulado acotado de $(L',s',i',0',1')$ si se dan las siguientes condiciones:
  1. $L\subseteq L'$
  2. $L$ es cerrado bajo $s',i'$
  3. $0=0'$ y $1=1'$
  4. $s=s'|_{L^2}$ e $i=i'|_{L^2}$
- **Subuniverso**: Un conjunto $S\subseteq L$ es un subuniverso de $(L,s,i,0,1)$ si $0,1\in S$ y además $S$ es cerrado bajo $s,i$.
  - Notar que los subuniversos de $(L,s,i,0,1)$ son los universos de los subreticulados acotados de $(L,s,i,0,1)$.
- _Propiedades:_
  - Si $(L,s,i,0,1)$ es un reticulado acotado y $S_1,S_2$ son subuniversos de $(L,s,i,0,1)$, entonces $S_1\cap S_2$ es un subuniverso de $(L,s,i,0,1)$

### Homomorfismo e isomorfismo de reticulados acotados

- **Homomorfismo**: Sean $(L,s,i,0,1)$ y $(L',s',i',0',1')$ reticulados acotados, una función $F:L\to L'$ será llamada un homomorfismo de $(L,s,i,0,1)$ en $(L',s',i',0',1')$ si $\forall x,y\in L$ se cumple que:
  1. $F(x\ s\ y)=F(x)\ s'\ F(y)$
  2. $F(x\ i\ y)=F(x)\ i'\ F(y)$
  3. $F(0)=0'$
  4. $F(1)=1'$
- **Isomorfismo**: Un homomorfismo de $(L,s,i,0,1)$ en $(L',s',i',0',1')$ será llamado isomorfismo cuando sea biyectivo y su inversa sea también un homomorfismo.
  - Escribiremos $(L,s,i,0,1)\cong (L',s',i',0',1')$
- _Propiedades_:
  - _Para isomorfismo no hace falta chequear la inversa_: Si $F:(L,s,i,0,1)\to (L',s',i',0',1')$ es un homomorfismo biyectivo, entonces $F$ es un isomorfismo
  - _La imagen del homomorfismo es un subuniverso_: Si $F:(L,s,i,0,1)\to (L',s',i',0',1')$ es un homomorfismo, entonces $I_F$ es un subuniverso de $(L',s',i',0',1')$.

### Congruencias de reticulados acotados

- **Definición de congruencia**: Sea $(L,s,i,0,1)$ un reticulado acotado, una congruencia sobre $(L,s,i,0,1)$ será una relación de equivalencia $\theta$ la cual sea una congruencia sobre $(L,s,i)$.
- **Definición de operaciones**: Tenemos definidas sobre $L/\theta$ dos operaciones binarias $\overset{\sim}{s},\overset{\sim}{i}$ tales que $x/\theta\ \overset{\sim}{s}\ y/\theta=(x\ s\ y)/\theta$ y $x/\theta\ \overset{\sim}{i}\ y/\theta=(x\ i\ y)/\theta$
- **Definición de cociente**: La $5$-upla $(L/\theta,\overset{\sim}{s},\overset{\sim}{i},0/\theta,1/\theta)$ es llamada el cociente de $(L,s,i,0,1)$ sobre $\theta$ y la denotaremos con $(L,s,i,0,1)/\theta$.
- _Propiedades_:
  - _La proyección canónica de la congruencia es un homomorfismo_: Sea $(L,s,i,0,1)$ un reticulado acotado y $\theta$ una congruencia sobre $(L,s,i,0,1)$, entonces $(L,s,i,0,1)/\theta$ es un reticulado acotado y $\pi_\theta$ es un homomorfismo de $(L,s,i,0,1)$ en $(L,s,i,0,1)/\theta$ cuyo núcleo es $\theta$.
  - _El núcleo de un homomorfismo es una congruencia_: Si $F:(L,s,i,0,1)\to (L',s',i',0',1')$ es un homomorfismo de reticulados acotados, entonces $ker(F)$ es una congruencia sobre $(L,s,i,0,1)$.

## Reticulados complementados

- **Definición de complemento**: Sea $(L,s,i,0,1)$ un reticulado acotado, dado $a\in L$ diremos que $a$ es complementado cuando exista un elemento $b\in L$ (llamado complemento de a) tal que $a\ s\ b=1\wedge a\ i\ b=0$.
  - Notar que el $b$ puede no ser único. Es decir, $a$ puede tener varios complementos.
- **Definición de operación unaria**: Una operación unaria sobre un conjunto $L$ es una función de $L$ en $L$.
  - Si $s$ denota una operación unaria, entonces escribiremos $x^s$ en vez de $s(x)$
- **Definición de reticulado complementado**: Por un reticulado complementado entenderemos una $6$-upla $(L,s,i,^c,0,1)$ tal que $(L,s,i,0,1)$ es un reticulado acotado y $^c$ es una operación unaria sobre $L$ tal que $\forall x\in L,x\ s\ x^c=1\wedge x\ i\ x^c=0$
- _Propiedades_:
  - _Máximo y mínimo tienen un solo complemento_: Sea $(L,s,i,0,1)$ un reticulado acotado, si $1$ es un complemento de $a$ entonces $a=0$. Del mismo modo, si $a$ es un complemento de $0$, entonces $a=1$.

### Orden asociado a un reticulado complementado

- **Definición**: Dado un reticulado complementado $(L,s,i,^c,0,1)$, llamaremos a $\leq=\{(x,y):x\ s\ y=y\}$ el orden parcial asociado a $(L,s,i,^c,0,1)$ y $(L,\leq)$ será llamado el poset asociado a $(L,s,i,^c,0,1)$.
  - Notar que $\leq=\{(x,y):x\ i\ y=x\}$

### Subreticulado complementado

- **Definición**: Dados reticulado complementados $(L,s,i,^c,0,1)$ y $(L',s',i',^{c'},0',1')$, diremos que $(L,s,i,^c,0,1)$ es un subreticulado complementado de $(L',s',i',^{c'},0',1')$ si se dan las siguientes condiciones:
  1. $L\subseteq L'$
  2. $L$ es cerrado bajo $s',i',^{c'}$
  3. $0=0'$ y $1=1'$
  4. $s=s'|_{L^2}$, $i=i'|_{L^2}$ y $^c=^{c'}|_L$
- **Definición de subuniverso**: Sea $(L,s,i,^c,0,1)$ un reticulado complementado, un conjunto $S\subseteq L$ es llamado subuniverso de $(L,s,i,^c,0,1)$ si $0,1\in S$ y además $S$ es cerrado bajo $s,i,^c$.
  - Notar que los subuniversos de $(L,s,i,^c,0,1)$ son los universos de los subreticulados complementados de $(L,s,i,^c,0,1)$.

### Homomorfismo e isomorfismo de reticulados complementados

- **Homomorfismo**: Sean $(L,s,i,^c,0,1)$ y $(L',s',i',^{c'},0',1')$ reticulados complementados, una función $F:L\to L'$ será llamada un homomorfismo de $(L,s,i,^c,0,1)$ en $(L',s',i',^{c'},0',1')$ si $\forall x,y\in L$ se cumple que:
  1. $F(x\ s\ y)=F(x)\ s'\ F(y)$
  2. $F(x\ i\ y)=F(x)\ i'\ F(y)$
  3. $F(x^c)=F(x)^{c'}$
  4. $F(0)=0'$
  5. $F(1)=1'$
- **Isomorfismo**: Un homomorfismo de $(L,s,i,^c,0,1)$ en $(L',s',i',^{c'},0',1')$ será llamado isomorfismo cuando sea biyectivo y su inversa sea un homomorfismo.
  - Usaremos el símbolo $\cong$ para denotar la relación de isomorfismo.
- _Propiedades:_
  - _Para isomorfismo de reticulados complementados no hace falta ver la inversa_: Si $F:(L,s,i,^c,0,1)\to (L',s',i',^{c'},0',1')$ es un homomorfismo biyectivo, entonces $F$ es un isomorfismo.
  - _La imagen del homomorfismo es un subuniverso_: Si $F:(L,s,i,^c,0,1)\to (L',s',i',^{c'},0',1')$ es un homomorfismo, entonces $I_F$ es un subuniverso de $(L',s',i',^{c'},0',1')$.

### Congruencias de reticulados complementados

- **Definición de congruencia**: Sea $(L,s,i,^c,0,1)$ un reticulado complementado, una congruencia sobre $(L,s,i,^c,0,1)$ será una relación de equivalencia $\theta$ sobre $L$ la cual cumpla:
  1. $\theta$ es una congruencia sobre $(L,s,i,0,1)$
  2. $x/\theta=y/\theta\Rightarrow x^c/\theta=y^c/\theta$
- **Definición de operaciones**: Definimos sobre $L/\theta$ dos operaciones binarias $\overset{\sim}{s},\overset{\sim}{i}$ y una operación unaria $^{\overset{\sim}{c}}$ tales que:
  - $x/\theta\ \overset{\sim}{s}\ y/\theta=(x\ s\ y)/\theta$
  - $x/\theta\ \overset{\sim}{i}\ y/\theta=(x\ i\ y)/\theta$
  - $(x/\theta)^{\overset{\sim}{c}}=x^c/\theta$
- **Definición de cociente**: La $6$-upla $(L/\theta,\overset{\sim}{s},\overset{\sim}{i},^{\overset{\sim}{c}},0/\theta,1/\theta)$ es llamada el cociente de $(L,s,i,^c,0,1)$ sobre $\theta$ y la denotaremos con $(L,s,i,^c,0,1)/\theta$.
- _Propiedades:_
  - _La proyección canónica de una congruencia sobre un reticulado complementado es un homomorfismo de estos_: Sea $(L,s,i,^c,0,1)$ un reticulado complementado y sea $\theta$ una congruencia sobre $(L,s,i,^c,0,1)$ entonces $(L,s,i,^c,0,1)/\theta$ es un reticulado complementado y $\pi_\theta$ es un homomorfismo de $(L,s,i,^c,0,1)$ en $(L,s,i,^c,0,1)/\theta$ cuyo núcleo es $\theta$.
  - _El núcleo de un homomorfismo es una congruencia_: Si $F:(L,s,i,^c,0,1)\to (L',s',i',^{c'},0',1')$ es un homomorfismo de reticulados complementados, entonces $ker(F)$ es una congruencia sobre $(L,s,i,^c,0,1)$.

## Álgebras de Boole

- **Distributividad**: Diremos que un reticulado acotado $(L,s,i,0,1)$ (resp. complementado $(L,s,i,^c,0,1)$ ) es distributivo cuando $(L,s,i)$ lo sea.
- **Álgebra de Boole**: Reticulado complementado que es distributivo.
- _Propiedades_:
  - _La distributividad y la distributividad dual son equivalentes_: Sea $(L,s,i)$ un reticulado terna, entonces $(\forall x,y,z\in L, x\ i\ (y\ s\ z)=(x\ i\ y)\ s\ (x\ i\ z))\iff (\forall a,b,c\in L,a\ s\ (b\ i\ c)=(a\ s\ b)\ i\ (a\ s\ c))$.
  - _En un reticulado acotado distributivo se puede tener a lo sumo un complemento_: Si $(L,s,i,0,1)$ es un reticulado acotado y distributivo, entonces todo elemento tiene a lo sumo un complemento.
    - Es decir, si $x\ s\ u=x\ s\ v=1$ y $x\ i\ u=x\ i\ v=0$, entonces $u=v$ cualesquiera sean $x,u,v\in L$.
  - Sea $(B,s,i,^c,0,1)$ un álgebra de Boole, $\forall x,y\in B,y=(y\ i\ x)\ s\ (y\ i\ x^c)$
  - _Teorema de Álgebras de Boole_: Sea $(L,s,i,^c,0,1)$ un álgebra de Boole y sean $a,b\in L$, se tiene que:
    1. $(a\ i\ b)^c=a^c\ s\ b^c$
    2. $(a\ s\ b)^c=a^c\ i\ b^c$
    3. $a^{cc}=a$
    4. $a\ i\ b=0\iff b\leq a^c$
    5. $a\leq b\iff b^c\leq a^c$

## Notación

- En general usaremos letras mayúsculas en negrita para denotar una estructura dada y su correspondiente mayúscula en itálica denotará al universo de esta.
