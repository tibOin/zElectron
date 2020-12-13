# Portable LightCommands
## Hack d'une petite enceinte Bluetooth

### Introduction

Au boulot il y a, à l'accueil, une boite de collecte pour piles usagées. Je jette souvent un coup d'oeil parce qu'il y a parfois des trésors !
Et là, coup de chance : une petit enceinte Bluetooh. (Cadeau du CSE de l'année dernière...).
Ma copine va gueuler, encore un bordel ramené à la maison... Mais tant pis, l'occas' est trop intéressante !

Bon, reste à voir si elle fonctionne. Si non, trouver pourquoi, et enfin... Lui trouver une utilité...

### Phase 1 : Tests

Allez, essayons. J'actionne l'interrupteur. Et la lumière fut ! Une petite LED multicolore s'allume et clignote. Déjà la batterie fourni un peu de jus.
Me munissant de mon smartphone, j'essaie de détecter l'enceinte en Bluetooth. Rien... Ah Fuck! 
Et après quelques minutes allumée, un horrible sifflement se fait entendre. Mon dieu, éteignons ça !

Après cette petite expérience, je résume les observations :
  - Le système général semble fonctionner, la LED s'allume, il y a du jus.
  - On a une horrible sortie sonore. Le haut-parleur fonctionne. 
  - Problème d'amplification ? A priori non, puisque rien n'est lu. Mais on ne sait pas encore.
  - Pas de Bluetooth. Pourquoi ? -> Le truc a été récupéré dans une "poubelle". Ne marche plus ?

Bon, ne sachant pas depuis combien de temps ça n'avait pas été chargé je trouve un cable adequat et une prise `230V~/5Vcc` et je branche le bazar.
Allez, a tout hasard je rallume et je lance la détection Bluetooth. IL EST LÀ !
Je balance un p'tit son. Qualité de merde, mais ça fonctionne !

Ok. Cette enceinte Bluetooth est parfaitement fonctionnelle. Et dire qu'elle allait partir à la poubelle...

### Phase 2 : Trouver une utilité

On peut faire plein de trucs avec un enceinte Bluetooth. C'est sûr. Mais quoi ?...
J'en sais rien. Je la laisse de côté un moment. Et puis je tombe sur cette article sur un possible Hack des différents dispositifs Alexa, Ok Google, Siri, etc.
par laser. Et putain que c'est simple ! Il suffit de balancer un signal audio dans un laser et de pointer le tout sur le micro du bordel. Et boum ! On peut passer
des commandes vocales en silence. Et depuis très loin. (Un laser c'est puissant !). En plus, un simple pointeur laser suffit. `5mW` c'est suffisant pour la plupart des
appareils.
Eh ! Mais j'ai un petit module laser Elegoo dans ma boite ! Et j'ai une enceinte Bluetooth ! J'ai mon ampli audio. Mon pont avec l'ordi et ma sortie lumineuse !
Tout est réuni pour bidouiller un p'tit dispositif de test. Une PoC (Proof of Concept).

### Phase 3 : Hack de l'enceinte

Après une étude visuelle approfondie du circuit du machin. Et ayant pris connaissance des 3 bornes de mon module laser (`-`, `+` et `Signal`).
Je trouve le moyen de connecter mon laser pour qu'il remplisse la tâche que je veux lui assigner. 

<img src="https://raw.githubusercontent.com/tibOin/zElectron/master/docs/_site/assets/images/lightcommands/back.png" width:200 alt="Back">Erreur...</img>

Plus qu'à mettre en pratique. J'ai pris 3 jumpers femelle-femelle que j'ai coupé pour avoir d'un coté le socket et de l'autre le fil à nu. 
Et j'ai soudé les fils sur la carte. J'ai viré la sortie jack pour y mettre le laser à la place. 
Coup de pot, le diamètre du laser est très proche de celui du port jack.
Bon, ne critiquez pas les soudures, j'avais plus d'étain j'ai réutilisé celui déjà sur la carte avec des résultats... Désastreux. 

Il restait un détail pour le moins gênant. Cette LED qui m'indiquait que l'enceinte fonctionne, maintenant parasite ma sortie laser. Qu'à cela ne tienne,
je la couvre de gaine themorétractable noire. Et le tour est joué.

![Image 2](image2)
![Image 3](image3)
![Image 4](image4)

Et le resultat est là. En plus c'est vachement discret. Si ce n'est qu'il n'y a plus aucun son.

### Conclusion




