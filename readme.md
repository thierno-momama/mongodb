# Créer et entré une nouvelle base :
```
use mesclients (crée la bdd client et rentre directement de dans)
db (pour voir ou nous sommes)

```
# Crée notre premier utilisateur
````
db.createUser({
    user: "Alex",
    pwd: "123",
    roles: ["readWrite", "dbAdmin"]
});

```
# Insert dans une table
````
db.clients.insert([{nom: "Olland", prenom: "Alexis"}, {nom: "Saint", prenom:"Justine"}]);
```
# Pour voir les differentes informations

db.clients.find();

# Pour insert un nouveau client dans la bdd

```
db.clients.insert({nom: "Dante", prenom: "Jean", sexe: "Homme"});
db.clients.find();
```
# Pour formatter l'affichage

```
db.clients.find().pretty();
```
# Modifier une information avec l'identifiant mais ici l'identifiant est le nom Saint
```
db.clients.update({nom: "Saint"}, {$set:{sexe: "Femme"}});
db.clients.find().pretty(); (formatter et voir le resultat)
```
# Pour enlever les données à un client au lieu de mettre set on met unset et le :1 identifie la clé qui doit être supprimer
```
db.clients.update({nom: "Olland"}, {$unset:{sexe:1}});
db.clients.find().pretty();
```
# Renommer le nom d'un champs par exemple le champs sexe en age
```
db.clients.update({name: "Saint"}, {$rename: {"sexe":"age"}});
db.clients.find().pretty();
```
# Supprimer un client
```
db.clients.remove({nom: "Dante"});
db.clients.find().pretty();
```
# Les operateurs OR et AND example recherché un employé qui s'appel Jean ou qui a 23 ans
```
db.clients.find({$or: [{age: 23}, {prenom: "Alexis"}]}).pretty();
db.clients.find({$and: [{age: 23}, {prenom: "Alexis"}]}).pretty();
```
# Les operateurs de comparaisons: $lt = plus petit que exple: age plus petit que et pour l'operateur plus grand que , on utilise $gt
```
db.clients.find({age:{$lt:25}}).pretty();
db.clients.find({age:{$gt:25}}).pretty();
```
# Pour trier on met 1 pour un ordre croissant et -1 , pour un ordre decroissant
```
db.clients.find().sort({nom:1}).pretty();
db.clients.find().sort({nom:-1}).pretty();
```
