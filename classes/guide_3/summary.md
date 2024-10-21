---
geometry: margin=3cm
---

# Guía 3: Reticulados par

## Definición inicial y algunas propiedades

- **Reticulado par**: poset $(P,\leq)$ el cual cumple que $\forall a,b\in P$ existen en $(P,\leq)$ $sup(\{a,b\})$ e $inf(\{a,b\})$
- _Propiedades_:
  - Si $(P,\leq)$ es un conjunto totalmente ordenado, entonces $(P,\leq)$ es un reticulado par.
  - Si $(P,\leq)$ es un reticulado par, entonces existe $sup(S)\forall S\subseteq P$.

## Funciones $s$, $i$

- **Función binaria**: Dado un conjunto $A$, por una operación binaria sobre $A$ entenderemos una función cuyo dominio es $A^2$ y cuya imagen está contenida en $A$.
- **Funciones** $s$, $i$: En un reticulado par $(P,\leq)$ tenemos dos operaciones binarias naturalmente definidas:
  $$
  \begin{aligned}
      s:P^2&\to P & i:P^2&\to P\\
      (a,b)&\to sup(\{a,b\}) & (a,b)&\to inf(\{a,b\})
  \end{aligned}
  $$
  - Escribiremos $a\ s\ b$ en lugar de $s(a,b)$ y $a\ i\ b$ en lugar de $i(a,b)$
- _Lemas_: Dado un reticulado par $(L,\leq)$:
  - _Cotas básicas, Reflexividad y Conmutatividad_. Se cumplen las siguientes:
    1. $x\leq x\ s\ y\ \forall x,y\in L$
    2. $x\ i\ y\leq x\ \forall x,y\in L$
    3. $x\ s\ x=x\ \forall x\in L$
    4. $x\ i\ x=x\ \forall x\in L$
    5. $x\ s\ y = y\ s\ x\ \forall x,y\in L$
    6. $x\ i\ y = y\ i\ x\ \forall x,y\in L$
  - _Supremo e ínfimo cuando están relacionados_. Se tiene que:
    1. $x\leq y\iff x\ s\ y=y\ \forall x,y\in L$
    2. $x\leq y\iff x\ i\ y=x\ \forall x,y\in L$
  - _Absorción_. Se tiene que:
    1. $x\ s\ (x\ i\ y)=x\ \forall x,y\in L$
    2. $x\ i\ (x\ s\ y)=x\ \forall x,y\in L$
  - _Asociatividad_. Se tiene que:
    1.  $(x\ s\ y)\ s\ z=x\ s\ (y\ s\ z)\ \forall x,y,z\in L$
    2.  $(x\ i\ y)\ i\ z=x\ i\ (y\ i\ z)\ \forall x,y,z\in L$
  - _Preserva el orden_. Se tiene que:
    1. $x\leq z\wedge y\leq w\Rightarrow x\ s\ y\leq z\ s\ w\ \forall x,y,z,w\in L$
    2. $x\leq z\wedge y\leq w\Rightarrow x\ i\ y\leq z\ i\ w\ \forall x,y,z,w\in L$
  - _Desigualdad de la distributividad_. Se tiene que:
    - $(x\ i\ y)\ s\ (x\ i\ z)\leq x\ i\ (y\ s\ z)\ \forall x,y,z\in L$
  - _Relación entre s/i con sup/inf para conjuntos_. Se tiene que, cualesquiera sean los elementos $x_1,...,x_n\in L:n\geq 2$:
    - $(...(x_1\ s\ x_2)\ s\ ...)\ s\ x_n=sup(\{x_1,...,x_n\})$
    - $(...(x_1\ i\ x_2)\ i\ ...)\ i\ x_n=inf(\{x_1,...,x_n\})$
- _Notación_: Dado que la distribución de paréntesis en una expresión de la forma $(...(x_1\ s\ x_2)\ s\ ...)\ s\ x_n$ es irrelevante (ya que $s$ es asociativa), en general se suprimen. Lo mismo para $i$.

## Reglas/Trucos para demostraciones

- _Igualdad en Posets_: Para ver que $x=y$ en un poset $(P,\leq)$, ver que:
  - $x\leq y$
  - $y\leq x$.
- _Igualar un Supremo_: Para ver que $x=sup(S)$ en un poset $(P,\leq)$, ver que:
  - $x$ es cota superior de $S$
  - $x\leq z\ \forall z$ cota superior de $S$
- _Superar un Supremo_: Para ver que $z\geq x\ s\ y$ en un reticulado par $(L,\leq)$, ver que:
  - $z\geq x$
  - $z\geq y$
- _Ser Menor o Igual que un Ínfimo_: Para ver que $z\leq x\ i\ y$ en un reticulado par $(L,\leq)$, ver que:
  - $z\leq x$
  - $z\leq y$
