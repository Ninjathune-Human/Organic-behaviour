![Laboratoire de fusion](banniere.png)

# Laboratoire de fusion

Des cellules vivantes, dessinées à main levée, reliées par des liens de filiation routés en orthogonal. Chaque cellule est une membrane souple qui ondule, réagit aux gestes et transmet ses propriétés à sa descendance.

Page autonome, sans installation : ouvrir `index.html` dans un navigateur, ou la version en ligne sur GitHub Pages. Fonctionne à la souris, au doigt et au stylet, sur ordinateur, iPad et iPhone.

## Gestes en bref

| Geste | Effet |
| --- | --- |
| Dessiner une forme sur le fond | Crée une cellule de cette forme |
| Double appui sur une cellule | Fait naître une fille de la même forme |
| Tirer depuis le bord d'une cellule | Relie une mère à sa fille |
| Glisser l'intérieur | Déplace la cellule |
| Appui long | Met la cellule en mode tremblement |
| Glisser une cellule qui tremble | Déplace toute sa lignée |
| Appui sur une autre cellule (mode tremblement) | Lui donne la taille de la cellule qui tremble |
| Tirer les marques du coin (mode tremblement) | Fait tourner la cellule |
| Appui simple sur une mère | Allume sa lignée |
| Appui sur l'encoche d'une mère | Replie ou déplie ses filles |
| Trait en travers d'un lien | Coupe le lien |
| Croix ou rature sur une cellule | Supprime la cellule |

## Créer une cellule

### En dessinant

Tracer une forme fermée sur le fond, d'un seul geste. Le tracé est reconnu, puis remplacé par une cellule de la forme correspondante. L'octogone n'en fait pas partie : trop proche du rond, il le faisait mal reconnaître ; un octogone dessiné devient un rond ou un hexagone.

Formes reconnues :

- rond et ovale ;
- rectangle, qui devient un carré s'il en est proche ;
- triangle ;
- losange, pentagone, hexagone ;
- étoile ;
- cœur, pointe en bas ;
- nuage, avec autant de bosses que dessinées ;
- flèche.

Comme dans un logiciel de dessin, la forme est redressée en **forme standard** :

- un triangle proche de l'équilatéral, du rectangle ou de l'isocèle le devient ;
- les polygones et l'étoile sont réguliers et homothétiques, avec des branches de même longueur pour l'étoile ;
- le cœur prend des proportions standard, et les garde quand il change de taille ;
- une forme presque droite est remise d'aplomb.

La **flèche** se dessine de trois façons :

- en contour, comme une forme fermée ;
- d'un seul geste : la hampe, puis la pointe en V ;
- en deux traits : la hampe, puis la pointe posée sur l'un de ses bouts, dans les 3 secondes. Le trait droit reste affiché en attendant sa pointe, puis s'efface s'il n'en reçoit pas.

### Par bourgeonnement

Un **double appui** sur une cellule, au doigt, au stylet ou à la souris, fait naître une fille. Le second appui doit suivre le premier de moins d'une demi-seconde ; il peut tomber un peu à côté, sur le bord ou juste hors de la membrane, et la paume posée sur l'écran ne le bloque pas. Elle sort de la membrane de sa mère, grandit, dépasse légèrement sa place puis s'y pose. Le lien qui les unit s'allume au passage.

- La fille reprend la forme de sa mère : même type, même taille, même orientation et même teinte.
- La première fille se place à côté de la mère, à droite, ou à gauche s'il n'y a pas la place.
- Les suivantes se rangent sous la sœur la plus basse, en colonne.
- Une mère dont la famille est repliée la déplie d'abord.

## Relier une mère et sa fille

Poser le doigt sur le **bord** d'une cellule, là où la membrane s'éclaire au survol, puis tirer : un connecteur souple sort de la membrane. Le lâcher sur une autre cellule crée le lien. Lâché dans le vide, il revient dans sa cellule d'origine.

- La cellule d'où part le lien devient la **mère**, celle où il arrive la **fille**.
- Une cellule n'a qu'une mère, et une mère ne peut pas devenir la fille de sa propre descendance.
- Au moment du lien, les deux cellules frissonnent ensemble et une lueur passe de la mère à la fille.
- La fille **hérite de la teinte** de sa mère et la transmet, génération après génération, à sa propre descendance.
- Le lien est plus épais côté mère : on lit le sens de la filiation.

Les liens sont routés en orthogonal autour des cellules, sans les traverser, et se recalculent quand une cellule bouge, tourne ou change de taille.

**Allumer une lignée.** Un appui simple sur une mère allume toutes ses filles, puis leurs filles : une impulsion lumineuse descend le long des liens. Un nouvel appui l'éteint.

**Couper un lien.** Tracer un trait qui le croise : le lien se rompt au point de coupe et chaque moitié revient comme un élastique dans sa cellule. La fille, devenue orpheline, retrouve sa teinte d'origine et la transmet à sa descendance.

## Déplacer

**Une cellule seule.** Glisser son intérieur : elle se soulève, porte une ombre, puis frissonne quand on la pose. Si un lien est presque droit, l'aimant le redresse : il s'enclenche à 8 px de l'alignement et se libère au-delà de 16 px.

**Une lignée entière.** Quand une cellule tremble (voir le mode tremblement), la glisser emmène toutes ses filles visibles et leurs propres filles, en gardant leur disposition. On peut glisser dans le même geste que l'appui long ou après avoir levé le doigt. Un léger glissement pendant l'appui long ne le fait pas échouer.

## Le mode tremblement

Un **appui long** (environ une demi-seconde) sur une cellule la fait trembler. Un appui sur le fond termine ce mode.

**Transmettre une taille.** Pendant que la cellule tremble, un appui sur une autre cellule lui donne son encombrement. Elle s'y glisse en ondulant, en gardant sa forme : un polygone ou une étoile change de taille sans se déformer.

**Tourner.** Deux petites marques courbes apparaissent au coin de la cellule qui tremble. Les tirer fait tourner la cellule autour de son centre :

- les marques tournent avec la forme, si bien que le doigt garde la prise ;
- à moins de 5° de l'horizontale ou de la verticale, la forme se cale d'un mouvement amorti, puis s'en libère au-delà de 10° ;
- pour une flèche, c'est sa direction qui se cale ;
- un rond n'a pas de marques, puisqu'il reste le même en tournant.

## Replier et déplier une famille

Une mère porte une petite **encoche** sur sa membrane, tournée vers ses filles.

- **Replier :** un appui sur l'encoche fait rentrer les filles dans la mère, génération après génération, en commençant par les plus éloignées. La lumière remonte le long des liens, puis un **bourgeon** se forme sur la membrane.
- **Déplier :** un appui sur le bourgeon fait ressortir les filles, qui regagnent leur place avec un léger dépassement.
- **Déplacer une famille repliée :** il suffit de déplacer la mère. Au dépli, les filles ressortent autour de sa nouvelle position.
- **Ajouter une fille** à une mère repliée, par un lien ou un double appui, rouvre la famille.

## Supprimer

Une **croix** sur une cellule (deux traits droits qui se coupent, le second commencé dans les 3 secondes) ou une **rature** en zigzag la supprime. La cellule se contracte et s'efface, ses liens se rétractent vers les cellules restantes, et ses filles repliées ressortent avant sa disparition.

## Réglages

| Réglage | Rôle |
| --- | --- |
| Plein écran | Affiche le laboratoire sur tout l'écran (sur iPhone, passer par l'écran d'accueil, voir plus bas) |
| Gestes | Ouvre ou referme l'aide |
| Ressort | Les liens ondulent comme des ressorts quand leur tracé change |
| Voies unifiées | Les liens parallèles se tassent en faisceau au lieu de s'étaler dans l'espace libre |
| Hystérésis | Un lien ne change de côté de départ que si le nouveau tracé est nettement meilleur, ce qui évite les sauts pendant un déplacement |
| Lignes à 45° | Coupe les angles des liens par des pans à 45° ; le curseur règle leur longueur maximale, adaptée à chaque angle selon la place disponible |

## Sur iPad et iPhone

- **Stylet :** à son approche, le bord de la cellule visée s'éclaire. La paume posée sur l'écran pendant l'écriture est ignorée.
- **Griffonnage :** cette fonction d'iPadOS, qui transforme l'écriture manuscrite en texte, avale parfois des contacts du stylet, même hors des champs de texte. La page la neutralise sur la scène, et un appui dont seul le lever est arrivé compte quand même. S'il reste des ratés, désactiver Réglages › Apple Pencil › Griffonnage.
- **Plein écran :** ouvrir l'adresse dans Safari, puis Partager › Sur l'écran d'accueil. Le laboratoire s'ouvre alors comme une application, sans barre de navigation.

## Sous le capot

- Un seul fichier HTML, sans dépendance externe ni serveur.
- Rendu en Canvas 2D ; les membranes sont des chaînes de points reliés par des ressorts, simulées à 240 pas par seconde. L'animation s'arrête dès que la scène est au repos.
- Routage orthogonal par [libavoid-js](https://github.com/Aksem/libavoid-js), portage WebAssembly de la bibliothèque libavoid du projet Adaptagrams, sous licence LGPL-2.1-or-later. Le module est embarqué dans la page.
- Reconnaissance des formes : le tracé est comparé à chaque forme candidate ; pour les nuages et les flèches, les creux du tracé sous son enveloppe convexe départagent les formes proches ; le cœur se reconnaît au creux du milieu de son bord supérieur.
