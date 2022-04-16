# Pour voir la bdd on fait : 
```
bd
```
# Pour afficher la bdd
```
show dbs
```
# Pour créer une bdd:
```
use blog
```
# Pour créer une collection
```
db.createCollection("posts")
```
# Pour inserer
```
db.posts.insertOne({
    title: 'Post 1',
    body: 'Body of post 1',
    category: 'New',
    likes: 1,
    tags: ['news', 'events'],
    date: Date()
})
```
# Pour insert plusieurs
```
db.posts.insertMany([
    {
        title: 'Post 2',
        body: 'Body of post 2',
        category: 'New',
        likes: 2,
        tags: ['news', 'events'],
        date: Date()
    },
    {
        title: 'Post 3',
        body: 'Body of post 3',
        category: 'New',
        likes: 3,
        tags: ['news', 'events'],
        date: Date()
    },
    {
        title: 'Post 4',
        body: 'Body of post 4',
        category: 'New',
        likes: 4,
        tags: ['news', 'events'],
        date: Date()
    },
    {
        title: 'Post 5',
        body: 'Body of post 5',
        category: 'New',
        likes: 5,
        tags: ['news', 'events'],
        date: Date()
    },
    {
        title: 'Post 6',
        body: 'Body of post 6',
        category: 'New',
        likes: 6,
        tags: ['news', 'events'],
        date: Date()
    }
])
```
# Pour voir tous les documents de la collection
```
db.posts.find()
```
# Pour voir seulement les documents qui ont une categories
```
db.posts.find({category: 'New'})
```
# Pour Trier en fonction du titre: 1 croissant et -1 decroissant
```
db.posts.find().sort({title: 1})
```
# Pour count category
```
db.posts.find({category: 'New'}).count()
```
# Pour limiter ou bien findOne
```
db.posts.find().limit(2)
db.posts.findOne()
```
# Pour findOne dont like est superieur à 3
```
db.posts.findOne({likes: {$gt: 3}})
```
# Pour update
```
db.posts.update({title: 'Post 1'}, {$set: {category: "Tech"}})

db.posts.updateOne({ title: 'Post 6' }, { 
    $set: { 
        title: 'Post 6', 
        body: 'Body of post.', 
        category: 'News' } }, { upsert: true })
```
# Pour incrementer une valeur
```
db.posts.update({ title: 'Post 1' }, { $inc: { likes: 2 } })
```
# update many increment
```
db.posts.updateMany({}, {$inc: {likes: 1}})
```
# Delete one
```
db.posts.deleteOne({title: 'Post 6'})
```
# deleteMany
```
db.posts.deleteMany({category: "Tech"})
```
