## Week 17 Day 1

### Mongo Part-4

**$gt**
https://docs.mongodb.com/manual/reference/operator/query/gt/

**$gte**
https://docs.mongodb.com/manual/reference/operator/query/gte/

**$lt**
https://docs.mongodb.com/manual/reference/operator/query/lt/

**$lte**
https://docs.mongodb.com/manual/reference/operator/query/lte/

```json
db.students_marks.find({maths: {$gt:50}})
db.students_marks.find({science: {$gte:50}})
db.students_marks.find({english: {$lt:40}})
db.students_marks.find({maths: {$lte:50}})
db.students_marks.find({$and: [{maths: {$gt:50}}, {maths: {$lt:75}}]})
```

**sort**
https://docs.mongodb.com/manual/reference/method/cursor.sort/

```json
/** 1 ASCENDING -1 DESCENDING **/
db.students_marks.find({gender: "Male"}).sort({maths: 1})
db.students_marks.find({gender: "Female"}).sort({science: -1})
db.students_marks.find({}).sort({maths: 1, science: -1})
```

**limit**
https://docs.mongodb.com/manual/reference/method/cursor.limit/

```json
db.students_marks.find({}).sort({maths: 1, science: -1}).limit(10)
```

**skip**
https://docs.mongodb.com/manual/reference/method/cursor.skip/

```json
db.students_marks.find({}).sort({maths: 1, science: -1}).limit(10).skip(20)
```



**count**
https://docs.mongodb.com/manual/reference/method/cursor.count/

```json
db.students_marks.count({gender: "Male"})
db.students_marks.count({maths: {$lte:50}})
```

