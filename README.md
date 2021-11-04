# Vorassic

## 1. Règles du jeu

### 1.1 Plateau de jeu

Le jeu se joue sur un plateau carré, de n x n cases. Chaque case contient un nombre entre 0 et 9.
On choisira la taille n de la grille - dans l’intervalle [5 ; 26] - au début du jeu. Chacune des colonnes est numérotée de 0 à n-1. Les cases contiennent des valeurs entre 0 et 9. Par défaut, ces valeurs sont fonction de la distance aux deux cases en coin haut gauche et bas droite, comme le montre l'exemple ci-dessous. Pour une taille de 5, la configuration de départ sera la suivante :

? | A | B | C | D | E |</br>
0 | J | 1 | 2 | 3 | 4 |</br>
1 | 1 | 2 | 3 | 4 | 3 |</br>
2 | 2 | 3 | 4 | 3 | 2 |</br>
3 | 3 | 4 | 3 | 2 | 1 |</br>
4 | 4 | 3 | 2 | 1 | R |</br>

Deux joueurs s'affrontent sur ce plateau, jaune et rouge. Au départ, jaune possède la case haut gauche tandis que rouge possède la case bas droite. C'est jaune qui commence. Chacun, à tour de rôle, doit jouer un coup. Il est interdit de passer son tour tant qu’il reste des coups à jouer. Lorsque plus aucun joueur ne peut jouer, la partie s'arrête.

### 1.2 Les coups - mode serpent

Un coup consiste à donner la case que l'on souhaite capturer. Attention ! Il y a une limitation aux coups jouables, on ne peut capturer une case que si :

1. elle est libre

2. elle est adjacente à la dernière case capturée

3. le mouvement se fait vers le haut, vers le bas, vers la droite ou vers la gauche. Les mouvements en diagonale sont interdits. Dans notre exemple, jaune peut jouer soit B0, soit A1, et il est obligé de choisir l'une de ces deux options. Supposons qu'il joue A1, la grille devient :

? | A | B | C | D | E |</br>
0 | j | 1 | 2 | 3 | 4 |</br>
1 | J | 2 | 3 | 4 | 3 |</br>
2 | 2 | 3 | 4 | 3 | 2 |</br>
3 | 3 | 4 | 3 | 2 | 1 |</br>
4 | 4 | 3 | 2 | 1 | R |</br>

et le score est maintenant de 1 à 0 en faveur de jaune. Au tour suivant, (après que rouge aura joué supposons, D4), jaune devra capturer soit la case B1, soit la case A2. S'il joue B1 la grille devient :

? | A | B | C | D | E |</br>
0 | j | 1 | 2 | 3 | 4 |</br>
1 | j | J | 3 | 4 | 3 |</br>
2 | 2 | 3 | 4 | 3 | 2 |</br>
3 | 3 | 4 | 3 | 2 | 1 |</br>
4 | 4 | 3 | 2 | R | r |</br>

Le score, à ce moment de la partie, est de 3 à 1 en faveur de jaune.

### 1.3 Les coups - mode pieuvre

Le principe est le même que pour le mode serpent, à une différence prêt : on peut aller dans une case dès qu’elle se trouve à côté d’une case déjà capturée (vs à la dernière case capturée pour le mode serpent). Donc, on ne peut capturer une case si:

1. elle est libre

2. elle est adjacente à une case déjà capturée.

3. le mouvement se fait vers le haut, vers le bas, vers la droite, vers la gauche ou en diagonale hautdroite, en diagonale haut-gauche, en diagonale bas- droite, en diagonale bas-gauche. Les mouvements en diagonale sont autorisés. Dans l'exemple ci dessous, jaune peut jouer en B0, A1, A2, A3, B3, C3, C2, C1, C0

? | A | B | C | D | E |</br>
0 | J | 1 | 2 | 3 | 4 |</br>
1 | 1 | J | 3 | 4 | 3 |</br>
2 | 2 | J | 4 | 3 | R |</br>
3 | 3 | 4 | 3 | 2 | R |</br>
4 | 4 | 3 | 2 | 1 | R |</br>

### 1.4 Fin et gain de la partie </br>

Le jeu s'arrête lorsque plus aucun joueur ne peut jouer. Ainsi, si rouge ne peut plus jouer mais que
jaune peut encore jouer, la partie continue. Le vainqueur est celui qui a amassé le plus de points à la
fin de la partie.

## 2. Spécification de votre programme

Le programme minimum doit:
a. demander la taille de la grille de jeu
b. générer et afficher la grille de départ : celle-ci sera remplie soit par défaut comme expliqué ciavant, soit au hasard avec un générateur de nombres aléatoires.
c. demander le mode de jeu (mode serpent OU mode pieuvre)
d. demander à tour de rôle à chaque joueur le coup qu'il veut jouer
e. gérer le déroulement et la fin de partie.
f. afficher, après chaque coup l’état de la grille en mode texte dans la console, ainsi que les
scores. Une représentation possible est celle indiquée dans ce document mais c’est loin d’être
la seule.
