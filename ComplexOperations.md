[< back](./README.md)
## Queries, filters and complex operations

1. Connection to the previous excercise DB:
    ```
    use flow
    ```
2. List of all the movies by some criteria:
    ```
    db.movies.find({year: 2018})
    ```
3. List all the elements with a limit:
    ```
    db.movies.find({country: "United States"}).limit(10)
    ```
4. List with methods for pagination: 
    ```
     db.movies.find().sort({income: -1}).limit(5)
     
     db.movies.find().sort({income: -1}).skip(5).limit(5)
    ```
 5. Previous methods showing only some of its attributes:
    ```
    db.movies.find({country: "United States"}, {title: 1, genre: 1, _id: 0}).limit(10)
    
    db.movies.find().sort({income: -1}, {title: 1, genre: 1, _id: 0}).limit(5)
    db.movies.find().sort({income: -1}, {title: 1, genre: 1, _id: 0}).skip(5).limit(5)
    ```
 6. List that shows all different countries:
    ```
    db.movies.distinct("country")
    ```
