Exercise Questions

1)	db.addresses.find()

2)	db.addresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:1})

3)	db.addresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:0})

4)	db.addresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:0,"address.zipcode":1})

5)	db.addresses.aggregate([{$match:{"borough":"Bronx"}},{$limit:5}])

6)	db.addresses.aggregate([{$match:{"borough":"Bronx"}}])

7)	db.addresses.aggregate([{$match:{"borough":"Bronx"}},{$skip:5},{$limit:5}])

8)	db.addresses.find({grades : { $elemMatch:{"score":{$gt : 90}}}})

9)	db.addresses.find({grades : { $elemMatch:{"score":{$gt : 80,$lte:100}}}})

10)	db.addresses.find({"address.coord.0" : {$lt :-95.754168}})

11)	db.addresses.find({$and:[{"cuisine" : {$ne :"American "}},{"grades.score" : {$gt : 70}}, {"address.coord.0" : {$lt : -65.754168}}]});

12)	db.addresses.find({$and:[{"cuisine" : {$ne :"American "}},{"grades.score" : {$gt : 70}}, {"address.coord.1" : {$lt : -65.754168}}]});

13)	db.addresses.find({$and:[{"cuisine" : {$ne :"American "}},{"borough" : {$ne :"Brooklyn "}},{"grades.grade" : 'A'}]}).sort({"cuisine":-1});

14)	db.addresses.find({name: /^Wil/},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1});

15)	db.addresses.find({name: /^Wil/},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1});

16)	db.addresses.find({name: /.*Reg.*/},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1})

17)	db.addresses.find({$and:[{"cuisine" : {$in :["American","Chinese"]}},{"borough" : "Bronx"}]});

18)	db.addresses.find({"borough" : {$in :["Bronx","Brooklyn","Queens","Staten Island"]}},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:0});

19)	db.addresses.find({"borough" : {$nin :["Bronx","Brooklyn","Queens","Staten Island"]}},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:0});

20)	db.addresses.find({grades : { $elemMatch:{"score":{$lt : 10}}}},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,_id:0});

21)	db.addresses.find({$or: [  {name: /^Wil/}, {"$and": [    {"cuisine" : {$ne :"American "}}, {"cuisine" : {$ne :"Chinees"}}]}]},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1});

22)	

23)

24)	db.addresses.find( {$and:[{"address.coord.1" : {$lt : 52.0}},{"address.coord.1" : {$gt : 42.0}}]},{"restaurant_id" : 1,"name":1,"address":1,_id:0});

25)	db.addresses.find({}).sort({"name":1})

26)	db.addresses.find({}).sort({"name":-1})

27)	db.addresses.find({}).sort({"cuisine":1,"borough":-1})

28)	db.addresses.find({"address.street":{$exists:true}})

29)	db.addresses.find({"address.street":{$type:1}})

30)	db.addresses.find(  {"grades.score" : {$mod : [7,0]} },{"restaurant_id" : 1,"name":1,"grades":1});

31)	db.addresses.find({"name":/.*mon.*/},{"restaurant_id" : 1,"name":1,"address.coord":1})

32)	db.addresses.find({"name":/^Mad/},{"restaurant_id" : 1,"name":1,"address.coord":1})