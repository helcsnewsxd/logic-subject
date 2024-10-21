---
geometry: margin=3cm
---

# Guía 6:_Reticulados cuaterna y su lenguaje elemental_

## Definición

- Un **reticulado cuaterna** es una $4$-upla $(L,s,i,\leq)$ tal que $L$ es un conjunto no vacío, $s$ e $i$ son operaciones binarias sobre $L$, $\leq$ es una relación binaria sobre $L$ y se cumplen las siguientes propiedades:

  1. _Reflexividad_: $\forall x\in L, x\leq x$
  2. _Transitividad_: $\forall x,y,z\in L, x\leq y\wedge y\leq z\Rightarrow x\leq z$
  3. _Antisimetría_: $\forall x,y\in L, x\leq y\wedge y\leq x\Rightarrow x=y$
  4. _Cota superior (1)_: $\forall x,y\in L, x\leq x\ s\ y\wedge y\leq x\ s\ y$
  5. _Cota superior (2)_: $\forall x,y,z\in L, x\leq z\wedge y\leq z\Rightarrow x\ s\ y\leq z$
  6. _Cota inferior (1)_: $\forall x,y\in L, x\ i\ y\leq x\wedge x\ i\ y\leq y$
  7. _Cota inferior (2)_: $\forall x,y,z\in L, z\leq x\wedge z\leq y\Rightarrow z\leq x\ i\ y$

- _Misma información que reticulado terna_: una $4$-upla $(L,s,i,\leq)$ es un reticulado cuaterna $\iff$ $(L,s,i)$ es un reticulado terna y $\leq$ es su orden parcial asociado.
  - En base a esto, muchos conceptos definidos para posets o reticulados terna los usaremos referidos a un reticulado cuaterna.

## Lenguaje elemental de reticulados cuaterna

- Tengamos en cuenta que las **fórmulas elementales de reticulados cuaterna** son _palabras_ que se construyen usando símbolos de la siguiente lista:
  - $\forall\ \exists\ \neg\ \lor\ \wedge\ \to\ \leftrightarrow\ (\ )\ =\ s\ i\ \leq$
  - Variables: $x,y,z,w,...$
  - Nombres de elementos fijos: $a,b,c,d,...$

### Términos elementales de reticulados cuaterna

- Los **términos elementales de reticulados cuaterna** son _palabras_ que representan el resultado de aplicar a las variables y a los nombres de elementos fijos las operaciones $s$ e $i$ cierta cantidad de veces.
- _Reglas constructivas_: sean $s,t$ términos elementales de reticulados cuaterna entonces

  - Cada variable
  - Cada nombre de elemento fijo
  - $(t\ s\ s)$
  - $(t\ i\ s)$

  son términos elementales de reticulados cuaterna y es la única forma de construirlos.

- Un término elemental $t$ _representa o asume un valor_ cuando tenemos un reticulado cuaterna concreto y le asignamos valores a las variables y nombres de elementos fijos que ocurren en $t$.

### Fórmulas elementales de reticulados cuaterna

- _Reglas constructivas_: sean $t,s$ términos elementales de reticulados cuaterna y $\varphi_1,\varphi_2$ fórmulas elementales de reticulados cuaterna, entonces:

  - $(t=s)$
  - $(t\leq s)$
  - $\varphi_1\wedge\varphi_2$
  - $\varphi_1\lor\varphi_2$
  - $\varphi_1\leftrightarrow\varphi_2$
  - $\varphi_1\to\varphi_2$
  - $\neg\varphi_1$
  - $\forall x\varphi_1\ \forall y\varphi_1\ \forall z\varphi_1\ ...$
  - $\exists x\varphi_1\ \exists y\varphi_1\ \exists z\varphi_1\ ...$

  son fórmulas elementales de reticulados cuaterna y es la única forma de construirlas.

- Una fórmula elemental _asume o representa_ un valor de verdadero o falto cuando tenemos un reticulado cuaterna concreto $(L,s,i,\leq)$ y además asignamos valores concretos de $L$ a las variables libres y a los nombres de elementos fijos que ocurren en dicha fórmula.
  - Cabe destacar que los cuantificadores siempre ranguean sobre $L$.

### Sentencias elementales de reticulados cuaterna

- Una **sentencia elemental de reticulados cuaterna** es una fórmula elemental de reticulados cuaterna que no tiene variables libres
- _Variables libres_:
  - Si una variable ocurre varias veces en una fórmula, entonces algunas de aquellas ocurrencias serán libres y otras no
  - A las ocurrencias que no son libres las llamaremos _acotadas_.
  - Cuando digamos que $x$ es una _variable libre_ de una fórmula $\varphi$, nos estaremos refiriendo a que $x$ ocurre al menos una vez libremente en $\varphi$ (aunque también puede ocurrir acotadamente)

### Alcance de la ocurrencia de un cuantificador

- Un _cuantificador_ es una palabra formada por alguno de los símbolos $\forall\ \exists$ seguido de una variable.
- _Propiedad_: Siempre que un cuantificador ocurra en una fórmula, seguido a dicha ocurrencia ocurrirá una fórmula elemental (la cual además es única).
  - _Alcance_: En base a esto, el alcance de una ocurrencia de un cuantificador es el espacio ocupado por la única fórmula que ocurre inmediatamente después de dicha ocurrencia dle cuantificador.

## Pruebas elementales de reticulados cuaterna

- Las propiedades que definen a un reticulado cuaterna pueden ser escritas como sentencias elementales de reticulados cuaterna:

  1. _Reflexividad_: $A_{\leq R}=\forall x(x\leq x)$
  2. _Transitividad_: $A_{\leq T}=\forall x\forall y\forall z((x\leq y\wedge y\leq z)\to x\leq z)$
  3. _Antisimetría_: $A_{\leq A}=\forall x\forall y((x\leq y\wedge y\leq x)\to x=y)$
  4. _Cota superior (1)_: $A_{s\text{ es }C}=\forall x\forall y(x\leq x\ s\ y\wedge y\leq x\ s\ y)$
  5. _Cota superior (2)_: $A_{s\leq C}=\forall x\forall y\forall z((x\leq z\wedge y\leq z)\to x\ s\ y\leq z)$
  6. _Cota inferior (1)_: $A_{i\text{ es }C}=\forall x\forall y(x\ i\ y\leq x\wedge x\ i\ y\leq y)$
  7. _Cota inferior (2)_: $A_{i\geq C}=\forall x\forall y\forall z((z\leq x\wedge z\leq y)\to z\leq x\ i\ y)$

- Llamaremos **pruebas elementales de reticulados cuaterna** a las pruebas que tengan las siguientes características:
  1. Se parte de una estructura $(L,s,i,\leq)$ de la cual solo sabemos que satisface los axiomas $A_{\leq R},A_{\leq A},A_{\leq T},A_{s\text{ es }C},A_{s\leq C},A_{i\text{ es }C},A_{i\geq C}$
  2. Las deducciones de la prueba son muy simples y obvias de justificar con mínimas frases en castellano
  3. En la escritura de la prueba, lo concerniente a la matemática misma se expresa usando solo sentencias elementales de reticulados cuaterna
