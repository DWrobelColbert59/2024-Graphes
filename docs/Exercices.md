# Exercices

## Les exercices de base

!!! question "Exercice 1"

    On considère le graphe $G = (V, E)$ avec :

    \[
        V = \lbrace A, B, C, D, E\rbrace \quad \textrm{et} \quad E = \left\lbrace \rule[0.5cm]{0cm}{0pt} \lbrace A, B \rbrace, \lbrace A, C\rbrace, \lbrace A, E\rbrace, \lbrace B, D \rbrace, \lbrace C, D \rbrace\right\rbrace
    \]

    1. Quel est le degré du sommet $A$ ?
    2. Existe-il une chaîne entre $A$ et $D$ ?
    3. Représenter ce graphe.

??? tip "Indications"

    1. Il suffit de compter les arêtes contenant $A$.
    2. Il suffit de suivre les arêtes en partant de $A$ et voir si l'on arrive sur $D$.

??? bug "Correction"

    1. On compte exactement trois arêtes contenant $A$. D'où $\delta(A) = 3$.

    2. Il existe plusieurs chaînes possibles :

        \[
            \lbrace A, B \rbrace - \lbrace B, D \rbrace \quad \textrm{ou} \quad \lbrace A, C \rbrace - \lbrace C, D \rbrace  
        \]

    3. Une possibilité est : 

        <center>
            <img src="../images/exo1.png" alt="image" width="200" height="auto">
        </center>

!!! question "Exercice 2"

    On considère le graphe orienté $G = (V, E)$ avec :

    \[
        V = \lbrace A, B, C, D, E, F\rbrace \quad \textrm{et} \quad E = \left\lbrace \rule[0.5cm]{0cm}{0pt} (A, D), (A, E), (B, A), (B, C), (C, F), (D, C), (F, B)\right\rbrace
    \]

    1. Déterminer les valeurs de $\delta^-(C)$ et $\delta^+(C)$.
    2. Combien y-a-t il de cycles partant du sommet $C$ ?
    3. Donner une représentation de ce graphe.

??? tip "Indications"

    1. $\delta^-(C)$ correspond au nombre d'arcs sortants du sommet $C$. On compte alors les arcs ayant $C$ pour cible.
    2. Il suffit de suivre les chemins possibles avec les arcs proposés.

??? bug "Correction"

    1. On a $\delta^-(C) = 2$ car il y a deux arcs avec $C$ comme cible et $\delta^+(C) = 1$ car un seul arc possède $C$ comme origine.
    2. Il y a deux cycles depuis le sommet $C$ donnés par les chemins :

        \[
            (C, F) - (F, B) - (B, C) \quad \textrm{et} \quad (C, F) - (F, B) - (B, A) - (A, D) - (D, C)
        \] 

    3. Une possibilité est : 

        <center>
            <img src="../images/exo2.png" alt="image" width="450" height="auto">
        </center>

## Avec une liste d'adjacence

!!! question "Exercice 3"

    On considère le graphe dont la liste d'adjacence est donnée par :

    \[
        \begin{array}{ccl}
            \begin{array}{|c|}\hline A\\\hline\end{array} & \longrightarrow & \begin{array}{|c|}\hline B \\\hline\end{array}\\
            \begin{array}{|c|}\hline B\\\hline\end{array} & \longrightarrow & \begin{array}{|c|c|c|}\hline A & D & G \\\hline\end{array}\\
            \begin{array}{|c|}\hline C\\\hline\end{array} & \longrightarrow & \begin{array}{|c|c|}\hline D & E \\\hline\end{array}\\
            \begin{array}{|c|}\hline D\\\hline\end{array} & \longrightarrow & \begin{array}{|c|c|c|c|}\hline B & C & E & G\\\hline\end{array}\\
            \begin{array}{|c|}\hline E\\\hline\end{array} & \longrightarrow & \begin{array}{|c|c|}\hline C & D \\\hline\end{array}\\
            \begin{array}{|c|}\hline F\\\hline\end{array} & \longrightarrow & \begin{array}{|c|}\hline G\\\hline\end{array}\\
            \begin{array}{|c|}\hline G\\\hline\end{array} & \longrightarrow & \begin{array}{|c|c|c|}\hline B & D & F\\\hline\end{array}\\
        \end{array}
    \]

    1. Ce graphe est-il orienté ou simple ?
    2. Donner le degré du sommet $D$.
    3. Proposer un dictionnaire écrit en python implantant ce graphe.

??? tip "Indications"

    1. Il suffit de vérifier si chaque arête $(u, v)$ possède son symétrique $(v, u)$ dans la liste d'adjacence.

??? bug "Correction"

    1. Toutes les arêtes possèdent un symétrique dans la liste donc le graphe est simple.
    2. Le sommet de $D$ est $\delta(D) = 4$.
    3. On propose le dictionnaire :

        ``` python title="Proposition de correction" linenums="1"
        G = {   'A' : ['B'],
                'B' : ['A', 'D', 'G'],
                'C' : ['D', 'E'],
                'D' : ['B', 'C', 'E', 'G'],
                'E' : ['C', 'D'],
                'F' : ['G'],
                'G' : ['B', 'D', 'F']}
        ```

!!! question "Exercice 4"

    1. Écrire une fonction `degre(G : dict, s : str) -> int` qui renvoie le degré d'un sommet $s$.
    2. Compléter la fonction `degre_max(G : dict) -> str` qui renvoie le sommet de plus grand degré dans un graphe $G$ :

        ``` python title="Plus haut degré" linenums="1"
        from math import inf

        def degre_max(G : dict) -> str:
            res  = None
            maxi = -inf

            for el in G:
                if ... > ... :
                    res  = ...
                    maxi = ...

            return res
        ```

??? tip "Indications"

    1. Le degré correspond au nombre de voisins.
    2. Lorsqu'on trouve un sommet avec un degré plus grand, on le garde en mémoire.

??? bug "Correction"

    1. Le degré correspond à la longueur de la liste associée :

        ``` python title="Plus haut degré" linenums="1"
        def degre_max(G : dict, s : str) -> int:
            return len(G[s])
        ```

    2. On propose le code :

        ``` python title="Plus haut degré" linenums="1"
        from math import inf

        def degre_max(G : dict) -> str:
            res  = None
            maxi = -inf

            for el in G:
                if degre(G, el) > maxi :
                    res  = el
                    maxi = degre(G, el)

            return res
        ```