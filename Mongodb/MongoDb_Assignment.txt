show databases
MongoLearn      73.7 kB
Mydb            81.9 kB
Sample1         81.9 kB
VideoPlayer       41 kB
ecommerce        225 kB
empdb             41 kB
eventsdb          41 kB
mongo_practice  8.19 kB
test            8.19 kB
admin            348 kB
local           5.26 GB
use mongo_practice
'switched to db mongo_practice'
show collections
movies
db.movies.insertMany([
{
title: "Fight Club" ,
writer: "Chuck Palahniuko",
year: 1999,
actors : [
"Brad Pitt",
"Edward Norton"
]
},

{ title : "Pulp Fiction",
writer : "Quentin Tarantino",
year: 1994,
actors : [
"John Travolta",
"Uma Thurman"
]
},

{
title: "Inglorious Basterds", writer : "Quentin Tarantino" ,
year: 2009,
actors : [
"Brad Pitt",
"Diane Kruger",
"Eli Roth"
]
},

{
title: "The Hobbit: An Unexpected Journey",
writer: "J.R.R. Tolkein",
year: 2012,
franchise: "The Hobbit"
},

{
title : "The Hobbit: The Desolation of Smaug", writer: "J.R.R. Tolkein",
year: 2013,
franchise: "The Hobbit"
},

{
title: "The Hobbit: The Battle of the Five Armies",
writer : "J.R.R. Tolkein",
year: 2012,
franchise: "The Hobbit",
synopsis: "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
},

{
title: "Pee Wee Herman's Big Adventure"
},

{
title : "Avatar"
}
]
)
{ acknowledged: true,
  insertedIds: 
   { '0': ObjectId("617f7c183d92108c6f234108"),
     '1': ObjectId("617f7c183d92108c6f234109"),
     '2': ObjectId("617f7c183d92108c6f23410a"),
     '3': ObjectId("617f7c183d92108c6f23410b"),
     '4': ObjectId("617f7c183d92108c6f23410c"),
     '5': ObjectId("617f7c183d92108c6f23410d"),
     '6': ObjectId("617f7c183d92108c6f23410e"),
     '7': ObjectId("617f7c183d92108c6f23410f") } }
db.movies.find().pretty()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
{ _id: ObjectId("617f7c183d92108c6f23410a"),
  title: 'Inglorious Basterds',
  writer: 'Quentin Tarantino',
  year: 2009,
  actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ] }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
{ _id: ObjectId("617f7c183d92108c6f23410e"),
  title: 'Pee Wee Herman\'s Big Adventure' }
{ _id: ObjectId("617f7c183d92108c6f23410f"), title: 'Avatar' }
db.find({writer:"Quentin Tarantino"}).pretty()
TypeError: db.find is not a function
use movies
'switched to db movies'
db.find({writer:"Quentin Tarantino"}).pretty()
TypeError: db.find is not a function
use mongo_practice
'switched to db mongo_practice'
db.movies.find({writer:"Quentin Tarantino"}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
{ _id: ObjectId("617f7c183d92108c6f23410a"),
  title: 'Inglorious Basterds',
  writer: 'Quentin Tarantino',
  year: 2009,
  actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ] }
db.movies.find({actor:"Brad Pitt"}).pretty()
db.movies.find({actor:["Brad Pitt"]}).pretty()
db.movies.find({actors:["Brad Pitt"]}).pretty()
db.movies.find({actors:"Brad Pitt"}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f23410a"),
  title: 'Inglorious Basterds',
  writer: 'Quentin Tarantino',
  year: 2009,
  actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ] }
db.movies.find({franchise: "The Hobbit"}).pretty()
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
db.movies.find(year:{$gte:1990},year:{$lt:2000}).pretty()
SyntaxError: Unexpected token, expected "," (1:19)

> 1 | db.movies.find(year:{$gte:1990},year:{$lt:2000}).pretty()
    |                    ^
db.movies.find({year:{$gte:1990},year:{$lt:2000}}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
db.movies.find({year:{$lt:2000},year:{$gt:2010}}).pretty()
Error: connect ETIMEDOUT 3.86.126.133:27017 could not be cloned.
db.movies.find({year:{$lt:2000},year:{$gt:2010}}).pretty()
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
db.movies.find($or:[{year:{$lt:2000},year:{$gt:2010}}]).pretty()
SyntaxError: Unexpected token, expected "," (1:18)

> 1 | db.movies.find($or:[{year:{$lt:2000},year:{$gt:2010}}]).pretty()
    |                   ^
db.movies.find($or:[year:{$lt:2000},year:{$gt:2010}]).pretty()
SyntaxError: Unexpected token, expected "," (1:18)

> 1 | db.movies.find($or:[year:{$lt:2000},year:{$gt:2010}]).pretty()
    |                   ^
db.movies.find( {$or:[year:{$lt:2000},year:{$gt:2010}]}).pretty()
SyntaxError: Unexpected token, expected "," (1:26)

> 1 | db.movies.find( {$or:[year:{$lt:2000},year:{$gt:2010}]}).pretty()
    |                           ^
db.movies.find( {$or:[{year:{$lt:2000}},{year:{$gt:2010}}]}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
db.movies.updateOne({title : "The Hobbit: An Unexpected Journey"},{$set : {"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
SyntaxError: Unexpected token (1:257)

> 1 | db.movies.updateOne({title : "The Hobbit: An Unexpected Journey"},{$set : {"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
    |                                                                                                                                                                                                                                                                  ^
db.movies.updateOne({title : "The Hobbit: An Unexpected Journey"},{$set : {synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
{ acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0 }
db.movies.updateOne({title : "The Hobbit: The Desolation of Smaug"},{$set : {"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
SyntaxError: Unexpected token (1:271)

> 1 | db.movies.updateOne({title : "The Hobbit: The Desolation of Smaug"},{$set : {"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
    |                                                                                                                                                                                                                                                                                ^
db.movies.updateOne({title : "The Hobbit: The Desolation of Smaug"},{$set : synopsis: {"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
SyntaxError: Unexpected token, expected "," (1:84)

> 1 | db.movies.updateOne({title : "The Hobbit: The Desolation of Smaug"},{$set : synopsis: {"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
    |                                                                                     ^
db.movies.updateOne({title : "The Hobbit: The Desolation of Smaug"},{$set : {synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
{ acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0 }
db.movies.find().pretty()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
{ _id: ObjectId("617f7c183d92108c6f23410a"),
  title: 'Inglorious Basterds',
  writer: 'Quentin Tarantino',
  year: 2009,
  actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ] }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit',
  synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
{ _id: ObjectId("617f7c183d92108c6f23410e"),
  title: 'Pee Wee Herman\'s Big Adventure' }
{ _id: ObjectId("617f7c183d92108c6f23410f"), title: 'Avatar' }
db.movies.find({title:"Pulp Fiction"}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman' ] }
db.movies.updateOne({title:"Pulp Fiction"},{$push: {actors:"Samuel L.Jackson"}})
{ acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0 }
db.movies.find({title:"Pulp Fiction"}).pretty()
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman', 'Samuel L.Jackson' ] }

use mongo_practice
'switched to db mongo_practice'
db.movies.createIndex({synopsis:"text"})
'synopsis_text'
db.movies.find()
{ _id: ObjectId("617f7c183d92108c6f234108"),
  title: 'Fight Club',
  writer: 'Chuck Palahniuko',
  year: 1999,
  actors: [ 'Brad Pitt', 'Edward Norton' ] }
{ _id: ObjectId("617f7c183d92108c6f234109"),
  title: 'Pulp Fiction',
  writer: 'Quentin Tarantino',
  year: 1994,
  actors: [ 'John Travolta', 'Uma Thurman', 'Samuel L.Jackson' ] }
{ _id: ObjectId("617f7c183d92108c6f23410a"),
  title: 'Inglorious Basterds',
  writer: 'Quentin Tarantino',
  year: 2009,
  actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ] }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit',
  synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
{ _id: ObjectId("617f7c183d92108c6f23410e"),
  title: 'Pee Wee Herman\'s Big Adventure' }
{ _id: ObjectId("617f7c183d92108c6f23410f"), title: 'Avatar' }
db.movies.find({$text:{$search:"Bilbo"}})
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit',
  synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.' }
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
db.movies.find({$text:{$search:"Gandalf"}})
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit',
  synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.' }
db.movies.find({$text:{$search:"Bilbo -Gandalf"}})
{ _id: ObjectId("617f7c183d92108c6f23410d"),
  title: 'The Hobbit: The Battle of the Five Armies',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.' }
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
db.movies.find({$text:{$search:"dwarves hobbit"}})
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
{ _id: ObjectId("617f7c183d92108c6f23410c"),
  title: 'The Hobbit: The Desolation of Smaug',
  writer: 'J.R.R. Tolkein',
  year: 2013,
  franchise: 'The Hobbit',
  synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.' }
db.movies.find({$or: [{$text:{$search:"dwarves -hobbit"}},{$text:{$search:"hobbit -dwarves"}}]})
MongoServerError: Too many text expressions
db.movies.find({$text:{$search:"gold dragon"}})
{ _id: ObjectId("617f7c183d92108c6f23410b"),
  title: 'The Hobbit: An Unexpected Journey',
  writer: 'J.R.R. Tolkein',
  year: 2012,
  franchise: 'The Hobbit',
  synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.' }
db.movies.deleteOne({title:"Avatar"})
{ acknowledged: true, deletedCount: 1 }
db.movies.deleteOne({title:"Pee Wee Herman's Big Adventure"})
{ acknowledged: true, deletedCount: 1 }

db.users.insertMany([{
username: "GoodGuyGreg",
first_name: "Good Guy",
last_name: "Greg"
},
{
username: "ScumbagSteve",
full_name:
{
first: "Scumbag",
last: "Steve"
}
}
])
{ acknowledged: true,
  insertedIds: 
   { '0': ObjectId("617fb9c42341e0564d529350"),
     '1': ObjectId("617fb9c42341e0564d529351") } }
db.posts.insertMany([
{
username: "GoodGuyGreg",
title: "Passes out at party",
body : "Wakes up early and cleans house"
},
{
username: "GoodGuyGreg", title: "Steals your identity", body: "Raises your credit score"
}, 
{
username: "GoodGuyGreg",title: "Reports a bug in your code",body: "Sends you a Pull Request"
},
{
username: "ScumbagSteve", title : "Borrows something", body: "Sells it"
},
{
username: "ScumbagSteve", title : "Borrows everything", body : "The end"},
{
username: "ScumbagSteve",title: "Forks your repo on github", body: "Sets to private"
}
])
{ acknowledged: true,
  insertedIds: 
   { '0': ObjectId("617fbabf2341e0564d529352"),
     '1': ObjectId("617fbabf2341e0564d529353"),
     '2': ObjectId("617fbabf2341e0564d529354"),
     '3': ObjectId("617fbabf2341e0564d529355"),
     '4': ObjectId("617fbabf2341e0564d529356"),
     '5': ObjectId("617fbabf2341e0564d529357") } }
db.posts.find().pretty()
{ _id: ObjectId("617fbabf2341e0564d529352"),
  username: 'GoodGuyGreg',
  title: 'Passes out at party',
  body: 'Wakes up early and cleans house' }
{ _id: ObjectId("617fbabf2341e0564d529353"),
  username: 'GoodGuyGreg',
  title: 'Steals your identity',
  body: 'Raises your credit score' }
{ _id: ObjectId("617fbabf2341e0564d529354"),
  username: 'GoodGuyGreg',
  title: 'Reports a bug in your code',
  body: 'Sends you a Pull Request' }
{ _id: ObjectId("617fbabf2341e0564d529355"),
  username: 'ScumbagSteve',
  title: 'Borrows something',
  body: 'Sells it' }
{ _id: ObjectId("617fbabf2341e0564d529356"),
  username: 'ScumbagSteve',
  title: 'Borrows everything',
  body: 'The end' }
{ _id: ObjectId("617fbabf2341e0564d529357"),
  username: 'ScumbagSteve',
  title: 'Forks your repo on github',
  body: 'Sets to private' }
db.createCollection("comments")
{ ok: 1 }

db.comments.insertOne({
username: "GoodGuyGreg",
comment : "Hope you got a good deal!",
post : ObjectId("617fbabf2341e0564d529355")
})
{ acknowledged: true,
  insertedId: ObjectId("617fc7e32341e0564d529358") }
db.posts.find({_id: "617fc7e32341e0564d529358"})
db.posts.find({_id: ObjectId("617fc7e32341e0564d529358")})
db.comments.find({_id: ObjectId("617fc7e32341e0564d529358")})
{ _id: ObjectId("617fc7e32341e0564d529358"),
  username: 'GoodGuyGreg',
  comment: 'Hope you got a good deal!',
  post: ObjectId("617fbabf2341e0564d529355") }
db.comments.insertMany([
{
username: "GoodGuyGreg",
comment : "What's mine is yours!",
post : ObjectId("617fbabf2341e0564d529356")
},
{
username: "GoodGuyGreg",
comment : "Don't violate the licensing agreement!",
post : ObjectId("617fbabf2341e0564d529357")
},
{
username: "ScumbagSteve",
comment : "It still isn't clean",
post : ObjectId("617fbabf2341e0564d529352")
},
{
username: "ScumbagSteve",
comment : "Denied your PR cause I found a hack",
post : ObjectId("617fbabf2341e0564d529354")
}
]



)
{ acknowledged: true,
  insertedIds: 
   { '0': ObjectId("617fd8602341e0564d529359"),
     '1': ObjectId("617fd8602341e0564d52935a"),
     '2': ObjectId("617fd8602341e0564d52935b"),
     '3': ObjectId("617fd8602341e0564d52935c") } }


db.users.find()
{ _id: ObjectId("617fb9c42341e0564d529350"),
  username: 'GoodGuyGreg',
  first_name: 'Good Guy',
  last_name: 'Greg' }
{ _id: ObjectId("617fb9c42341e0564d529351"),
  username: 'ScumbagSteve',
  full_name: { first: 'Scumbag', last: 'Steve' } }

db.posts.find({username: "GoodGuyGreg"})
{ _id: ObjectId("617fbabf2341e0564d529352"),
  username: 'GoodGuyGreg',
  title: 'Passes out at party',
  body: 'Wakes up early and cleans house' }
{ _id: ObjectId("617fbabf2341e0564d529353"),
  username: 'GoodGuyGreg',
  title: 'Steals your identity',
  body: 'Raises your credit score' }
{ _id: ObjectId("617fbabf2341e0564d529354"),
  username: 'GoodGuyGreg',
  title: 'Reports a bug in your code',
  body: 'Sends you a Pull Request' }
db.comments.find()
{ _id: ObjectId("617fc7e32341e0564d529358"),
  username: 'GoodGuyGreg',
  comment: 'Hope you got a good deal!',
  post: ObjectId("617fbabf2341e0564d529355") }
{ _id: ObjectId("617fd8602341e0564d529359"),
  username: 'GoodGuyGreg',
  comment: 'What\'s mine is yours!',
  post: ObjectId("617fbabf2341e0564d529356") }
{ _id: ObjectId("617fd8602341e0564d52935a"),
  username: 'GoodGuyGreg',
  comment: 'Don\'t violate the licensing agreement!',
  post: ObjectId("617fbabf2341e0564d529357") }
{ _id: ObjectId("617fd8602341e0564d52935b"),
  username: 'ScumbagSteve',
  comment: 'It still isn\'t clean',
  post: ObjectId("617fbabf2341e0564d529352") }
{ _id: ObjectId("617fd8602341e0564d52935c"),
  username: 'ScumbagSteve',
  comment: 'Denied your PR cause I found a hack',
  post: ObjectId("617fbabf2341e0564d529354") }

var result=db.posts.find({title:"Reports a bug in your code"},{_id:1})
result
{ _id: ObjectId("617fbabf2341e0564d529354") }
