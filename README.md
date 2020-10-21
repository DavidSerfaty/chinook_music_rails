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
```bash
Album.where("title like ?", 'Great %').count
```
Supprime tous les albums dont le nom contient "music".
```bash
Album.where("title like ?", '%music %').delete_all
```
Combien y a t'il d'albums écrits par AC/DC ?
```bash
Album.where("artist like ?", 'AC/DC').count
```
Combien de chanson durent exactement 158589 millisecondes ?
```bash
Track.where("duration like ?", 158589).count
==> 0
```

## Niveau Difficile
Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

puts en console tous les titres de AC/DC.
```bash
tracks = Track.where("artist like ?", "AC/DC")
tracks.each do |track|
  puts track.title
end
```
puts en console tous les titres de l'album "Let There Be Rock".
```bash
tracks = Track.where("album like ?", "Let There Be Rock")
tracks.each do |track|
  puts track.title
end
```
Calcule le prix total de cet album ainsi que sa durée totale.
```bash
total_price = 0
total_duration = 0
tracks = Track.where("album like ?", "Let There Be Rock")
tracks.each do |track|
  total_price += track.price
  total_duration += track.duration
end
  puts "Prix total : #{total_price} et durée total : #{total_duration}"
```
Calcule le coût de l'intégralité de la discographie de "Deep Purple".
```bash
total_price = 0
tracks = Track.where("artist like ?", "Deep Purple")
tracks.each do |track|
  total_price += track.price
end
puts total_price
```
Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.
```bash
Track.where("artist like ?", "Eric Clapton").each do |track|
  track.update(artist: "Britney Spears")
end
```
