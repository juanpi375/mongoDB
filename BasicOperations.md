### [< back](README.md)
## Creation of DBs and basic operations

  1. Start of the MongoDB Server:
      ```
      $ mongod
      ```
  2. Connection to the DB:
      ```
      $ mongo
      ```
  3. Creation of a collection and insertion of documents:
      ```
      use futbolfifa
      db.createCollection("players")
      db.players.insert({name: "Felipe", surname: "Lewis", position: 9, birth: "10/10/90"})
      db.players.insert({name: "Felipe", surname: "Lewis", position: 9, birth: "10/10/90"})
      db.players.insert({name: "Felipe", surname: "Lewis", position: 9, birth: "10/10/90"})
      db.players.insert({name: "Felipe", surname: "Lewis", position: 9, birth: "10/10/90"})
      db.players.insert({name: "Felipe", surname: "Lewis", position: 9, birth: "10/10/90"})
      ```
  4. List the documents:
      ```
      db.players.find({})
      ```
 5. Extra collections in the same DB:
    ```
    db.createCollection("teams")
    db.teams.insert({_id: 100, name: "New Zeland", rank: 27})
    db.teams.insert({_id: 101, name: "Italy", rank: 7})
    db.teams.insert({_id: 102, name: "Poland", rank: 15})

    db.createCollection("championships")
    db.championships.insert({year: 2019, price: 500000})
    db.championships.insert({year: 2020, price: 1500000})
    ```
