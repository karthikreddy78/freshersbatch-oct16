1)	db.zipcodes.find({city:'ATLANTA',state:'GA'})

2)	`db.zipcodes.aggregate([{$match:{city:'ATLANTA',state:'GA'}}])

3)	db.zipcodes.aggregate([{$match:{city:"ATLANTA"}},{$count:"pop"}])
{ pop: 41 }

4)	db.zipcodes.aggregate([{$match:{city:"ATLANTA"}},{$group:{_id:{city:"ATLANTA"},count:{$sum:"$pop"}}}])

5)	db.zipcodes.aggregate([{$group:{_id:"$state",total:{$sum:"$pop"}}}])

6)	db.zipcodes.aggregate([{$group:{_id:"$state",total:{$sum:"$pop"}}},{$sort:{total:-1}}])

7)	db.zipcodes.aggregate([{$group:{_id:{city:"$city",state:"$state"},total:{$sum:"$pop"}}}])

8)	db.zipcodes.aggregate([{$group:{_id:{city:"$city",state:"$state"},total:{$sum:"$pop"}}},{$sort:{total:-1}}])

9)	db.zipcodes.aggregate([{$group:{_id:{city:"$city",state:"$state"},total:{$sum:"$pop"}}},{$sort:{total:-1}},{$limit:3}])

10)	db.zipcodes.aggregate([{$group:{_id:{city:"$city",state:"Texas"},total:{$sum:"$pop"}}},{$sort:{total:-1}},{$limit:3}])

11)	db.zipcodes.aggregate([{$group:{_id:"$state",total:{$avg:"$pop"}}}])

12)	db.zipcodes.aggregate([{$group:{_id:"$state",total:{$avg:"$pop"}}},{$sort:{total:-1}},{$limit:3}])