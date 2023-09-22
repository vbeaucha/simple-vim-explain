# VIM un paradigme qui s'ouvre a vous

## La saisie de texte de nos jours

Aujourd'hui la norme en terme de saisie de texte est d'utiliser un outil graphique ( Sublime Text, gedit, word ).

On tape sur une touche, du texte s'écrit, le backspace efface un carectére et on se déplace soit avec les fléches du clavier, soit un clique souris


Jusque là je ne vous apprends rien de bien nouveau

## C'est bien beau mais pourquoi vim?

Vim change complétement de paradigme et est déconcertant pour les novices.


Pourquoi apprendre une nouvelle manière de saisie de texte alors ?

Et bien, c'est tout simple: Vous n'aurez peut-être pas toujours accés à un outils graphique.

Si vous travaillez sur des serveurs, vous allez vous retrouver dans le monde bien sombre du terminal et de la ligne de commande. Autant avoir quelques armes en main le jour ou celà se produit!


Dans Vim vous avez 2 modes ( 3 en réalité mais on y reviendra )

 - EDIT [ESC] : je manipule du texte existant
 - INSERT [i] : je saisie du texte ( rien de nouveau sous le soleil )

C'est bien en ça que Vim est super fort: son mode edition!

## Le kit de survie du mode edition 

### Ce déplacer

Il serait trop facile d'utiliser les fleches pour se déplacer! à la place on utilise: 

```
- ↑ k : haut
- ↓ j : Bas
- ← h : Gauche
- → l : Droite
- → e : Fin de mot
- → E : Prochain espace / Fin de ligne
- ← b : Debut de mot
- ← B : Espace précédent / Début de ligne

- :[NUM] : aller à la ligne [NUM]
```

### Modifier un élément

Il exite deux grande commande pour modifier un texte existant 

```
- d : delete -> On reste en mode edition
- c : change -> On passe en mode insertion
```

C'est bien beau d'avoir ces commandes, mais comment les utiliser ? Avec un objet ou une circonstance!


Les circonstances:
```
 - i : inside
 - t : till
```
Les Objets: 
```
- w : Word
- p : paragraph
- [KEY] : caractère arbitraire
```

Quelques exemples exemples : 
```
 - di{ : va supprimer tout se qui se trouve entre les prochains {}
 - cw: modifier le mot courant
 - d[KEY1][KEY2] : supprimer les caractère de la KEY1 à la KEY2
```

#### En pratique

Imaginons que vous vouliez modifier ce code

```
function main(){
	// le main affiche hello world
	console.log("hello world")
}
```

On se place ici : 
```
function main(){
	// le main affiche hello world
->>	console.log("hello world")
}
```

un petit : di{ ou di} et magie: 

```
function main(){
}
```

## Je veux aller plus vite! 


Vous etes encore là? Dans ce cas, je vous donne une liste de commande qui vous permettrons de switcher du mode edition au insert et d'accelérer votre travail avec vim

```
- o : insérer une ligne sous le curseur
- G : fin du fichier
- $ : fin de la ligne
- { ou } : début ou fin de paragraphe (bloc de texte sans saut de ligne)
- CTRL + (u/d) : faire défiler d’une demie hauteur d’écran (up, down)  
```

J'ai fait une erreur! -> pas de soucis 

```
- u : undo (équivalent CTRL+Z)
- CTRL + r : redo
```

J'en ai marre je supprime tout!

```
- cc/dd : supprimer une ligne entière (avec ou sans passage en mode INSERT)
- d[number]d: supprimer [number] lignes
```

Faire un copier/coller

```
- y : copier ( même usage que les commandes c/d )
- p : coller ( même usage que les commandes c/d ) 
```

## Je veux sortie de cet enfer!

Sur le net, on peut s'amuser a trouver un masse incroyable de methode pour sortir de vim

Par exemple: débrancher votre ordinateur -> Efficace mais peu pratique


Je vous offre la bonne méthode!

```
- :w : write ( sauvegarder quoi)
- :q : quit (quitter -> enfin!)
- :wq : sauvegarder et quitter
- :q! : quitter en ignorant toute modification 
```

## Le 3eme mode de vim 


Comme j'ai pu l'enoncé plus haut, il existe un 3eme mode d'utilisation de Vim: Le mode Visuel [v] qui permet de faire de faire de la selection du texte parcouru

Comme pour le mode editon, les commande *y* et *p* permet de copier/ coller la selection

## Rechercher dans le mode edit

Vous pouvez faire des recherches dans un texte grace a plusieurs commande: 

```
- f[key] : aller à la 1er occurrence [key]
- ; : occurence suivante
- , : occurence precédente

- /[foo] : rechercher un pattern
- n : pattern suivant
- N : pattern precédent
```

## Personnalisé votre vim

Vim permet l'intégration de différent module grace à son fichier .vimrc


Je vous redirige vers des articles ou plugins bien utile:

- Fenêtres splittées - https://vim.works/2019/04/10/split-window-aesthetics/

- Tabs - https://vim.works/2019/06/24/tabbed-editing-in-vim/

- distraction-free - https://www.hamvocke.com/blog/distraction-free-writing/




















