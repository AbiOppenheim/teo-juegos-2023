# Teoría de Juegos - 2023

La **==forma normal==** dada por una matriz de pago en la que los jugadores simultánea e independientemente eligen sus estrategias, es decir toman una decisión individual.

Un **==juego==** es una terna $G = ( I , S , u )$ donde:

- $I = \{1, …, n\}$: conjunto de jugadores
- $S$: estrategias
	- $S_i \neq \empty$: estrategias "puras" (en contraste de "mixtas") para el jugador $i \ \ (1 \leq i \leq n)$
	- Una **estrategia** (strategy profile), es un elemento del conjunto $S=(s_1,\dots,s_n)=S_1\times S_2\times \dots\times S_n = \ \bigtimes_{i\in I}S_i$  
- $u = (u_1, …, u_n): S\to\mathcal{R}^n$: funciones de pago o utilidad
	- Una función de pago $u_i: S\to\mathcal{R}$

---

**==Estrategia i-borrada==** (deleted strategy profile):							

$s_{-i} = (s_1, s_2, \ldots, s_{i-1}, \underset{\uparrow}{\ \ \ \ \ \ }{s_{i+1}}, s_{i+2}, \ldots, s_{n-1}, s_n)$

Representa el "interés" del jugador i-ésimo

---

**==Juegos de suma 0==**

**Idea:** no hay un "banco", o un "pozo" a distribuir

• Sea $G = (X_1 \times … \times Xn, M_1, …, M_n)$

Si $Σ_i M_i(x_1,…,x_n) = 0$ para todo $x_1,…,x_n$, para todo $i$, se dice que $G$ es de suma $0$

• Si $Σ_i M_i(x_1,…,x_n) = \text{cte}$. para todo $x_1,…,x_n$, … se puede decir que es de suma 0 también! (es más general)

- Son usuales los juegos para n = 2 de suma 0.
- En estos casos, lo que gana un jugador lo pierde el otro.
- Se pueden pensar como que un jugador le paga al otro.

**Convención**

- Si $G$ es para 2 de suma 0, lo notamos $G = (X, Y, M)$ donde

	- $X$ e $Y$ son conjuntos 
	- $M$ es una matriz (numérica), 
	- $n = |X|$, $m = |Y|, M \in R^{m\times n}$

	alcanza con dar una sola matriz ya que $M_2(x,y) = -M_1(x,y)$

**Ejemplo con dos jugadores:**

Juegan $I$ vs. $II$ (simultáneamente)

- $I$ elige $x \in X$
- $II$ elige $y \in Y$
- $II$ le paga $M(x, y)$ a $I$

Fin

**Pago:** no es de un pozo, sino de un jugador a otro

---

Un juego $G = (X, Y, M)$ es **==finito==** si $X$ e $Y$ son finitos.

En otro caso, $G$ se dice **==infinito==**.

---

**==Equivalencia==**

Idea: **==relabeling==** de estrategias, borrado de estrategias repetidas (que son innecesarias)

- Si $I$ tiene $x_1, x_2 \in X$, con $M(x_1,y) = M(x_2,y)$ para todo $y \in Y$, entonces puede elminarse $x_2$

**Mas precisamente** 

- Sean $G_1 = (X_1, Y_1, M_1)$ y $G_2 = (X_2, Y_2, M_2)$ dos juegos

- $G_2$ es una reducción de $G_1$, o $G_1$ reduce en $G_2$, notado $G_1 \to G_2$, si vale exactamente una de las condiciones siguientes:

	a. $X_2 = X_1, \exists \ \ f:Y_1\to Y_2$ sobreyectiva / $M_1(x,y) = M_2(x,f(y)) \ \ \ \forall \ \ x\in X_1, y\in Y_1$, ó

	b. $Y_2 = Y_1, \exists \ \ g:X_1\to X_2$ sobreyectiva / $M_1(x,y) = M_2(g(x),y) \ \ \ \forall \ \ x\in X_1, y\in Y_1$

$*$ Una función $f:X\to Y$ es sobreyectiva si $\forall \ \ y\in Y, \ \exists\ \ x\in X, \ f(x)=y$. Es decir, si no hay puntos $y$ en el co-dominio ($Y$) tal que no tengan un $x\in X$ tal que $f(x)=y$

- Si $f$ es biyectiva, significa que se hace *relabeling* de estrategias.

- Si $f$ no es biyectiva, esto equivale a que $G_2$ resulta de una eliminación de estrategias

	duplicadas sobre $G_1$ y luego eventualmente *relabeling*.

	

- Sea $\to_r$ la sub relación de $\to$ definida análogamente a $\to$ pero en donde $f$ no es biyectiva (es decir, se elimina al menos una estrategia de un jugador)

**==Equivalencia de juegos==**

- Se define $G_1 \leftrightarrow G_2 \iff \\ G_1 \to G_2 \or G_2 \to G_1$

	

	i.e. $\leftrightarrow = \leftarrow \cup \rightarrow$ donde $\leftarrow=\rightarrow^{-1}$

	- Se definen $\rightarrow^*$ y $\leftrightarrow^*$ como las clausuras reflexo-transitivas de $\rightarrow$

	- Notación: $\leftrightarrow^* =$ "$\sim$" 

		(es una relación de equivalencia)

- $G_1 \sim G_2$​ denota una **==equivalencia==** de los juegos $G_1$ y $G_2$

- $G = (X, Y, M)$ es **==completamente reducido==** sii

	$x_1 \neq x_2 \Rightarrow \exists \ \ y \ \ M(x_1, y) \neq M(x_2, y) \ \ \and$ 

	$y_1 \neq y_2 \Rightarrow \exists \ \ y \ \ M(x, y_1) \neq M(x, y_2)$

	Intuitivamente, no hay en $M$ filas ni columnas redundantes (sea finito o no)

**Obs:** G es *completamente reducido* $\iff \not\exists \ \ G’ \text{ tal que } G \to_r G’$

​		($\iff \ \ G$ es una forma normal respecto de $\to_r$)

**Proposición**

Todo juego de suma 0 (finito o no) es equivalente a otro completamente reducido. <!--Buscar demo-->

**Def.:** si $G = (X, Y, M), G^t = (Y, X, M^t)$ entonces $G_1 \sim G_2 ⇒ G_1^t \sim G_2^t$

**Def.:** $G_1 = (X_1,Y_1,M_1)$ es **==isomorfo==** a $G_2 = (X_2,Y_2,M_2)$ sii existen biyecciones $f : X_1 \to X_2$ y $g : Y_1 \to Y_2$ tales que $M_1(x_1,y_1) = M_2(f(x_1),g(y_1))$

---

Una estrategia $s_i \in S_i$ se dice **==estrictamente dominada==** para el jugador $i$ si

$\exists \ \ s’_i \in S_i$ tal que $\forall \ \ s_1, …, s_{i-1}, s_{i+1}, …, s_n$ 

​						$u_i(s_1, …, s_i , … s_n) < u_i(s_1, …, s’_i , … s_n) \ \ \  \forall s_i\neq s’_i$ 

En ese caso, diremos que $s_i$ está **estrictamente dominada** por $s’_i$

<u>Idea:</u> una estrategia estrictamente dominada será sin duda peor para el jugador, independientemente de la elección del rival.

**Axioma 1 de racionalidad**: nunca elegir una estrategia dominada estrictamente (independientemente de lo que pueda hacer el oponente)

**Definición (para $n=2$)**

- Sea $G = (X,Y, u)$ con $u = (u_1,u_2)$.

- Relación $\to_e$ **"dominación estricta"**: eliminación de 1 ó más estrategias estrictamente dominadas:

	Sean $x_1, x_2 \in X, y_1, y_2 \in Y$, decimos que

	$x_1$ *domina estrictamente* a $x_2$ sii $\forall \ \  y \ \  u_1(x_1, y) > u_1(x_2, y)$

	$y_1$ *domina estrictamente* a $y_2$ sii $\forall \ \ x \ \  u_2(x, y_1) > u_2(x, y_2)$

$G \to_e G’$ si $G’$ es el resultado de eliminar una estrategia dominada (de uno u otro jugador)

- Relación $\to^*_e$: es la clausura reflexo-transitiva de $\to_e$

- $G$ es *resoluble por dominación estricta* sii $\exists X’,Y’,u \ \ \ G\to^*_e (X’,Y’,u’) \and |X’| = |Y’| = 1$

	es decir si existe una secuencia de eliminaciones de estrategias estrictamente dominadas que culmina en un juego trivial.

**Definición (para $n=2$)**

- Sea $G = (X,Y, u)$ con $u = (u_1,u_2)$.

- Relación $\to_d$ **"dominación débil"**: eliminación de 1 ó más estrategias débilmente dominadas:

	Sean $x_1, x_2 \in X, y_1, y_2 \in Y$, decimos que

	$x_1$ *domina débilmente* a $x_2$ sii $\forall \ \  y \ \  u_1(x_1, y) \geq u_1(x_2, y) \ \ \and \ \ \exists \ \ y \ \ u_1(x_1,y)>u_1(x_2,y) $

	$y_1$ *domina débilmente* a $y_2$ sii $\forall \ \ x \ \  u_2(x, y_1) > u_2(x, y_2) \ \ \and \ \ \exists \ \ x \ \ u_2(x,y_1)>u_2(x,y_2) $

$G \to_d G’$ si $G’$ es el resultado de eliminar una estrategia *débilmente* dominada (de uno u otro jugador)

- Relación $\to^*_d$: es la clausura reflexo-transitiva de $\to_d$

- $G$ es *resoluble por dominación débil* sii $\exists X’,Y’,u \ \ \ G\to^*_d (X’,Y’,u’) \and |X’| = |Y’| = 1$

	es decir si existe una secuencia de eliminaciones de estrategias débilmente dominadas que culmina en un juego trivial.

**<u>Algoritmo:</u> Para resolver un juego por dominación estricta:**

```
repetir
	borrar las estrategias estrictamente dominadas de 1
	borrar las estrategias estrictamente dominadas de 2
hasta que no haya borrado posible
si sólo sobrevivió una estrategia conjunta, 
	el juego es resoluble por dominación estricta
```

Para dominación débil, es análogo

**Obs:**

- Si $G \to^*_d (X’,Y’,u’)$ con $|X’| = 1 \or |Y’| = 1$ entonces $G \to^*_d (X’’,Y’’,u’’)$ con $|X’’| = |Y’’| = 1$

- No todo juego finito es resoluble por dominación (ni estricta ni débil), es decir

	$\exists \ \ G$ finito $\forall \ X’ \ \ \forall \ Y’ \ \ \forall \ u’ \ \ G \to^*_{d/e} (X’,Y’,u’) ⇒ |X’| > 1 \and |Y’| > 1$

---

**==Equilibrio de Nash==**

**Def.:** Sea G en forma normal para $n$ jugadores con $S_1.,…,S_n$ los conjuntos de estrategias respectivamente, y sea la estrategia conjunta $(s_1,…,s_n) \in S_1 \times … S_n$.

Se dice que $(s_1,…,s_n)$ es un equilibrio de *Nash estricto* sii $u_i(s_1, …, s_{i-1}, s_i, s_{i+1}, …, s_n) > u_i (s_1, …, s_{i-1}, s’_i, s_{i+1}, …, s_n)$ para todo $1 \leq i \leq n, s’i \in S_i, s’_i \neq s_i$.

Se dice que $(s_1,…,s_n)$ es un equilibrio de *Nash débil* sii $u_i(s_1, …, s_{i-1}, s_i, s_{i+1}, …, s_n) \geq u_i (s_1, …, s_{i-1}, s’_i, s_{i+1}, …, s_n)$ para todo $1 \leq i \leq n, s’_i \in S_i$.

- Una estrategia conjunta tal que para cada jugador lo mejor es **mantener su estrategia individual si supone que todos los demás harán lo mismo**. 
- Una situación estable de la cual nadie se desea ir si los demás tampoco.

---

**==Mejor respuesta (BR)==**

Recordar la def. de una *estrategia i-borrada*: si $s = (s_1,…,s_n), s_{-i} = (s_1,…,s_{i-1},s_{i+1},…,s_n)$

Dado $s = (s_1,…,s_n)$, diremos que si es una **mejor respuesta** a $s_{-i}$, sii $u_i(s_1,…,s_{i-1},s_i,s_{i+1},…,s_n) \geq u_i(s_1, …, s_{i-1}, s’_i, s_{i+1}, …, s_n)$ para todo $1 \leq i \leq n, s’_i \in S_i$.

**Def.:** $\text{BR}_i(s_{-i})= \{s_i / s_i \text{ es una mejor respuesta a} \ s_{-i}\}$

- Si $G$ para $n$ jugadores es finito, $\text{BR}_i(s_{-i}) \neq \empty \ \ \forall \ \ i \in I \ \ \ \forall \ \ s \in  S$

- En un juego de dos jugadores, $(s_1 , s_2)$ es un equilibrio de Nash débil si y sólo si la estrategia $s_1$ de 1 es una mejor respuesta a la estrategia $s_2$ de 2, y la estrategia $s_2$ de 2 es una mejor respuesta a la estrategia $s_1$ de 1.

	$(s_1 , s_2)$ es un NE $\iff s_1 \in BR_1(s_2) \and s_2 \in BR_2(s_1)$

**Proposición**

• En un juego de $n$ jugadores, si al aplicar (iteradamente) la eliminación de estrategias estrictamente dominadas <u>queda una única estrategia</u> $(s_1^*, s_2^*, ..., s_n^*)$, **entonces esta es el único equilibrio de Nash**.

• En un juego de $n$ jugadores, **todo equilibrio de Nash sobrevive al proceso de eliminación de estrategias estrictamente dominadas. Pero también pueden sobrevivir otras que no sean equilibrios de Nash.**

---

**==Valor bajo (puros)==**

Dado $G = (X, Y, M)$ (finito o no), se define el **valor bajo** de $G$ para $x_0 \in X$

​														$\Lambda_G(x_0) = \text{inf}_{y\in Y} M(x_0, y)$

**Intuición:** es lo peor que le puede pasar a columna si elige $x_0$ (pensar en forma pesimista, en un oráculo o en un espía)

**==Valor inferior de un juego==**

Dado $G = (X, Y, M)$ (finito o no), se define el **valor inferior** de $G$

​														$\lambda^*_G = \text{sup}_{x\in X} \Lambda_G(x) = \text{sup}_{x\in X}\ \ \text{inf}_{y\in Y} M(x, y)$

**Intuición:** es a lo más que puede aspirar columna con total certeza si su rival es racional; su mejor opción posible

**==Valor alto (puros)==**

Dado $G = (X, Y, M)$ (finito o no), se define el **valor alto** de $G$ para $y_0 \in Y$

​														$\Upsilon_G(y_0) = \text{sup}_{x\in X} M(x, y_0)$

**Intuición:** es lo peor que le puede pasar a fila si elige $y_0$ (pensar en forma pesimista, en un oráculo o en un espía)

**==Valor superior de un juego==**

Dado $G = (X, Y, M)$ (finito o no), se define el **valor superior** de $G$

​														$\upsilon^*_G = \text{inf}_{y\in Y} \Upsilon_G(y) = \text{inf}_{y\in Y}\ \ \text{sup}_{x\in X} M(x, y)$

**Intuición:** es a lo más que puede aspirar fila con total certeza si su rival es racional; su mejor opción posible



**Proposición**

Sea $G = (X, Y, M)$ (finito o no).

Para todo $x_0 \in X, y_0 \in Y,$ 						$\Lambda_G(x_0)\leq\Upsilon_G(y_0) \\ \lambda^*_G \leq \upsilon^*_G$

**==Valor de un juego==**

Dado $G = (X, Y, M)$ (finito o no), si  $\lambda^*_G = \upsilon^*_G$ entonces este número se llama el **==valor puro==** de $G$, y se dice que $G$ tiene valor puro.

**Observación:** El valor puro, <u>si existe, es único.</u>

- Para $G$ finito, representa al menos un elemento en la matriz, máximo en su fila y mínimo en su columna. Es un *punto silla*.
- Para $G$ infinito, no necesariamente hay un elemento que alcanza este límite.

"Si jugamos una única vez, el valor puro significa lo más a lo que puedo aspirar (lo peor que me puede pasar) siendo ambos racionales (e infalibles). Es decir, <u>cuánto puedo ganar en el peor caso para mí y en el peor caso para el oponente, a la vez.</u>"



**Proposición**

Sean $G_1 = (X_1, Y_1, M_1), G_2 = (X_2, Y_2, M_2)$.

Si $G_1 \sim G_2$, entonces

​										$\lambda^*_{G_1} = \lambda^* _{G_2}\\ \upsilon^*_{G_1} = \upsilon^*_{G_2}$

En particular si $G_1$ tiene valor, entonces $G_2$ también y ambos valores coinciden.

*Dem.* Ver que $G_1 \to G_2 ⇒ \lambda^*_{G_1} = \lambda^* _{G_2}\ \and \ \upsilon^*_{G_1} = \upsilon^*_{G_2}$

**Corolario (inmediato)**

Sean $G_1 = (X_1, Y_1, M_1), G_2 = (X_2, Y_2, M_2)$.

Si $G_1 \simeq G_2$, entonces

​										$\lambda^*_{G_1} = \lambda^* _{G_2}\\ \upsilon^*_{G_1} = \upsilon^*_{G_2}$

En particular si $G_1$ tiene valor, entonces también $G_2$ y ambos valores coinciden.

---

**==Juegos dinámicos de información completa==**

- Hay un <u>conjunto finito de jugadores</u>.
- Se sabe quién mueve cuándo y qué opciones tiene.
- Qué saben los jugadores cuando mueven.
- Se saben los pagos determinados por sus opciones.
- Todo esto es conocimiento común de todos.



- ==**Información perfecta**==

	Cada jugador sabe quién hizo qué decisión, cada vez que tiene la oportunidad de decidir algo.

	- Todas las jugadas previas se observan antes de que la próxima jugada sea hecha.
	- Todo jugador sabe quién hizo qué cosa antes de toda decisión
	- Estos juegos se caracterizan por tener carácter
		- secuencial
		- con estados

- ==**Información imperfecta**==

	Un jugador podría no conocer las decisiones de otro, hasta el final.



**Árbol de juego (forma extensiva)**

- En un árbol de juego, una estrategia para un jugador queda representada por un <u>conjunto de ejes</u>, uno partiendo desde cada nodo en que aquel mueve.
- Una combinación de estrategias (conjuntos de ejes), uno por jugador, induce un camino de la raíz a un <u>nodo terminal</u>, lo que <u>determina el pago</u> a cada uno de los jugadores. 

**==Forzar el pago==**

En un juego de información perfecta, estudiaremos casos en que un jugador *puede forzar a que el pago pertenezca a un conjunto determinado.*

- Equivale a que tenga una estrategia que garantiza recibir un pago en ese conjunto sin importar la que elija el otro jugador.
- Para abreviar, en lugar de *forzar el pago en*, escribiremos sólo *forzar*.



- Sea $G$ para 2 jugadores ($I$ y $II$), finito, suma 0 e información perfecta, con matriz de pagos $M$.
- Sea $R = \text{Im}(M) \subseteq \R$, la imagen o conjunto de pagos posibles.
- Como $G$ es finito, $R$ es finito.

**Def.** Sea $S\subseteq R$. Diremos que $I$ puede forzar $S \ \iff$

**i)** $\exists \ x_1 \ \forall \ y_1 \ \exists \ x_2  \ \forall \ y_2\dots M(x,y) \in S$

​		**(si $I$ hace el movimiento inicial)**

**ii)** $\forall \ y_1 \ \exists \ x_1  \ \forall \ y_2 \ \exists \ x_2 \dots M(x,y) \in S$

​		**(si $II$ hace el movimiento inicial)**

donde $x_1, y_1, x_2, y_2\dots$ son los sucesivos movimientos.

**Todo esto sin pérdida de generalidad ante posibles secuencias de distintas longitudes.**

En realidad es un bosquejo, se debería usar inducción.

Análogamente definimos cuando $II$ puede forzar $S$.



**Lema del complemento**

Sea $S\subseteq R$, y $G$ con las condiciones anteriores.

Entonces:

​														$\text{jugador } I \text{ puede forzar } S \\ \or \\ \text{jugador } II \text{ puede forzar } R – S$

(i.e., el complemento de $S$)

**Observación**: El lema no vale si se quita la hipótesis de información perfecta.

<u>Ejemplo:</u>

 $G = MP, R = \{-1,1\} \\S = \{1\}, R – S = \{-1\}$.

Ni $I$ puede forzar $S$ ni $II$ puede forzar $R – S$.

*(Peor aún, ninguno puede forzar ninguno de ambos conjuntos unitarios.)*



**Lema:** Sea $G$ con las condiciones anteriores, $v \in \R$.

Entonces:

- $v \leq \lambda^*_G \iff I \text{ puede forzar } \{ u \in \R \ / \ u \geq v \}$.
- $v \geq \upsilon^*_G \iff II \text{ puede forzar } \{ u \in \R \ / \ u \leq v \}$.

**Dem.**

- La primera afirmación se debe a que $I$ puede elegir una estrategia que le garantice un pago de hasta $\lambda^*_G$, no importa lo que elija $II$, pero no un pago mayor.
- Análogamente para la segunda afirmación.



**Corolario**

Sea $G$ con las condiciones anteriores, $v \in \R$.

Si $I$ puede forzar $\{u \in \R \ / \ u \geq v \}$ 	y 	$II$ puede forzar $\{ u \in \R \ / \ u \leq v \}$ 

​		entonces $G$ tiene valor y este es $v$.

Otro camino era adoptar esta condición como definición del valor de un juego para 2 jugadores de suma 0 e información perfecta. (Ver libro de Binmore.)



**==Teorema de Zermelo==**

- **Todo juego de 2 jugadores de suma 0 e información perfecta tiene valor.**
- Además, si el juego es finito, existe una estrategia combinada que alcanza ese valor.

**Def:**  

- Un juego $G = (X, Y, M)$ de suma 0 se dice que es de **información perfecta de nivel n**…

	- **Nivel 0**

		sii $M$ es constante.

	- **Nivel n+1** 

		sii al mover alguien se obtiene un juego de información perfecta de nivel $n$ o menos.

- Sea $G = (X, Y, M)$ un juego de suma 0. $G$ es de **información perfecta** sii es de información perfecta para algún $n \geq 0$, en ese caso diremos que **$n$ es el nivel de $G$.**



**Lema:** 

Sea $G = (X, Y, M)$ de suma 0 (finito o no). 

Si existen $x^* \in X$, $y^* \in Y$, tales que 

​						$\Lambda_G(x^*) \geq \Upsilon_G(y^*)$, 

entonces 		$\Lambda_G(x^*) = \Upsilon_G(y^*) = \lambda^*_G = \upsilon^*_G$. 

**Dem.:**

$\begin{align*} \lambda^*_G =  \sup_x \Lambda_G(x) &\geq \Lambda_G(x^*) \geq \Upsilon_G(y^*) \geq \inf_y \Upsilon_G(y) = \upsilon^*_G \end{align*}$ 

y por una proposición anterior $\lambda^*_G \leq \upsilon^*_G$.



**Corolario**

- **La matriz de un juego finito de suma 0 e información perfecta tiene algún punto silla, y ese valor es el valor del juego.**
	- En la situación finita anterior, es la estrategia conjunta $(x^*, y^*)$.
	- No vale la recíproca: podría haber otros puntos silla.
- **En todo juego de dos jugadores de suma 0 e información perfecta con conjunto de pagos simétrico con respecto al $0$** (por ej. el ajedrez y otros mencionados),  **al menos uno de ambos jugadores puede asegurarse $\geq 0$** (el “empate” o algún resultado mejor, es decir “no perder”).
	- *Dem.* Por el teorema de Kuhn y por casos según el valor sea $\geq 0$ o $\leq 0$.

---

**==Estrategia mixta==**

Sea $\Delta(S_i) =$ { distribuciones de probabilidad sobre $S_i$ } $= \{\sigma : S_i \to \R_{\geq 0} \ \ / \ \ \sum_{j=1,…,n}\sigma_i(s_j) = 1\}$ donde $S_i = \{s_1, …, s_m \}, m = |S_i|$.

Una estrategia mixta de un jugador es una distribución de probabilidad sobre el conjunto de sus estrategias. Si un jugador $i$ tiene estrategia $S_i=\{s_{i1},s_{i2},\dots,s_{ik}\}$ entonces una estrategia mixta para el jugador $i$ le asigna a cada estrategia pura $s_i\in S_i$ una probabilidad $0 \leq \sigma_i(s_i)\leq 1$ que jugará, donde $\sum_{s_i\in S_i}\sigma_i(s_i)=1$



- Una estrategia *mixta* para el jugador i-ésimo es una $\sigma \in \Delta(S_i)$.
- Ahora el juego no consiste en que cada jugador elija una $s \in S_i$ sino una $\sigma \in \Delta(S_i)$.

**Ejemplo** (Matching pennies) :

- El jug 1 tiene dos estrategias puras: C y S, pero infinitas estrategias mixtas (y lo mismo para el jug 2).
- Ejemplos:
	- $( \sigma_1(C) = 0.3 , \sigma_1(S) = 0.7 )$ es una estrategia mixta
	- $( \sigma_1(C) = 0.5 , \sigma_1(S) = 0.5 )$ es una estrategia mixta
	- $( \sigma_1(C) = 1 , \sigma_1(S) = 0 )$ es una estrategia mixta

**¿Cómo medimos el pago?**

- Es una forma de estudiar el juego iterado.
- El pago no es determinista.
- Podemos estudiar el <u>*pago esperado*</u>.
- Eso haremos para definir $M’$.
- Por un lado parece que tenemos otro mecanismo de juego.
- Sin embargo, no cambia: vía esta nueva $M’$, tenemos otro juego en forma normal.

**Notación**

- Si $x\in X$, podemos notar con $\mathcal{X}_x \in \Delta(X)$ a

	$\mathcal{X}_x(s) = \begin{cases}    1 & \text{si } s=x, \\    0 & \text{si } s \neq x. \end{cases}$

- Si $y\in Y$, podemos notar con $\mathcal{X}_y \in \Delta(Y)$ a

	$\mathcal{X}_y(s) = \begin{cases}    1 & \text{si } s=y, \\    0 & \text{si } s \neq y. \end{cases}$



- En el contexto de $M’$, en lugar de $\mathcal{X}_x$ escribiremos simplemente $x$.

	*Ejemplo:* $M’(x, \eta) = M’(\mathcal{X}_x, \eta)$.

- Del mismo modo, en lugar de $\mathcal{X}_y$ escribiremos simplemente $y$.

	*Ejemplo:* $M’(\xi, y) = M’(\xi, \mathcal{X}_y)$.

**Observación:** 

- El pago esperado para $X$ si $X$ elige $x$ e $Y$ elige $\eta$ es: 

	$M'(x, \eta) = \sum_{y \in Y} M(x, y) \eta(y)$

- El pago esperado para $X$ si $X$ elige $\xi$ e $Y$ elige $y$ es:  

	$M'(\xi, y) = \sum_{x \in X} M(x, y) \xi(x)$

- El pago esperado para $X$ si $X$ elige $x$ e $Y$ elige $y$ es simplemente: 

	$M'(x, y) = M(x, y)$

- Finalmente, el pago esperado para $X$ si $X$ elige $\xi$ e $Y$ elige $\eta$ es 

	$M’(\xi,\eta) = \sum_{x\in X} \sum_{y\in Y} \ \ M(x, y) \ \ \xi(x) \ \eta(y)$

Para un juego general, que no sea necesariamente de suma $0$, usaremos en la notación $u_i$ (o $u’_i$) en lugar de $M$ y $–M$.



##### Ejemplo

|       |  L   | R    |
| ----: | :--: | ---- |
| **U** | 2,3  | 3,4  |
| **D** | 1,2  | 6,0  |

- Estrategia mixta para el jugador 1: $σ_1(\frac{1}{3},\frac{2}{3})$ 
- Estrategia mixta para el jugador 2: $σ_2(\frac{1}{4},\frac{3}{4})$ 
- Estrategia mixtas $\sigma=(\sigma_,\sigma_2)$
- Pago esperado para el jugador 1 jugando U es $\frac{1}{4}\cdot 2+\frac{3}{4}\cdot3=\frac{11}{4}$
- Pago esperado para el jugador 2 jugando L es $\frac{1}{3}\cdot 3+\frac{2}{3}\cdot 2=\frac{7}{3}$

**==Extensión mixta de un juego==**

Extendemos entonces $G$ mediante el juego $E(G)$ del siguiente modo:

Dado $G = (X, Y, u_1, u_2)$, se define

$E(G) = (\Delta(X),\Delta(Y), u_1’, u_2’)$, donde

$u_i’(\xi, \eta) = \sum_{x\in X} \sum_{y\in Y} u_i(x, y) \xi(x) \eta(y), i = 1, 2$

Notación para suma 0:

$M’(\xi, \eta) = \sum_{x\in X} \sum_{y\in Y} M(x, y) \xi(x) \eta(y)= \sum_{x\in X, \ y\in Y} M(x, y) \xi(x) \eta(y)$



- Como $|\Delta(S_i)|$ es infinito (si $S_i$ es no trivial), $E(G)$ es un juego infinito.
- Sin embargo, veremos que algunas de las propiedades de los juegos finitos persisten y otras “mejoran”.
- Eso es en parte lo que hace atractivo el estudio de extensiones mixtas.



**Recordar**: Sea $G = (X, Y, M)$ un juego finito de suma 0, y $G = E(G) = (\mathcal{X}, \mathcal{Y}, M’)$ su extensión mixta.

- Si $x\in X$, y $\eta\in\mathcal{Y}$, entonces

	$M'(x, \eta) = \sum_{y \in Y} M(x, y) \eta(y)$

- Si $\xi\in \mathcal{X}$, y $y\in Y$, entonces

	$M'(\xi, y) = \sum_{x \in X} M(x, y) \xi(x)$

- Si $\xi\in \mathcal{X}, \eta\in \mathcal{Y}$, entonces

	$M’(\xi,\eta) = \sum_{x\in X} \sum_{y\in Y} \ \ M(x, y) \ \ \xi(x) \ \eta(y)$

**==Lema (purificación)==**

- Sea $G = (X, Y, M)$ un juego finito de suma cero, 

- $\Gamma = E(G) = (\mathcal{X}, \mathcal{Y}, M')$ su extensión mixta, $x^* \in X$, $\eta \in \mathcal{Y}$. 

- Supongamos que $M'(x^*, \eta) \geq M'(x, \eta)$ para toda $x \in X$. 

	Es decir, **contra $\eta, x^*$ es mejor o igual que cualquier otra estrategia pura.** 

- Entonces, $M'(x^*, \eta) \geq M'(\xi, \eta)$ para toda $\xi \in \mathcal{X}$. 

	Es decir, **no hay otra estrategia mixta que supere a $x^*$.** 

- Análogamente para el otro jugador: 

	$\forall \ \ y \ \ M'(\xi, y^*) \leq M'(\xi, y) \Rightarrow \forall \ \eta \ M'(\xi, y^*) \leq M'(\xi, \eta)$.

Un equilibrio de Nash de estrategia mixta es un perfil de estrategia mixta $\sigma^*=(\sigma^*_i, \sigma^*_{-i})$ con la propiedad de que ningún jugador $i$ tiene una estrategia mixta $\sigma_i$ tal que prefiera el resultado del perfil $\sigma=(\sigma_i, \sigma^*_{-i})$ sobre el resultado del perfil de estrategia $\sigma=(\sigma^*_i, \sigma^*_{-i})$.

Equilibrio de Nash de estrategia mixta: 

- Para cada jugador $i \in N$, $U_i(\sigma^*_i, \sigma^*_{-i}) \geq U_i(\sigma_i, \sigma^*_{-i})$ para todo $\sigma_i \in \Delta(S_i)$, donde $\Delta(S_i)$ es el conjunto de distribuciones de probabilidad sobre $S_i$ con elemento típico $\sigma_i$.
- Un perfil de estrategia mixta $\sigma^*=(\sigma^*_1, \ldots, \sigma^*_n)$ es un equilibrio de Nash si y solo si para cada jugador $i$, $\sigma^*_i$ es una mejor respuesta a $\sigma^*_{-i}$.

**Demostración**

Sólo para la primera afirmación ya que la segunda es análoga.

Sea $\xi\in\mathcal{X}$.

$\begin{align*} M’(x^*, \eta) = M’(x^*, \eta) \cdot 1 &= \sum_{x\in X} M’(x^*, \eta) \xi(x) \\ &\geq \sum_{x\in X} M’(x, \eta) \xi(x) \\ &= \sum_{x\in X} (\sum_{y \in Y} M(x, y) \eta(y)) \xi(x) \\ &= \sum_{x\in X} \sum_{y\in Y} M(x, y) \xi (x) \eta(y) = M’(\xi, \eta) \end{align*}$

**Corolario**

- Sea $G = (X, Y, M)$ un juego finito de suma 0, y $\Gamma = E(G) = (\mathcal{X}, \mathcal{Y}, M’)$ su extensión mixta.

- Para el cálculo del valor bajo de la estrategia mixta $\xi$ del jugador $X$

  $\Lambda_\Gamma(\xi) = \inf_{\eta\in\mathcal{Y}} M’(\xi, \eta)$

  basta con considerar la peor estrategia pura $y$ de $Y$ que haya contra $\xi$:

  $\Lambda_\Gamma(\xi) = \inf_{y \in Y} M’(\xi, y)$

  Es decir, **ante una mixta fija de $X$, la peor pura de $Y$ es tan perjudicial como la peor mixta de $Y$.**

- Análogamente para $\eta$ del otro jugador, es decir 

	$\Upsilon_\Gamma(\eta) = \sup_{\xi\in\mathcal{X}} M’(\xi, \eta) = \sup_{x\in X}M'(x,\eta)$

**Proposición**

Sea $G = (X, Y, M)$ un juego finito de suma 0, y $G = E(G) = (\mathcal{X}, \mathcal{Y}, M’)$ su extensión mixta.

Si $\xi \in \mathcal{X}, \eta \in \mathcal{Y}$, entonces

- $\Lambda_\Gamma(\xi) = \inf_{y\in Y} M’(\xi, y) \ \ \lambda^*_G \leq \lambda^*_\Gamma$
- $\Upsilon_\Gamma(\eta) = \sup_{x\in X} M’(x, \eta) \ \ \upsilon^*_G \geq \upsilon^*_\Gamma$

**Dem.**

$\lambda^*G = \sup_x \inf_y M(x, y) \ \leq \ \sup_\xi  \inf_y M’(\xi, y) \ = \ \sup_\xi \Lambda_\Gamma(\xi) = \lambda^*_\Gamma$

Esto significa que, al considerar los valores esperados, la máxima garantía de ganancia del jugador no empeora con respecto al juego original puro (podría mejorar o quedar igual).