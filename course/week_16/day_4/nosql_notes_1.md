## Week 16 Day 4 Session 1

#### Mongo Part-3

**COLLECTION STRUCTURE**

```json
{
	"_id": ObjectId(),
    "name": <string>,
    "gender": <string>,
    "shirt_size": <string>,
    "language": <string>
}
```

**FIND CRITERIA**

```json
/** Find all the users **/
db.users.find()

/** Find all the users where gender is Male **/
db.users.find({gender: "Male"})

/** Find all the users where gender is not Male **/
db.users.find({gender: {$ne:"Male"}})

/** Find all the users where gender is Male and language is Hindi **/
db.users.find({gender: "Male", language: "Hindi"})
db.users.find({$and: [{gender: "Male"}, {language: "Hindi"}]})

/** Find all the users where gender is Male and language is not Hindi **/
db.users.find({$and: [{gender: "Male"}, {language: {$ne:"Hindi"}}]})

/** Find all the users where shirt size is L or XL **/
db.users.find({$or: [{shirt_size: "L"}, {shirt_size: "XL"}]})
db.users.find({shirt_size: {$in: ["L", "XL"]}})

/** Combining multiple conditions **/
db.users.find({$or: [{$and: [{gender: "Male"}, {shirt_size: "L"}]}, {$and: [{gender: "Female"}, {shirt_size: "M"}]}]})
db.users.find({$and: [{$or: [{$and: [{gender: "Male"}, {shirt_size: "L"}]}, {$and: [{gender: "Female"}, {shirt_size: "M"}]}]}, {language: "English"}]})
db.users.find({$and: [{$or: [{$and: [{gender: "Male"}, {shirt_size: "L"}]}, {$and: [{gender: "Female"}, {shirt_size: "M"}]}]}, {language: {$in: ["English", "Kannada"]}}]})
```

**NOTE: Import bson file into your database**

```shell
mongorestore -d db_name <path>
```