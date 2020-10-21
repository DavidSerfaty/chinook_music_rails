# README

Maintenant que ta BDD est prête, tu vas répondre aux questions ci-dessous :

## Niveau facile

Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?
```bash
Album.count
```
Qui est l'auteur de la chanson "White Room" ?
```bash
Track.find_by(title: "White Room").artist
```
Quelle chanson dure exactement 188133 milliseconds ?
```bash
Track.find_by(duration: 188133).title
```
Quel groupe a sorti l'album "Use Your Illusion II" ?
```bash
Album.find_by(title: "Use Your Illusion II").artist
```

## Niveau Moyen
Combien y a t'il d'albums dont le titre contient "Great" ? (indice)
Supprime tous les albums dont le nom contient "music".
Combien y a t'il d'albums écrits par AC/DC ?
Combien de chanson durent exactement 158589 millisecondes ?


## Niveau Difficile
Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

puts en console tous les titres de AC/DC.
puts en console tous les titres de l'album "Let There Be Rock".
Calcule le prix total de cet album ainsi que sa durée totale.
Calcule le coût de l'intégralité de la discographie de "Deep Purple".
Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.
