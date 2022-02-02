writeCode

Write code to execute below expressions.

1. Create a database named `blog`.

use db blog

2. Create a collection called 'articles'.

db.createCollection("articles");

3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

db.articles.insertMany([
  {_id:"977", title: "A Modern Introduction to Programming",
  author:{
    name:"Marijn Haverbeke",
    email:"Marijn@gmail.com",
    age:43
  }
  tags:["JavaScript","Java"]
  },
  {_id:"978", title:"Learning JavaScript Design Patterns", details:"A JavaScript and jQuery Developer's Guide",
  author:{
    name:"Addy Osmani",
    email:"Addy@gmail.com",
    age:47
  }
  tags:["Jquery","JavaScript"]
  },
  {_id:"979", title: "Speaking JavaScript", details: "An In-Depth Guide for Programmers",
  author:{
    name:"Marijn Haverbeke",
    email:"Marijn@gmail.com",
    age:43
  }
  tags:["python","Java"]
  }
])


4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find().pretty();

5. Find a document using \_id field.

db.articles.find({_id:"979"});

6. 1. Find documents using title

db.articles.find({title:"Speaking JavaScript"});

7. 2. Find documents using author's name field.

db.articles.find()

8. Find document using a specific tag.

db.articles.find({tags:"JavaScript"});

9. Update title of a document using its \_id field.

db.articles.update({_id:979},{$set:{title:"Eloquent JavaScript"}});

10. Update a author's name using article's title.

db.articles.update({title:"Eloquent JavaScript"},{$set;{author.name:"Marjin Heverbik"}});

11. rename details field to description from all articles in articles collection.

TODO:

12. Add additional tag in a specific document.

db.articles.update({_id:987},{$push:{tags:"node.js"}});

13. Update an article's title using $set and without $set.

db.articles.update({_id:979},{$set:{title:"JavaScript"}});

db.articles.update({_id:979},{title:"JavaScript"});

- Write the differences here ?

with $ sign it will add and update the value of the document and in case of without $ it will delete the value previous and add only new value.

13. find an article using title and increment it's auhtor's age by 5.

TODO: db.articles.update({title:"JavaScript"},{$set:{$add:[]}})

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.

db.articles.remove({_id:979});

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.

db.users.find(sports:"cricket");

- Update user with extra golf field in sports array whose name is "Steve Ortega".

db.users.update({name:"Steve Ortega"},{$set:{$push:{sports:"golf"}}});

- Find all users who play either 'football' or 'cricket'.

db.users.find({$and:{sports:"football"},{sports:"cricket"}});

db.users.find({sports:{$in:["football","circket"]}});

- Find all users whose name includes 'ri' in their name.

db.users.find($contains:{name:"ri"});