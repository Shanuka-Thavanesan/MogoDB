**1. Create a Database called movies.**
```
 use movie

switched to db movie
```
**2. Create a collection called moviedetails.**
```
 db.createCollection("moviesdetails")

{ ok: 1 }
```
**3. Create the above 5 movie documents into a moviedetails collection.**
```
  movie> db.moviesdetails.insertMany([{
Movie Title:"Jurassic Park",Type:"Adventure",Director:"steven Spielberg",Release year:1993},{Movie Title:"Forrest Gump",Type:"drama",Director:"Robert Zemeckies",Release year:1994},{Movie Title:"Titanic",Type:"Romance",Director:"James Cameron",Release Year:1997},{Movie Tile:"The Dark Knight",Type:"Action",Director:"Christopher Nolan",Release Year:2008},{Movie Title:"Avatar",Type:"Science Fiction",Director:"James Cameron",Release Year:2009}])

{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654c7f5117597cba8b45c14f"),
    '1': ObjectId("654c7f5117597cba8b45c150"),
    '2': ObjectId("654c7f5117597cba8b45c151"),
    '3': ObjectId("654c7f5117597cba8b45c152"),
    '4': ObjectId("654c7f5117597cba8b45c153")
  }
}
```
**4. List all documents created.**
```
movie> db.moviesdetails.find()

[
  {
    _id: ObjectId("654c7f5117597cba8b45c14f"),
    Movie Title: 'Jurassic Park',
    Type: 'Adventure',
    Director: 'steven Spielberg',
    Release year: 1993
  },
  {
    _id: ObjectId("654c7f5117597cba8b45c150"),
    Movie Title: 'Forrest Gump',
    Type: 'drama',
    Director: 'Robert Zemeckies',
    Release year: 1994
  },
  {
    _id: ObjectId("654c7f5117597cba8b45c151"),
    Movie Title: 'Titanic',
    Type: 'Romance',
    Director: 'James Cameron',
    Release Year: 1997
  },
{
    _id: ObjectId("654c7f5117597cba8b45c152"),
    Movie Tile: 'The Dark Knight',
    Type: 'Action',
    Director: 'Christopher Nolan',
    Release Year: 2008
  },
  {
    _id: ObjectId("654c7f5117597cba8b45c153"),
    Movie Title: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    Release Year: 2009
  }
]
```
**5.List James Cameron’s movies.**
```
 db.moviesdetails.find({"Director":"James Cameron"})

[
  {
    _id: ObjectId("654c7f5117597cba8b45c151"),
    Movie Title: 'Titanic',
    Type: 'Romance',
    Director: 'James Cameron',
    Release Year: 1997
  },
  {
    _id: ObjectId("654c7f5117597cba8b45c153"),
    Movie Title: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    Release Year: 2009
  }
]
```
**6. List  James Cameron’s movies released in 2009.**
```
db.moviesdetails.find({"Release Year":2009})

[
  {
    _id: ObjectId("654c7f5117597cba8b45c153"),
    Movie Title: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    Release Year: 2009
  }
]
```
**7. Delete the movie which you don’t like.**
```
db.moviesdetails.remove({"Movie Title":"Forrest Gump"})

DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 1 }
```
**8. Add the movie which is your favorite.**
```
 db.moviesdetails.insertOne({"Movie Title":"Frozen","Type":"Drama","Director":"Jennifer Lee","Release Year":2013})

{
  acknowledged: true,
  insertedId: ObjectId("654c85f517597cba8b45c154")
}
```
**9. List movie Directed  by Christopher Nolan in 1994.**
```
db.moviesdetails.find({"Director":"Christopher Nolan","Release Year":1994})

empty result
```
**10. List out the Director’s Name in your document.**
```
db.moviesdetails.distinct("Director")

[
  'Christopher Nolan',
  'James Cameron',
  'Jennifer Lee',
  'steven Spielberg'
]
```
























