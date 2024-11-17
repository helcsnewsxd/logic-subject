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

# Guía 13: El álgebra de Lindenbaum

- **Relación**: Sea $T=(\Sigma,\tau)$ una teoría, definimos la siguiente relación binaria sobre $S^\tau$: $\varphi\dashv\vdash_T\psi$ sii $T\vdash(\varphi\leftrightarrow\psi)$
  - Propiedades:
    - $\dashv\vdash_T$ es una relación de equivalencia
    - $\{\varphi\in S^\tau:\varphi\text{ es un teorema de }T\}\in S^\tau/\dashv\vdash_T$
    - $\{\varphi\in S^\tau:\varphi\text{ es refutable en }T\}\in S^\tau/\dashv\vdash_T$
      - Una sentencia $\varphi$ se dice **refutable** en $(\Sigma,\tau)$ si $(\Sigma,\tau)\vDash\neg\varphi$
- **Clases**: Dada una teoría $T=(\Sigma,\tau)$ y $\varphi\in S^\tau$, $[\varphi]_T$ denotará la clase de $\varphi$ con respecto a la relación de equivalencia $\dashv\vdash_T$
- **Operaciones** sobre $S^\tau/\dashv\vdash_T$:
  - $[\varphi]_T s^T [\psi]_T = [(\varphi\lor\psi)]_T$
  - $[\varphi]_T i^T [\psi]_T = [(\varphi\land\psi)]_T$
  - $([\varphi]_T)^{c^T} = [\neg\varphi]_T$
- **Constantes** en $S^\tau/\dashv\vdash_T$:
  - $1^T=\{\varphi\in S^\tau:\varphi\text{ es un teorema de }T\}$
  - $0^T=\{\varphi\in S^\tau:\varphi\text{ es refutable en }T\}$
- **Álgebra de Lindenbaum**: Sea $(\Sigma,\tau)$ una teoría, denotaremos con $\mathcal{A}_T$ a $(S^\tau/\dashv\vdash_T,s^T,i^T,\ ^{c^T},0^T,1^T)$ y será llamada el _álgebra de Lindenbam_ de la teoría $T$.
  - $\mathcal{A}_T$ es un álgebra de Boole
- **Orden parcial**: Denotaremos con $\leq^T$ al orden parcial asociado al álgebra de Boole $\mathcal{A}_T$
  - $[\varphi]_T\leq^T[\psi]_T$ sii $T\vDash(\varphi\to\psi)$
- **Criterio para resolver ejercicios**: Si queremos demostrar que en $\mathcal{A}_T$ se da que $[\varphi]_T\neq[\psi]_T$ entonces basta con encontrar un modelo $\mathbf{A}$ de $T$ tal que $(\varphi\leftrightarrow\psi)$ sea falsa en $\mathbf{A}$. Es decir, deberemos encontrar un modelo el cual haga verdadera a una de las sentencias y falsa a la otra.
