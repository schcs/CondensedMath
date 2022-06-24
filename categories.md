# Categorias

Uma categoria $C$ consiste de 

- objetos $A$, $B$, $C$
- para cada par de objetos $A$ e $B$, uma coleção $H(A,B)$ de morfismos (mapas, setas, etc) $A\to B$. 

Outra notação: $\mbox{Hom}(A,B)$, $C(A,B)$, $H_C(A,B)$, $Hom_C(A,B)$.

Para objetos $A$, $B$, $C$ temos uma função 
$$H(A,B) \times H(B,C)\to H(A,C),\quad (f,g)\mapsto f\circ g.$$
Esta função chama-se composição. Para cada objeto $A$ temos $1_A\in H(A,A)$ tal que 
$$1_B\circ h=h,\ h\circ 1_A=h,\ (f\circ g)\circ h=f\circ(g\circ h)$$
para todo $h\in H(A,B)$, $g\in H(B,C)$ e $f\in H(C,D)$. Se $f\in H(A,B)$. então $A$ é o domínio de $f$ e 
$B$ é o codomínio.

## Exemplos

As seguintes são os exemplos mais comuns de categorias:

- __Set__: Os objetos são conjuntos, os mapas são mapas entre conjuntos.
- __Grp__: Os objetos são grupos, e os mapas são homomorfismos entre grupos. 
- __Ring__: Os objetos são anéis (com $1$), e os mapas são homomorfismos entre anéis.
-- __CRing__: Os objetos são anéis comutativos (com $1$), e os mapas são homomorfismos entre anéis 
computativos.
- __Vect_k__: Os objetos são espaços vetoriais sobre um corpo $k$ e os objetos são aplicações $k$-lineares.
- __$R$-Mod__: Os objetos são $R$-módulos (à esquerda) e os mapas são $R$-homomorfismos. 
- __Top__: Os objetos são espaços topológicos e os mapas são funções contínuas.


Um mapa $f\in H(A,B)$ é dito __isomorfismo__, se existir $g\in H(B,A)$ tal que $fg=1_B$ e $gf=1_A$. 

### Outros exemplos, 
- $\emptyset$ com nenhum objeto e nenhuma seta 
- $\{1\}$ com um objeto e uma seta $1_1$  
- $A\to B$ com dois objetos e três setas $1_A$, $1_B$, $A\to B$. 
- Um monoide $M$ pode ser visto como uma categoria com um objeto $A$ e uma seta associada com cada elemento de $M$. A identidade de $M$ corresponde a $1_A$ e a associatividade do monoide corresponde à associatividade da composição.
- Um grupo $G$ pode ser visto como  uma categoria com um objeto $A$ e uma seta  associada com cada elemento de $G$. Neste caso toda seta da categoria é um isomorfismo.
- Um grupo $G$ pode ser visto como uma categoria com apenas um objeto e todas setas invertíveis. 
- Se $P$ é um conjunto parcialmente ordenado, então $P$ pode ser vista como uma categoria. Os objetos da categoria são os elementos de $P$ e temos $\alpha\to\beta$ na categoria se e somente se $\alpha\leq \beta$.

## Categoria oposto o dual. 

Seja $C$ uma categoria. Os objetos de $C'$ são os mesmos, $1_A$ é o mesmo, e $H_{C'}(A,B)=H_C(B,A)$. 

## Functores

Functor covariante

Sejam $C$ e $D$ categorias. Um functor $F:C\to D$ associa
-- cada objeto $A\in C$ com um objeto $F(A)\in D$
-- uma função $F:H(A,B)\to H((F(A),F(B))$
tal que 
\[
    F(1_A)=1_{F(A)}\quad\mbox{e}\quad F(fg)=F(f)F(g).
\] 


### Functor de esquecimento
- Grp -> Set, Ring -> Set, Ring -> Grp, R-mod -> Ab, Ab -> Grp. 

### Functores livres
- Set -> Grp, Set -> Vec_k, Set -> R-mod, Set -> CRing, etc

Um functor contravariante entre $C$ e $D$ é um functor $C' -> D$.

### Example

Functor Top -> CRing, $X\mapsto C(C,\mathbb R)$. Se $f: X->Y$, então $F(f): F(Y)\to F(X)$ com $F(f)(\psi)=f\psi$. 

Spec: CRing -> Top, $R\mapsto Spec(R)$. 

Um functor $F:C\to D$ é dito fiel (cheio, full) se os mapas $H(A,B)->H(F(A),F(B))$ são injetivos (sobrejetivos). 

Subcategoria $D$ contém objetos de $C$ e $H_D(A,B)\subseteq H(A,B)$. Subcategoria cheia se $H_D(A,B)= H(A,B)$. Por exemplo, Ab é uma subcategoria de Grp.

## Transformação natural

Sejam $C$ e $D$ categorias e $F,G: C\to D$ functores. Uma transformação natural $\alpha$ entre $F$ e $G$ é composta por uma família de morfismos 
$\alpha_A:F(A)\to G(A)$ tal que para todo mapa $f:A -> B$ temos que o diagrama 

F(A) -> F(B)
 |       |
 v       v
G(A) -> G(B)
comuta. 

### Exemplos

Seja $C$ uma categoria discreta sobre um conjunto $X$. Então $C$ não tem setas, exceto $1_x$ para todo $x\in X$. Seja $D$ uma categoria qualquer. Então 
functores $F,G:C\to D$ escolhem um elemento $F(x)$ e $G(x)$ para cada $x \in X$. Uma transformação natural $\alpha$ é uma coleção de mapas 
$\alpha_x:F(x)\to G(x)$.   


Exemplo. Considere $F,G:CRing -> Grp$. $F(R) = GL_n(R)$, $G(R)=R^*$. Afirmamos que $\det_R:GL_n(R) -> R^*$ é uma transformação natural. 

Transformações naturais podem ser compostas. Se $F,G,H:C->D$ functores, $\alpha:F\to G$, $\beta:G\to H$ são transformações naturais, então a composição $\beta\alpha$ é transformação natural $F\to H$. A identidade $1_{F(A)}:F(A)\to F(A)$ natural $F\to F$. Assis se $C$ e $D$ são categorias, então 
a categoria dos funtores $[C,D]$ tem objetos functores entre $C$ e $D$ a as transformações naturais como morfismos. 

Isomorphismo natural entre $F$ e $G$ é uma transformação natural $\alpha$ tal que $\alpha_A:F(A)\to G(A)$ é um isomorfismo.

Exercício: Isomorphismo natural é um isomorfismo na categoria dos functores. Neste caso os functores $F$ e $G$ são naturalmente isomorfos. 

Dados dois functores $F,G:C\to D$. Dizemos que $F(A)$ e $G(A)$ são naturalmente isomorfos se $F$ e $G$ são naturalmente isomorfos. 

### Duplo dual

Seja $V$ e $W$ espaços vetoriais. Para $\alpha: V\to W$, temos que $\alpha^*=-\circ \alpha$ e $\alpha^{**}(\beta) = \beta(-\circ \alpha)$. 
Temos que $v\mapsto \varphi_v$ é um mapa de $V\to V^{**}$ onde $\varphi(v)(\beta)=\beta(v)$. Precisa provar que 
$\alpha^{**}(\varphi_v)=\varphi(\alpha_v)$. Mas isso segue dos fatos que 
\[
    \alpha^{**}(\varphi_v)(\beta)=\varphi_v(-\circ\alpha)(\chi)=\varphi_v(\chi\circ\alpha)=\chi(\alpha(v))
\]
e 
\[
    \varphi_{\alpha(v)}(\chi)=\chi(\alpha(v)).
\]
Pronto.
