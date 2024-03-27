# Les graphes

## Généralités

De manière générale, un graphe permet de représenter les connexions d’un ensemble en exprimant les relations
entre ses éléments : réseau de communication, réseau routier, circuit électronique, ... , mais aussi relations
sociales ou interactions entre espèces animales.

!!! note "Les ponts de Königsberg"

   
    Le problème des sept ponts de Königsberg cherche à déterminer s'il existe un chemin permettant de revenir à son point de départ en empruntant une seule fois chaque pont de la ville. Leonhard Euler démontre en 1735 qu'un tel chemin n'existe pas.
    
    <center>
        <img src="./images/ponts.png" alt="image" width="200" height="auto">
    </center>

La théorie des graphes est avant tout une branche à part entière et déjà ancienne des mathématiques. 
Néanmoins, l’importance accrue que revêt l’aspect algorithmique dans ses applications pratiques en fait aussi un domaine incontournable de l’informatique. 
Pour schématiser, les mathématiciens s’intéressent avant tout aux propriétés globales des graphes là où les
informaticiens vont plutôt chercher à concevoir des algorithmes efficaces pour résoudre un problème faisant intervenir un graphe.

### Présentation

!!! info "Définition"

    En mathématiques, un graphe est un couple $G = (V, E)$ avec :

    * $V$ l'ensemble des sommets du graphe ;
        
    * $E$ l'ensemble des arêtes, chacune étant associée à un couple $\lbrace u, v \rbrace$ avec $u, v \in E$.

    Le nombre de sommets dans un graphe correspond à son **ordre**.

    ??? question "Pourquoi des accolades pour une arête ?"

        Pour décrire l'arête entre les sommets $u$ et $v$, on utilise la notation $\lbrace u, v\rbrace$ pour
        mettre en avant le fait que l'arête ne soit pas orientée.

!!! tip "Vocabulaire"

    S'il existe une arête entre deux sommets $u$ et $v$, on dit que ces sommets sont **adjacents**.

!!! example "Exemple de graphe"

    Mathématiquement, le graphe suivant :

    <center>
        <img src="./images/ex1.png" alt="image" width="250" height="auto">
    </center>

    s'écrit $G = (V, E)$ avec :

    \[
        V = \lbrace A, B, C, D, E, F, G\rbrace \quad \textrm{et} \quad E = \left\lbrace \rule[0.5cm]{0cm}{0pt} \lbrace A, B \rbrace, \lbrace A, C\rbrace, \lbrace A, D\rbrace, \lbrace B, D \rbrace, \lbrace B, E\rbrace, \lbrace B, G\rbrace, \lbrace C, E\rbrace, \lbrace C,F \rbrace \right\rbrace
    \]

!!! info "Degré d'un sommet"

    Soit $G = (V, E)$ un graphe et $v \in V$ un sommet.  
    On note $\delta(v)$ le nombre de voisins de $v$. Ce nombre est aussi appelé le **degré** de $v$.

!!! example "Exemple"

    Dans le graphe précédent, on a $\delta(B) = 4$.


### Vocabulaire

!!! info "Définition"

    On dit qu'un graphe est **orienté** lorsque les arêtes possèdent un sens.  
    L'arête $\lbrace u, v \rbrace$ est alors notée $(u, v)$ et est appelée **un arc**.

    Pour un arc $(u, v)$ donné :

    * le sommet $u$ est appelé **l'origine** ;
    * le sommet $v$ est appelé **la cible**.

        ??? warning "Attention !"

            Attention au changement de notation et de nom !  
            L'arête $\lbrace u, v\rbrace$ laisse place à l'arc $(u, v)$.

!!! example "Exemple de graphe orienté"

    Mathématiquement, le graphe orienté suivant :

    <center>
        <img src="./images/ex2.png" alt="image" width="250" height="auto">
    </center>

    s'écrit $G = (V, E)$ avec :

    \[
        V = \lbrace A, B, C, D, E, F, G\rbrace \quad \textrm{et} \quad E = \left\lbrace \rule[0.5cm]{0cm}{0pt} (A, C), (A, F), (B, A), (B, G), (C, D), (D, B), (D, E)\right\rbrace
    \]

!!! info "Degré entrant et sortant"

    Dans un graphe orienté, on distingue la notion de degré entrant noté $\delta^-$ de celle de degré sortant noté $\delta^+$.

!!! example "Exemple"

    Dans le graphe précédent, on a $\delta^-(D) = 1$ et $\delta^+(D) = 3$.

## Implantation

### Avec des dictionnaires

### Avec une matrice

## Parcours de graphe

### Parcours en profondeur

### Parcours en largeur d'abordkd