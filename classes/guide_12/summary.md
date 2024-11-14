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

# Guía 12: Teorías de primer orden

## Teoría de primer orden

- **Teoría de primer orden**: Una teoría (de primer orden) es un par $(\Sigma,\tau)$ donde $\tau$ es un tipo y $\Sigma$ es un conjunto de sentencias de tipo $\tau$
  - Los elementos de $\Sigma$ son los _axiomas propios_ de $(\Sigma,\tau)$
  - Un _modelo de_ $(\Sigma,\tau)$ será una estructura de tipo $\tau$ la cual satisfaga todos los axiomas propios de $(\Sigma,\tau)$
  - Ejemplos:
    - $Po=(\{A_{\leq R},A_{\leq T},A_{\leq A}\}, \tau_{Po})$ con $\tau_{Po}=(\emptyset,\emptyset,\{\leq\},\{(\leq,2)\})$
    - $RetCua=(\Sigma_{RetCua},\tau_{RetCua})$ con $\Sigma_{RetCua}=\{A_{\leq R},A_{\leq T},A_{\leq A},A_{s\text{ es }C},A_{s\leq C},A_{i\text{ es }C},A_{i\geq C}\}$ y $\tau_{RetCua}=(\emptyset,\{s^2,i^2\},\{\leq^2\},a)$

## Prueba formal

- Como objeto matemático, una prueba resultará ser un par ordenado de palabras cuya primera coordenada codificará en forma natural la sucesión de sentencias y su segunda coordenada codificará la sucesión de justificaciones

### Reglas

- Reglas a considerar:
  - Sea $R$ una regla tal que $(\varphi_1,\dots,\varphi_n)\in R$, decimos que $\varphi_n$ se deduce de $\varphi_1,\dots,\varphi_{n-1}$ por la regla $R$ respecto a $\tau$ para expresar que $(\varphi_1,\dots,\varphi_n)\in R$
  - Particularización:
    - $Partic^\tau=\{(\forall v\varphi(v),\varphi(t)):\varphi_d=\varphi(v)\in F^\tau\text{ y }t\in T^\tau_c\}$
  - Existencia:
    - $Exist^\tau=\{(\varphi(t),\exists v\varphi(v)):\varphi=_d\varphi(v)\in F^\tau\text{ y }t\in T^\tau_c\}$
  - Evocación
    - $Evoc^\tau=\{(\varphi,\varphi):\varphi\in S^\tau\}$
  - Absurdo:
    - $Absur^\tau=Absur1^\tau\cup Absur2^\tau\cup Absur3^\tau$
      - $Absur1^\tau=\{((\neg\varphi\to(\psi\wedge\neg\psi)),\varphi):\varphi,\psi\in S^\tau\}$
      - $Absur2^\tau=\{((\varphi\to(\psi\wedge\neg\psi)),\neg\varphi):\varphi,\psi\in S^\tau\}$
      - $Absur3^\tau=\{((\varphi\wedge\neg\varphi),\psi):\varphi,\psi\in S^\tau\}$
  - Conjunción-introducción y conjunción-eliminación:
    - $ConjInt^\tau=\{(\varphi,\psi,(\varphi\wedge\psi)):\varphi,\psi\in S^\tau\}$
    - $ConjElim^\tau=ConjElim1^\tau\cup ConjElim2^\tau$
      - $ConjElim1^\tau=\{((\varphi\wedge\psi),\varphi):\varphi,\psi\in S^\tau\}$
      - $ConjElim2^\tau=\{((\varphi\wedge\psi),\psi):\varphi,\psi\in S^\tau\}$
  - Equivalencia-introducción y equivalencia-eliminación:
    - $EquivInt^\tau=\{((\varphi\to\psi),(\psi\to\varphi),(\varphi\leftrightarrow\psi)):\varphi,\psi\in S^\tau\}$
    - $EquivElim^\tau=EquivElim1^\tau\cup EquivElim2^\tau$
      - $EquivElim1^\tau=\{((\varphi\leftrightarrow\psi),(\varphi\to\psi)):\varphi,\psi\in S^\tau\}$
      - $EquivElim2^\tau=\{((\varphi\leftrightarrow\psi),(\psi\to\varphi)):\varphi,\psi\in S^\tau\}$
  - Disyunción-introducción y disyunción-eliminación:
    - $DisjInt^\tau=DijInt1^\tau\cup DisjInt2^\tau\cup DisjElim3^\tau$
      - $DisjInt1^\tau=\{(\varphi,(\varphi\lor\psi)):\varphi,\psi\in S^\tau\}$
      - $DisjInt2^\tau=\{(\psi,(\varphi\lor\psi)):\varphi,\psi\in S^\tau\}$
      - $DisjInt3^\tau=\{((\neg\varphi\to\psi),(\varphi\lor\psi)):\varphi,\psi\in S^\tau\}$
    - $DisjElim^\tau=DisjElim1^\tau\cup DisjElim2^\tau$
      - $DisjElim1^\tau=\{(\neg\varphi,(\varphi\lor\psi),\psi):\varphi,\psi\in S^\tau\}$
      - $DisjElim2^\tau=\{(\neg\psi,(\varphi\lor\psi),\varphi):\varphi,\psi\in S^\tau\}$
  - Conmutatividad:
    - $Commut^\tau=Commut1^\tau\cup Commut2^\tau$
      - $Commut1^\tau=\{((t\equiv s),(s\equiv t)):s,t\in T^\tau_c\}$
      - $Commut2^\tau=\{((\varphi\leftrightarrow\psi),(\psi\leftrightarrow\varphi)):\varphi,\psi\in S^\tau\}$
  - Modus Ponens:
    - $ModPon^\tau=\{(\varphi,(\varphi\to\psi),\psi):\varphi,\psi\in S^\tau\}$
  - División por casos:
    - $DivPorCas^\tau=\{((\varphi_1\lor\varphi_2),(\varphi_1\to\psi),(\varphi_2\to\psi),\psi):\varphi_1,\varphi_2,\psi\in S^\tau\}$
  - Reemplazo:
    - $Reemp^\tau=Reemp1^\tau\cup Reem2^\tau$
      - $Reem1^\tau=\{((t\equiv s),\gamma,\bar{\gamma}):s,t\in T^\tau_c,\gamma\in S^\tau\text{ y }\bar{\gamma}=\text{resultado de reemplazar en }\gamma\text{ una ocurrencia de }t\text{ por }s\}$
      - $Reem2^\tau=\{(\forall v_1\dots\forall v_n(\varphi\leftrightarrow\psi),\gamma,\bar{\gamma}),\varphi,\psi\in F^\tau,Li(\varphi)=Li(\psi)=\{v_1,\dots,v_n\},n\geq 0,\gamma\in S^\tau\text{ y }\bar{\gamma}=\text{resultado de reemplazar en }\gamma\text{ una ocurrencia de }\varphi\text{ por }\psi\}$
    - Transitividad:
      - $Trans^\tau=Trans1^\tau\cup Trans2^\tau\cup Trans3^\tau$
        - $Trans1^\tau=\{((t\equiv s),(s\equiv u),(t\equiv u)):t,s,u\in T^\tau_c\}$
        - $Trans2^\tau=\{((\varphi\to\psi),(\psi\to\Phi),(\varphi\to\Phi)):\varphi,\psi,\Phi\in S^\tau\}$
        - $Trans3^\tau=\{((\varphi\leftrightarrow\psi),(\psi\leftrightarrow\Phi),(\varphi\leftrightarrow\Phi)):\varphi,\psi,\Phi\in S^\tau\}$
    - Generalización:
      - $Generaliz^\tau=\{(\varphi(c),\forall v\varphi(v)):\varphi=_d\varphi(v)\in F^\tau,Li(\varphi)=\{v\}\text{ y }c\in\mathcal{C}\text{ no ocurre en }\varphi\}$
    - Elección:
      - $Elec^\tau=\{((\exists v\varphi(v),\varphi(e))):\varphi=_d\varphi(v)\in F^\tau,Li(\varphi)=\{v\}\text{ y }e\in\mathcal{C}\text{ no ocurre en }\varphi\}$
- **Regla universal**: Una regla $R$ es llamada universal cuando se da que si $\varphi$ se deduce de $\psi_1,\dots,\psi_k$ por $R$ entonces $((\psi_1\wedge\dots\wedge\psi_k)\to\varphi)$ es una sentencia universalmente válida
  - _Lema_: Sea $\tau$ un tipo, todas las reglas excepto las de elección y generalización son universales

### Axiomas lógicos

- Axiomas lógicos (_verdades universales_) de tipo $\tau$ que consideraremos: Sean $t\in T^\tau_c,\varphi\in S^\tau,\psi\in F^\tau,v\in Var,Li(\psi)\subseteq\{v\}:$
  - $(\varphi\leftrightarrow\varphi)$
  - $(t\equiv t)$
  - $(\varphi\lor\neg\varphi)$
  - $(\varphi\leftrightarrow\neg\neg\varphi)$
  - $(\neg\forall v\psi\leftrightarrow\exists v\neg\psi)$
  - $(\neg\exists v\psi\leftrightarrow\forall v\neg\psi)$
- Denotaremos $AxLog^\tau=\{\varphi\in S^\tau:\varphi\text{ es un axioma lógico de tipo }\tau\}$

### Justificaciones

- **Justificación básica**: Sea $Nombres_1$ el conjunto formado por las siguientes palabras:

  - EXISTENCIA
  - COMMUTATIVIDAD
  - PARTICULARIZACION
  - ABSURDO
  - EVOCACION
  - CONJUNCIONELIMINACION
  - EQUIVALENCIAELIMINACION
  - DISJUNCIONINTRODUCCION
  - ELECCION
  - GENERALIZACION

  Y $Nombres_2$ el conjunto formado por las siguientes palabras:

  - MODUSPONENS
  - TRANSITIVIDAD
  - CONJUNCIONINTRODUCCION
  - EQUIVALENCIAINTRODUCCION
  - DISJUNCIONELIMINACION
  - REEMPLAZO

  Una _justificación básica_ es una palabra perteneciente a la unión de los siguientes conjuntos de palabras:

  - $\{$CONCLUSION, AXIOMAPROPIO, AXIOMALOGICO$\}$
  - $\{\alpha(\bar{k}):k\in N,\alpha\in Nombres_1\}$
  - $\{\alpha(\bar{j},\bar{k}):j,k\in N,\alpha\in Nombres_2\}$
  - $\{DIVISIONPORCASOS(\bar{j},\bar{k},\bar{l}):j,k,l\in N\}$

  Y usaremos $JustBas$ para denotar el conjunto formado por todas las justificaciones básicas.

- **Justificación**: Una justificación es una palabra que pertenece a la unión de los siguientes conjuntos de palabras:

  - $JustBas$
  - $\{\text{HIPOTESIS}\bar{k}:k\in N\}$
  - $\{\text{TESIS}\bar{j}\alpha:j\in N,\alpha\in JustBas\}$

  Usaremos $Just$ para denotar el conjunto formado por todas las justificaciones.

- **Concatenaciones balanceadas de justificaciones**:
  - _Lema_: Sea $\bold{J}\in Just^+$, hay únicos $n\geq 1$ y $J_1,\dots,J_n\in Just$ tales que $\bold{J}=J_1\dots J_n$
    - Es decir que la sucesión $J_1,\dots,J_n$ puede codificarse con la palabra $J_1\dots J_n$ sin perder información
    - Dada $\bold{J}\in Just^+$, usaremos $n(\bold{J})$ y $\bold{J}_1,\dots,\bold{J}_{n(\bold{J})}$ para denotar los únicos $n$ y $J_1,\dots,J_n$ cuya existencia garantiza el lema anterior
  - **Bloques**: Dados números naturales $i\leq j$, usaremos $\langle i,j\rangle$ para denotar el conjunto $\{i,i+1,\dots,j\}$. A los conjuntos de la forma $\langle i,j\rangle$ los llamaremos bloques
  - **Justificación balanceada**: Sea $\mathcal{B}^\bold{J}$ el conjunto de bloques de $\bold{J}\in Just^+$, diremos que $\bold{J}$ es balanceada si se dan las siguientes condiciones:
    1. Por cada $k\in N$ hay a lo sumo un $i$ tal que $\bold{J}_i=\text{HIPOTESIS}\bar{k}$ y a lo sumo un $j$ tal que $\bold{J}_j=\text{TESIS}\bar{k}\alpha$, con $\alpha\in JustBas$
    2. Si $\bold{J}_i=\text{HIPOTESIS}\bar{k}$ entonces hay un $l>i$ tal que $\bold{J}_l=\text{TESIS}\bar{k}\alpha$, con $\alpha\in JustBas$
    3. Si $\bold{J}_i=\text{TESIS}\bar{k}\alpha$ entonces hay un $l<i$ tal que $\bold{J}_l=\text{HIPOTESIS}\bar{k}$
    4. Si $B_1,B_2\in\mathcal{B}^\bold{J}$, entonces $B_1\cap B_2=\emptyset$ o $B_1\subseteq B_2$ o $B_2\subseteq B_1$

### Pares adecuados

- _Lema_: Sea $\varphi\in S^{\tau+}$, hay únicos $n\geq 1$ y $\varphi_1,\dots,\varphi_n\in S^\tau$ tales que $\varphi=\varphi_1\dots\varphi_n$
  - Es decir que la sucesión $\varphi_1,\dots,\varphi_n$ puede codificarse con la palabra $\varphi_1\dots\varphi_n$ sin perder información
  - Dada $\varphi\in S^{\tau+}$, usaremos $n(\varphi)$ y $\varphi_1,\dots,\varphi_{n(\varphi)}$ para denotar los únicos $n$ y $\varphi_1,\dots,\varphi_n$ cuya existencia garantiza el lema anterior
- **Par adecuado**: Un par adecuado de tipo $\tau$ es un par $(\varphi,\bold{J})\in S^{\tau+}\times Just^+$ tal que $n(\varphi)=n(\bold{J})$ y $\bold{J}$ es balanceada
- _Bloques en un par adecuado_: Sea $(\varphi,\bold{J})$ un par adecuado de tipo $\tau$
  - Si $\langle i,j\rangle\in\mathcal{B}^\bold{J}$, entonces $\varphi_i$ será la **hipótesis** del bloque $\langle i,j\rangle$ en $(\varphi,\bold{J})$ y $\varphi_j$ será la **tesis** del bloque $\langle i,j\rangle$ en $(\varphi,\bold{J})$
  - Diremos que $\varphi_i$ está **bajo la hipótesis** $\varphi_l$ en $(\varphi,\bold{J})$ o que $\varphi_l$ es una una hipótesis de $\varphi_i$ en $(\varphi,\bold{J})$ cuando haya en $\mathcal{B}^\bold{J}$ un bloque de la forma $\langle l,j\rangle$ el cual contenga a $i$
  - Sean $i,j\in\langle 1,n(\varphi)\rangle$, diremos que $i$ es **anterior** a $j$ en $(\varphi,\bold{J})$ si $i<j$ y además para todo $B\in\mathcal{B}^\bold{J}$ se tiene que $i\in B\Rightarrow j\in B$
- _Dependencia de constantes en pares adecuados_:
  - **Dependencia directa**: Dadas $e,d\in\mathcal{C}$, diremos que $e$ depende directamente de $d$ en $(\varphi,\bold{J})$ si hay números $1\leq l<j\leq n(\varphi)$ tales que:
    1. $l$ es anterior a $j$ en $(\varphi,\bold{J})$
    2. $\bold{J}_j=\alpha\text{ELECCION}(\bar{l})$ con $\alpha\in\{\varepsilon\}\cup\{\text{TESIS}\bar{k}:k\in N\}$ y $(\varphi_l,\varphi_j)\in Elec^\tau$ vía $e$
    3. $d$ ocurre en $\varphi_l$
  - **Dependencia**: Dados $e,d\in\mathcal{C}$, diremos que $e$ depende de $d$ en $(\varphi,\bold{J})$ si existen $e_0,\dots,e_{k+1}\in\mathcal{C}$ con $k\geq 0$ tales que
    1. $e_0=e$ y $e_{k+1}=d$
    2. $e_i$ depende directamente de $e_{i+1}$ en $(\varphi,\bold{J})$ para $i=0,\dots,k$

### Definición de prueba formal

- **Prueba formal**: Sea $(\Sigma,\tau)$ una teoría de primer orden y $\varphi$ una sentencia de tipo $\tau$, una prueba formal de $\varphi$ en $(\Sigma,\tau)$ será un par adecuado $(\varphi,\bold{J})$ de algún tipo $\tau_1=(\mathcal{C}\cup\mathcal{C}_1,\mathcal{F},\mathcal{R},a)$, con $\mathcal{C}_1$ finito y disjunto con $\mathcal{C}$, tal que:
  1. Cada $\varphi_i$ es una sentencia de tipo $\tau_1$
  2. $\varphi_{n(\varphi)}=\varphi$
  3. Si $\langle i,j\rangle\in\mathcal{B}^\bold{J}$, entonces $\varphi_{j+1}=(\varphi_i\to\varphi_j)$ y $\bold{J}_{j+1}=\alpha\text{CONCLUSION}$, con $\alpha\in\{\varepsilon\}\cup\{\text{TESIS}\bar{k}:k\in N\}$
  4. Para cada $i=1,\dots,n(\varphi)$, se da una de las siguientes:
     1. $\bold{J}_i=\text{HIPOTESIS}\bar{k}$
        - Para algún $k\in N$
     2. $\bold{J}_i=\alpha\text{CONCLUSION}$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$ y hay un $j$ tal que $\langle j,i-1\rangle\in\mathcal{B}^\bold{J}$ y $\varphi_i=(\varphi_j\to\varphi_{i-1})$
     3. $\bold{J}_i=\alpha\text{AXIOMALOGICO}$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$ y $\varphi_i$ es un axioma lógico de tipo $\tau_1$
     4. $\bold{J}_i=\alpha\text{AXIOMAPROPIO}$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$ y $\varphi_i\in\Sigma$
     5. $\bold{J}_i=\alpha\text{PARTICULARIZACION}(\bar{l})$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Partic^{\tau_1}$
     6. $\bold{J}_i=\alpha\text{COMMUTATIVIDAD}(\bar{l})$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Commut^{\tau_1}$
     7. $\bold{J}_i=\alpha\text{ABSURDO}(\bar{l})$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Absur^{\tau_1}$
     8. $\bold{J}_i=\alpha\text{EVOCACION}(\bar{l})$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Evoc^{\tau_1}$
     9. $\bold{J}_i=\alpha\text{EXISTENCIA}(\bar{l})$
        - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Exist^{\tau_1}$
     10. $\bold{J}_i=\alpha\text{CONJUNCIONELIMINACION}(\bar{l})$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in ConjElim^{\tau_1}$
     11. $\bold{J}_i=\alpha\text{DISJUNCIONINTRODUCCION}(\bar{l})$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in DisjElim^{\tau_1}$
     12. $\bold{J}_i=\alpha\text{EQUIVALENCIAELIMINACION}(\bar{l})$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in EquivElim^{\tau_1}$
     13. $\bold{J}_i=\alpha\text{MODUSPONENS}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in ModPon^{\tau_1}$
     14. $\bold{J}_i=\alpha\text{CONJUNCIONINTRODUCCION}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in ConjInt^{\tau_1}$
     15. $\bold{J}_i=\alpha\text{EQUIVALENCIAINTRODUCCION}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in EquivInt^{\tau_1}$
     16. $\bold{J}_i=\alpha\text{DISJUNCIONELIMINACION}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in DisjElim^{\tau_1}$
     17. $\bold{J}_i=\alpha\text{REEMPLAZO}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in Reemp^{\tau_1}$
     18. $\bold{J}_i=\alpha\text{TRANSITIVIDAD}(\bar{l}_1,\bar{l}_2)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1$ y $l_2$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_i)\in Trans^{\tau_1}$
     19. $\bold{J}_i=\alpha\text{DIVISIONPORCASOS}(\bar{l}_1,\bar{l}_2,\bar{l}_3)$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l_1,l_2,l_3$ anteriores a $i$ y $(\varphi_{l_1},\varphi_{l_2},\varphi_{l_3},\varphi_i)\in DivPorCas^{\tau_1}$
     20. $\bold{J}_i=\alpha\text{ELECCION}(\bar{l})$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Elec^{\tau_1}$ vía un nombre de constante $e$, el cual no pertenece a $\mathcal{C}$ y no ocurre en $\varphi_1,\dots,\varphi_{i-1}$
     21. $\bold{J}_i=\alpha\text{GENERALIZACION}(\bar{l})$
         - Con $\alpha\in\{\varepsilon\}\cup\{TESIS\bar{k}:k\in N\}$, $l$ anterior a $i$ y $(\varphi_l,\varphi_i)\in Generaliz^{\tau_1}$ vía un nombre de constante $c$ el cual cumple:
           - $c\notin\mathcal{C}$
           - $c$ no es un nombre de constante que ocurra en $\varphi$ el cual sea introducido por la regla de elección
           - $c$ no ocurre en ninguna hipótesis de $\varphi_l$
           - Ningún nombre de constante que ocurra en $\varphi_l$ o en sus hipótesis, depende de $c$

## El concepto de Teorema

- **Teorema**: Cuando haya una prueba de $\varphi$ en $(\Sigma,\tau)$, diremos que $\varphi$ es un _teorema_ de la teoría $(\Sigma,\tau)$ y escribiremos $(\Sigma,\tau)\vdash\varphi$

## Conteo de modelos módulo isomorfismo

- **Definición**: Diremos que una teoría $T$ tiene, módulo isomorfismo, exactamente una cantidad $n$ de modelos de $m$ elementos si hay $\bold{A}_1,\dots,\bold{A}_n$ estructuras de tipo $\tau$ tales que:
  1. Cada $\bold{A}_i$ es un modelo de $T$
  2. $|A_i|=m$ para cada $i=1,\dots,n$
  3. $\bold{A}_i$ no es isomorfa a $\bold{A}_j$ para $i\neq j$
  4. Si $\bold{A}$ es un modelo de la teoría $T$ y $|A|=m$, entonces $\bold{A}$ es isomorfa a algún $\bold{A}_i$
- _Criterio para saber que dos estructuras no son isomorfas_: Si dos estructuras de tipo $\tau$ son tales que hay una $\varphi\in S^\tau$ la cual vale en una y no en la otra, entonces dichas estructuras no son isomorfas
  - Notar que _no es completo_, es decir, dos estructuras pueden satisfacer las mismas sentencias pero no ser isomorfas

## Propiedades básicas de pruebas y teoremas

- _Lema de cambio de índice de hipótesis_: Sea $(\varphi,\bold{J})$ una prueba formal de $\varphi$ en $(\Sigma,\tau)$ y sea $m\in N$ tal que $\bold{J}_i\neq\text{HIPOTESIS}\bar{m}$ para cada $i=1,\dots,n(\varphi)$. Supongamos que $\bold{J}_i=\text{HIPOTESIS}\bar{k}$ y que $\bold{J}_j=\text{TESIS}\bar{k}\alpha$ con $[\alpha]_1\notin Num$ y sea $\bar{\bold{J}}$ el resultado de reemplazar en $\bold{J}$ la justificación $\bold{J}_i$ por $\text{HIPOTESIS}\bar{m}$ y reemplazar la justificación $\bold{J}_j$ por $\text{TESIS}\bar{m}\alpha$. Entonces $(\varphi,\bar{\bold{J}})$ es una prueba formal de $\varphi$ en $(\Sigma,\tau)$
- _Lema de cambio de constantes auxiliares_: Sea $(\varphi,\bold{J})$ una prueba formal de $\varphi$ en $(\Sigma,\tau)$; $\mathcal{C}_1$ el conjunto de nombres de constante que ocurren en $\varphi$ y que no pertenecen a $\mathcal{C}$; $e\in\mathcal{C}_1$; $\bar{e}\notin\mathcal{C}\cup\mathcal{C}_1$ tal que $(\mathcal{C}\cup(\mathcal{C_1}-\{e\})\cup\{\bar{e}\},\mathcal{F},\mathcal{R},a)$ es un tipo; y $\bar{\varphi_i}=\text{ resultado de reemplazar en }\varphi_i\text{ cada ocurrencia de }e\text{ por }\bar{e}$. Entonces $(\bar{\varphi}_1\dots\bar{\varphi}_{n(\varphi)},\bold{J})$ es una prueba formal de $\varphi$ en $(\Sigma,\tau)$
- _Lema de propiedades básicas de_ $\vdash$: Sea $(\Sigma,\tau)$ una teoría
  1. _Uso de teoremas_: Si $(\Sigma,\tau)\vdash\varphi_1,\dots,\varphi_n$ y $(\Sigma\cup\{\varphi_1,\dots,\varphi_n\},\tau)\vdash\varphi$, entonces $(\Sigma,\tau)\vdash\varphi$
  2. Supongamos $(\Sigma,\tau)\vdash\varphi_1,\dots,\varphi_n$. Si $R$ es una regla distinta de GENERALIZACION y ELECCION, y $\varphi$ se deduce de $\varphi_1,\dots,\varphi_n$ por la regla $R$, entonces $(\Sigma,\tau)\vdash\varphi$.
  3. $(\Sigma,\tau)\vdash(\varphi\to\psi)$ sí y solo sí $(\Sigma\cup\{\varphi\},\tau)\vdash\psi$

## Consistencia

- **Teorías consistentes e inconsistentes**: Una teoría $(\Sigma,\tau)$ será
  - _Inconsistente_ cuando haya una sentencia $\varphi$ tal que $(\Sigma,\tau)\vdash(\varphi\wedge\neg\varphi)$.
  - _Consistente_ cuando no sea inconsistente
- _Lema de propiedades básicas de la consistencia_: Sea $(\Sigma,\tau)$ una teoría
  1. Si $(\Sigma,\tau)$ es inconsistente, entonces $(\Sigma,\tau)\vdash\varphi$ para toda sentencia $\varphi$
  2. Si $(\Sigma,\tau)$ es consistente y $(\Sigma,\tau)\vdash\varphi$, entonces $(\Sigma\cup\{\varphi\},\tau)$ es consistente
  3. Si $(\Sigma,\tau)\not\vdash\neg\varphi$ entonces $(\Sigma\cup\{\varphi\},\tau)$ es consistente

## El teorema de corrección

- _Definición_: Dada $(\Sigma,\tau)$ una teoría, escribiremos $(\Sigma,\tau)\vDash\varphi$ cuando $\varphi$ sea verdadera en todo modelo de $(\Sigma,\tau)$
- _Teorema de Corrección_: $(\Sigma,\tau)\vdash$ implica $(\Sigma,\tau)\vDash\varphi$
- _Corolario_: Si $(\Sigma,\tau)$ tiene un modelo, entonces $(\Sigma,\tau)$ es consistente
- _Idea para probar que una sentencia no es teorema_: Si queremos probar que una sentencia $\varphi\in F^\tau$ no es teorema de una teoría $(\Sigma,\tau)$ basta con encontrar un modelo de $(\Sigma,\tau)$ en el cual $\varphi$ sea falsa
