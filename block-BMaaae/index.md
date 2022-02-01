writeCode

Write code to:-

- create a database named `sports`.

use sports

- list all databases present in local mongod server.

show dbs

- create 3 collections named `cricket`, `football`, `TT` in sports databse.

db.createCollection('cricket');
db.createCollection('football');
db.createCollection('TT');
show collections

- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.

  db.cricket.insertMany([
  {
    'name': 'vasant',
    'age': '24',
    'email': 'vasant1197@gamil.com',
    'bid_price': "$500"
  },
  {
    'name': 'anand',
    'age': '26',
    'email': 'anand97@gamil.com',
    'bid_price': "$500"
  },
  {
    'name': 'zehan',
    'age': '23',
    'email': 'zehan9211@gamil.com',
    'bid_price': "$300"
  }]);

  db.football.insertMany([{"name":"zehan","age":23,"email":"zehna9211@gmail.com","bid_price":"$500"},{'name':'anand','age': '26','email': 'anand97@gamil.com','bid_price': "$500"}]);

  db.TT.insertMany([{"name":"zehan","age":23,"email":"zehna9211@gmail.com","bid_price":"$500"},{'name':'vivek','age': '27','email': 'vivek@gamil.com','bid_price': "$500"}]);

- list all collections in sports database.

show collections

- rename `TT` collection to `tennis`.

db.TT.renameCollection("tennis");

- create a capped collection called `khokho` which should have max 3 documents.

db.createCollection("Khokho",{capped:true,size:3});
db.cappedLogCollection.isCapped();

  Try inserting more than 3 and see what happens?

db.football.insertMany([{"name":"zehan","age":23,"email":"zehna9211@gmail.com","bid_price":"$500"},{'name':'anand','age': '26','email': 'anand97@gamil.com','bid_price': "$500"},{'name':'anand','age': '26','email': 'anand97@gamil.com','bid_price': "$500"},{'name':'baljeet','age': '26','email': 'baljeet97@gamil.com','bid_price': "$500"}]);


- check whether a collection is capped or not?

db.cappedLogCollection.isCapped();

- drop all documents from `football` collection.

db.football.drop();

- delete cricket collection completely.

db.cricket.remove();

- delete sports database.

db.dropDatabase();

- check which database you are connected to ?

db

- connect to test database

use test
