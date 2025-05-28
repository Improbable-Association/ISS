# Fiche memo mesures et calage sono

## Ressources
### HornPlans
- https://hornplans.1fr1.net/t10143p450-nouveaux-t-racks
- https://hornplans.1fr1.net/t3694p325-tutoriels-photo-et-video-pour-room-eq-wizard-rew
- https://hornplans.1fr1.net/t3694p150-tutoriels-photo-et-video-pour-room-eq-wizard-rew
- http://hornplans.free.fr/calage_sono.html
- http://hornplans.free.fr/calage_delay.html
- ...

### Vidéos explication de la phase
- https://www.youtube.com/watch?v=_KZ1_Je9fA8&ab_channel=Taylor%26FrancisBooks
- https://www.youtube.com/watch?v=IcYBP51eCMk&ab_channel=Taylor%26FrancisBooks

### Vidéos mise en phase et délai
- https://www.youtube.com/watch?v=XJSaivLEGsk&ab_channel=RCF
- https://www.youtube.com/watch?v=9l1oI58LRq0&ab_channel=RCF
- https://www.youtube.com/watch?v=j6Z_sIDrs8A&ab_channel=KeithMORRIS

### Vidéos choix des filtres si les enceintes sont déjà en place
- https://www.youtube.com/watch?v=XvgV9MclDBg&ab_channel=NathanLively

### Vidéos réponse impusionnelle (IR)
- https://www.youtube.com/watch?v=1jPtvZg_6RU&ab_channel=ScottEvans
- https://www.youtube.com/watch?v=67beH_UMHG8&ab_channel=NathanLively (crossover accoustique)

## Calibrage des éléments de mesures

### Calibrage de la carte son
Calibration dans REW :

1. Onglet "Preferences"
2. Bouton "Calibrate"
3. Suivre la procédure
4. Bouton "Make Cal" pour enregistrer la calibration

**Paramètres spéciaux Foscurite Scarlett 4i4**

Pour la Foscurite Scarlett 4i4 il faut mute la piste "Loopback" dans le logiciel Foscurite Control

### Calibrage du micro
Pour calibrer son micro il faut soit passer par un organisme qui peut le calibrer soit récupérer un fichier de calibration.
Les fichiers de calibration sont génériques il vaut mieux donc ne pas calibrer du tout le micro pour éviter de mal calibrer le micro.

## Paramètres REW
**Generator**

Pink PN = Pink Periodic Noise

**RTA**

Pour mesurer en RTA on va dans l'onglet "RTA".
On peut rentrer les paramètres suivants :
- Mode : RTA 1/3 oct
- FFT length : 32768
- Average : 16 (ou 32 si l’affichage n’est pas assez stable)
- Window : Rectangular
- Max overlap : 75%
- Update Interval : 1

**ATTENTION !** Toujours mettre en "RTA x/y octave" et pas en "Spectrum"

**NOTE :** Le "Spectrum" tient pas compte de la différence d'énergie entre le grave et l'aigu, c'est pour ça que l'on a une courbe décroissante.

**Sweep**

Pour un Sweep on utilise l'outil "Measure"

## 1. Mesure de chaque transducteur
### 1.1. Mesure des voies indépendamment
#### Prérequis
Pour la mesure il faut sur l'EQ à bandes ou sur le processeur :
- Aucun filtre
- Aucun EQ

**NOTE :** Sur un T.racks DS 2/4, on met les filtres en "FLAT THRU"

**BUT :** Mettre aucun filtre ou EQ permet de voir à quelles fréquences on peut espérer couper, et, le cas échéant, de voir les problèmes possibles, de savoir s'il vaut mieux equaliser au niveau du raccord, etc...

#### Mesure
1. Démarrage du Pink PN (ou Sweep)
2. Ouverture de la fenêtre RTA
3. Ajustement des niveaux en entrée (pour éviter de saturer, pour avoir une courbe lisible, etc...)
4. Lancement de la mesure

**NOTE :** Pour éviter d'être dans les réflexions qui perturbent la mesure on peut rajouter un délai avant le déclenchement réel de la mesure quand on fait un Sweep.

**NOTE :** S'il y a beaucoup de bruit il vaut mieux utiliser un Sweep car il a un meilleur rapport signal/bruit, il est possible de paramétrer la plage de fréquences mesurée pour gagner du temps.
L'avantage du bruit rose, est la simplicité et la rapidité.

#### **Placement du micro**
**Têtes proches des subs**

*Hauteur:*

On placera le micro dans l’axe situé au milieu des centres acoustiques des voies raccordées entre elles (l’axe du centre acoustique étant le milieu de la zone de radiation de la voie, autrement dit l’axe du centre du HP ou le centre de la sortie du pavillon).

**Synthèse :** Au milieu du mur

*Distance:*

Pour la distance du micro, choisir au minimum 3 fois l’écart entre les sources.

Exemple, si les centres acoustiques sont distants de 1 m, on placera le micro au minimum à 3 mètres de distance.

**NOTE :** Si le milieu des centres acoustiques est inférieur à la hauteur de l’oreille, rehausser légèrement le micro pour compenser la hauteur trop faible. Etant donné les longueurs d’ondes encore importantes au raccord entre sub et têtes, la hauteur du micro n'est pas trop critique.

**Têtes en hauteur sur un pont**

*Hauteur:*

On positionnera le micro à hauteur d’oreille.

*Distance:*

On positionnera le micro à un point moyen d’écoute, ni trop trop éloigné, ni trop prés des sources, mais à un point mi distant de la zone d’écoute, sachant que plus on se rapproche de la sonorisation, plus le sub sera proche de l’oreille (comparativement aux têtes), et inversement à grande distance.

**Mesure en salle**

Pour mesurer dans une salle, on passe un Pink PN (Pink Noise), et on déplace le micro à des endroits stratégiques et on corrige ensuite.

**Mesure de caissons de basses**

Toujours micro au sol pour des mesures de sub.
A 1 m de distance ou un peu moins si l'environnement n'est pas bon.

**Environnement**

En principe il faut un sol dur.
Pour la mesure d'un caisson de basse, vu les longueurs d'ondes, cela ne fait pas de grandes différences. Pour avoir un sol dur on peut utiliser une plaque de contre plaqué (ou autre bois) sur laquelle on peut poser le micro éventuellement le caisson.

### 1.2. Mesure de toutes les voies ensemble
La procédure de mesure est identique à la précédente

## 2. Correction des voies
## 2.1 But et principe
Le but ici est d’avoir la courbe la plus régulière avec le minimum d’égalisation. On élimine
seulement les résonances et trous les plus importants.

**ATTENTION !** Rappel plus les corrections sont importantes, plus on fait tourner la phase.

## 2.2. Type d'EQ
On distingue 2 grands types d’EQ principaux
- Les égaliseurs de type *Peaking* : Sur un égaliseur Peaking, il y a 3 paramètres par bande :
  - Le gain
  - La fréquence
  - Le facteur Q ou BW qui permet d’élargir ou rétrécir la bande de fréquence sur laquelle le gain agit.

**NOTE :** Un facteur Q de 0.5 donne une grande largeur de bande, un Q de 10, une bande étroite. A
contrario, avec un EQ gradué en BW (bandwidth), un BW de 3 correspond à une bande large, et 0.1
à une bande étroite.

- Les égaliseurs de type *Shelving* :
Le Shelving est un filtre en plateau qui s’utilise en bout de bande, dont le gain et la fréquence sont
réglables. Sur certains Shelving, on peut même régler la pente (6 ou 12dB/oct, ou voire pente
variable sur les processeurs haut de gamme)


**NOTE 2 :** Dans le cas d’une égalisation positive, plus la largeur de bande est étroite, plus la correction risque
de devenir désagréable à l’oreille (résonance).

On privilégiera donc des corrections négatives
lorsque cela est possible. (Égalisation positive (négative) augmentation (diminution) du gain)
Ne pas hésiter à traiter une résonance même si elle est un peu en dehors de la bande passante utile
du transducteur ou enceinte. Les résonances peuvent se faire entendre même au-delà de la
fréquence coupure.
Ne pas oublier de compenser les différences de niveau induites par les diverses corrections.

**RAPPEL :** Copier les corrections sur les voies identiques !

## 3. Filtrage
On filtre les HPs pour avoir le plus de niveau possible tout en protégeant les compressions.

**Type de filtres**

Il existe différents types de filtres les plus utilisés sont les suivants :

Si on applique un passe-bas à un HP et un passe-haut à un autre HP (à la même fréquence de
coupure) :

*Linktwitz Riley*

Rotation de phase de 360° pour un filtre 24dB/oct Linktwitz Riley

Rotation de phase de 720° pour un filtre 48dB/oct Linktwitz Riley

*Butterworth*

BW6 = 6 dB/oct Butterworth
Passe bas BW6 (90°) + Passe haut BW6 (90°) = 180° de rotation de phase entre les deux HPs

Passe bas BW12 (180°) + Passe haut BW12 (180°) = 360° donc en phase

Les BW sont plus utilisés pour des compressions et les passe haut des caissons de graves

Filtrage caissons de grave :
- Filtre passe haut (30 Hz à 50 Hz) but : éviter que les fréquences les plus graves ne génèrent une excursion de la membrane trop importante.
- Filtre type Butterworth but : ne pas atténuer trop tôt les fréquences près du point de coupure (coude de raccordement plus raide).

Si on a des transducteurs ayant tous deux leur courbe de réponse naturelle à -3dB à la fréquence de
raccordement souhaitée. Dans ce cas on peut programmer des filtres de type Butterworth, on
pourra récupérer les 3 𝑑𝐵 manquant sans utiliser d’égaliseur.

**NOTE :** Sur les MTH4654 de l'INSA on a un BW12 pour HPF

**RAPPEL :** Mesurer toutes les voies ensemble après filtrage.

## 4. Balance tonale et phase:
### 4.1. Prérequis
- Se mettre en RTA avec un affichage qui moyenne de manière importante lisser les accidents dûs aux réflexions en **1/3 d'octave** par exemple.
- Cocher dans le menu controls (petite roue d'engrenage en haut à droite) "Use bars on RTA" pour avoir une idée de la mesure dans laquelle la moyenne "applatit la courbe".

### 4.2. Ajustement des niveaux
On va ajuster les niveaux pour que les voies soient au même niveau, i.e. les caissons sont au même niveau que les satellites.

On peut ajuster les niveaux à partir de 2 méthodes :
- Amplificateur à fond et ajustement des gains des voies de sortie dans le processeur.
- Ajuster directement sur les amplificateur.

Il vaut mieux utiliser la première méthode pour éviter tout problème.

### 4.3 Phase et delays
On va choisir la phase et le delay des voies pour avoir un maximum de niveau au raccord entre voies.

**Phase**

Pour la phase on choisi d'inverser ou non la phase pour chaque voie pour avoir le niveau maximal au niveau du raccord des voies (et aussi le réglage qui garde possède le plus de grave).

**Delay**

Pour le delay on choisi plusieurs valeurs et on cherche le niveau maximal au niveau du raccord des voies

Pour choisir le délai on peut regarder la phase et essayer de rapprocher le plus possible le "tracé" des phases au niveau et autour du raccord des voies.

**NOTE :** Plus la pente de la phase est importante plus le nombre de rotation de la phase (et donc le retard / délai) est important.

**NOTE 2 :**

Si le tracé de la phase d'une voie monte (de la gauche vers la droite) on a un délai négatif

Si le tracé de la phase d'une voie descend (de la gauche vers la droite) on a un délai positif

**Réponse impusionnelle (IR)**

Pour obtenir la meilleure réponse impusionnelle globale possible (i.e. un seul pic) il est nécessaire de choisir judicieusement les délai.

Dans REW :
1. Onglet "Impulse" des mesures
2. Axe Y du graphique en %FS
3. On regarde le délai de chaque voie
4. On essaie d'avoir le même délai dans les IR de chaque voie (en réalisant de nouveau des mesures)
5. On essaie d'avoir la même forme de pic (positif / négatif)

**NOTE :**
Pour le graphique des IR on peut interpréter le graphique ainsi :

Si pic positif -> polarité positive

Si pic négaitif -> polarité négative

Pour résumer : http://hifi-stereo.fr/calage-de-la-reponse-impulsionnelle/



https://www.hometheatershack.com/threads/measure-time-delay-with-rew.171530/post-1596666
# COMMENT ON CHOISI LA FREQUENCE DE COUPURE ENTRE VOIES
http://hornplans.free.fr/phase2.html
Comment trouver la valeur de l’excès de phase?

Si le logiciel permet d’afficher le group delai et de corriger le delai manuellement, il suffit de programmer un delai qui fera correspondre le niveau le plus faible du group delai du caisson avec le 0 du group delai sur la courbe. Si le logiciel est capable d’afficher la réponse impulsionnelle, on peut s’en servir pour calculer le delai entre le HP et micro. Par contre, on ne se servira pas de ce delay pour la programmation des delais sur le processeur, on ne se servira que des courbes de phase: Même si réponse impulsionnelle et phase sont liés, la phase peut changer tout au long des fréquences, la réponse impulsionnelle exprime une valeur globale et non à une fréquence précise.



https://hornplans.1fr1.net/t11488-mesures-votre-matos-vos-habitudes-on-en-discute




C'est pas qu'une histoire de fréquences de raccordement, mais aussi des enceintes utilisées dans chaque bande de fréquences, la disposition aussi. Le plus fréquemment, c'est la voie sub qui va servir de référence. Donc tes subs seront à un delay de zéro, donc tu cales tes kicks sur tes subs, puis tops sur kicks. Néanmoins si pour la voie kick tu utilises un caisson initialement destiné à faire de la basse, suivant la fréquence de coupure, il est possible que ce soit la voie kick à prendre en référence. Il suffit de tester en mesurant les phases et voir ce qui t'aide le mieux à ce que les phases se chevauchent tout autour de la fréquence de raccord acoustique (et non électrique).

Un petit truc pour aider : lorsque le chevauchement de la phase ne se fait pas pas sur une plage d'au moins une octave, on peut jouer sur une pente d'un des filtres.







Cardioid array : https://www.youtube.com/watch?v=t-Ikv_uoLt0&ab_channel=NathanLively


## 5. Shelving (rehaussement des graves)
**But et principe**
Ici on a une réponse plate, on va maintenant créer une "bosse" en entrée (avant tout filtrage ou EQs) pour réhausser les graves et avoir une écoute plus agréable.

La chaine du signal est ainsi :
```
Table de mixage -> Processeur -> Amplificateurs -> HPs
```

On ajoute le rehaussement des graves avant tout traitement du DSP.
```
Table de mixage -> (Entrée Processeur ou EQ à bandes) EQ / Rehaussement des graves -> (Sortie Processeur) Filtrage, EQ, Limiteur -> Amplificateurs -> HPs
```

**ATTENTION !** Si on ne peut pas augmenter le niveau des graves avec le DSP et que l'on a pas d'égaliseur à bandes, il faut on augementer le gain de la voie des grave directement et ensuite mettre en phase et choisir le bon délai.

**Type de Shelving**

Pour effectuer le rehaussement des graves il faut utiliser un Low Shelf.
Le High Shelf permet de descendre assez bas en fréquences, il peut être utilisé en correction négative à la même fréquence que le low shelf.

Le High Shelving en gain négatif produit exactement la même courbe de réponse/phase qu'un Low Shelf positif. La seule différence, c'est le gain interne qui diffère (davantage de gain interne avec le Low Shelf).

## 6. Ecoute de confirmation
Vérficiation par une écoute qu'il ne reste rien à corriger.


## (7.) Mise en place des limiteurs
Le limiteur permet la protection des HPs et / ou des amplificateurs.

On distingue 2 types de limiteurs :
- Le limiteur RMS : qui garde un niveau RMS du signal ("un signal moyen") acceptable pour les HPs. On a donc ici des pics de signal qui peuvent passer au-dessus de la moyenne sans être complètement supprimés.
- Le limiteur PEAK : qui agit comme un "mur" / "brick wall" et qui bloque totalement le signal dépassant une certaine valeur.

### Calculatrice pour le niveau de la limitation
Voir la calculatrice du site Horn Plans : http://hornplans.free.fr/limiteur.html

### Réglages de plusieurs DSP
#### **the t.racks DSP 206 et équivalents**

**ATTENTION !**
Il est recommandé d'utiliser la version 1.03 du firmware du DSP pour une plus grande protection. En effet la version 1.02 comportait des dysfonctionnements au niveau des différents limiteurs.

Les réglages proposés ici furent récupérés du post de moumou sur le forum HornPlans au lien suivant : https://hornplans.1fr1.net/t10143p375-nouveaux-t-racks#187124 (pour la version 1.03 du firmware)

La version 1.03 du DSP 206 comporte un limiteur RMS et PEAK ce qui permet une double protection.

*Limiteur RMS*

Les réglages du compresseur / onglet "Comp" (limiteur RMS) doivent être les suivants :

- Ratio : infini (valeur dénommée Limit sur l’interface)
- Knee : 0db (pour ne pas pré-limiter)
- Release : 1 seconde (1000 ms) (bon compromis sur ce processeur)
- Threshold : calculatrice de HornPlans en mode dBu
- Attack :
  - Voie sub : 300ms
  - Bas medium : 250ms
  - Compression : 150ms
  - Voie pour enceinte large bande 120-20000 Hz : 200ms
  - Voie pour enceinte large bande 40 20000 Hz : 200ms

*Limiteur PEAK*

Les réglages de l’onglet "Limit" (limiteur PEAK) doivent être les suivants :

- Threshold : calculatrice de HornPlans en mode dBu + 3 dB
- Attack : 1ms
- Release : 1 seconde (1000 ms) (bon compromis sur ce processeur)

**NOTE :**

Si on a un amplificateur bien surdimensionné on a aucun souci à se faire.

Si on a un amplificateur peu surdimensionné on doit baisser l'Attack jusqu’à apaisement du clip de l’ampli.

#### **the t.racks DS 2/4**

**ATTENTION !**
Le the t.racks DS 2/4 ne comporte pas de limiteur PEAK

*Limiteur RMS*

Les réglages du limiteur RMS "Limiter" doivent être les suivants :

- Decay : 1 seconde (1000 ms) (bon compromis sur ce processeur)
- Attack :
  - Voie sub : 300ms
  - Bas medium : 250ms
  - Compression : 150ms
  - Voie pour enceinte large bande 120-20000 Hz : 200ms
  - Voie pour enceinte large bande 40 20000 Hz : 200ms
- Level : calculatrice de HornPlans en mode T.racks DS 2/4

**NOTE :**

Si on a un amplificateur bien surdimensionné on a aucun souci à se faire.

Si on a un amplificateur peu surdimensionné on doit baisser l'Attack jusqu’à apaisement du clip de l’ampli.

