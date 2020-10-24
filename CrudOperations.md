[< back](./README.md)
## Practise of CRUD operations
1. Creation of the database:
  ```
  use flow
  db.createCollection("movies")
  ```
2. Insertion of movies with different methods:
  ```
  db.movies.insert({title: "Mortal Engines", 
                    year: 2018, 
                    rating: 4.0, 
                    genre: "adventure", 
                    description: "Following a cataclysmic conflict known as the Sixty Minute War..", 
                    actors: [{name: "Hera", surname: "Hilmar"}, {name: "Robert", surname: "Sheehan"}, {name: "Hugo", surname: "Weaving"}], 
                    country: "New Zealand", 
                    income: 85000000, 
                    duration: 128})
  db.movies.insertOne({title: "The Longest Ride", 
                       year: 2015, 
                       rating: 3.8, 
                       genre: "romance", 
                       description: "On the way home from their first date..", 
                       actors:[{name: "Scott", surname: "Eastwood"},{name: "Britt", surname: "Robertson"},{name: "Jack", surname: "Huston"},{name: "Oona", surname: "Chaplin"}], 
                       country: "United States", 
                       income: 38000000, 
                       duration: 127})
  
  db.movies.insertMany([{title: "The Founder", 
                          year: 2016, 
                          rating: 4.2, 
                          genre: "biographic", 
                          description: "In 1954, Ray Kroc is a traveling milkshake machine salesman..", 
                          actors: [{name: "Michael", surname: "Keaton"}, {name: "Nick", surname: "Offerman"}, {name: "John Carroll", surname: "Lynch"}], 
                          country: "United States", 
                          income: 24000000, 
                          duration: 115},
                          
                          {title: "Seven Pounds", 
                          year: 2008, 
                          rating: 4.6, 
                          genre: "biographic", 
                          description: "In Los Angeles, Ben Thomas cruelly berates a sales representative, Ezra Turner, over the phone..", 
                          actors: [{name: "Will", surname: "Smith"}, {name: "Rosario", surname: "Dawson"}, {name: "Michael", surname: "Ealy"}], 
                          country: "United States", 
                          income: 169000000, 
                          duration: 123}
                          ])
  ```
  3. A pair of updates over all documents using filters:
      ```
      db.movies.updateMany(
        {rating: {$gt: 4.5}},
        {$set: {highlighted: true}}
      )
      
      db.movies.updateMany(
        {genre: "drama"},
        {$set: {genre: "boring"}}
      )
      ```
 5. Delete method with parameter:
    ```
    db.movies.deleteMany(
      {year: {$lt: new Date().getFullYear - 30}}
    )
    ```
 6. Find movies with a single parameter:
    ```
    db.movies.find(
      {country: "Argentina"}
    )
    ```
 7. Find movies with multiple parameters:
    ```
    db..movies.find(
      {
        genre: "action",
        rating: {$gt: 4.0},
        year: {$gte: new Date().getFullYear - 2}
      }
    )
    ```
  
  
