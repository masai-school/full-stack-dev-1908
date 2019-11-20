## Week 16 Day 3 Session 2

#### Mongo Part-2

**Show Databases**

```json
show dbs
```

**Create or Work on a Database**

```json
use masai
```

**Show Collections**

```json
show collections
```

**Create Collection**

```json
db.createCollection("students")
```

**Delete Collection**

```json
db.students.drop()
```

**Delete Database**

```json
db.dropDatabase()
```

**Create Data**

```json
db.students.insert({
   code: 'vk_001', 
   name: 'Ajay',
   email: 'ajay@gmail.com',
   batch: "VIKINGS"
})
```

**Read Data**
```json
db.students.find()
db.students.find().pretty()
db.students.find({code:"vk_001"}).pretty()
```

**Update Data**

```json
db.students.updateOne({code: "vk_001"}, {$set: {batch:"Cohort-1"}})
db.students.update({code: "vk_001"}, {$set: {batch:"Cohort-1"}})
db.students.updateMany({}, {$set: {batch:"Cohort-1"}})
db.students.update({}, {$set: {batch:"Cohort-1"}}, {multi:true})
```

**Delete Data**

```json
db.students.remove({})
db.students.remove({code: "vk_001"})
```
