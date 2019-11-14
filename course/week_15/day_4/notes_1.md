## Week 15 - Day 4

### Python Flask


```python
from flask import request

@app.route('/users')
def users():
  page = request.args.get('page', default = 1, type = int)
```

### CRUD [Create-Read-Update-Delete]

**HTTP Methods**

- `GET` - Used to fetch the specified resource
- `POST` - Used to create new data at the specified resource
- `PUT` - Used to create new data or replace existing data at the specified resource
- `PATCH` - Used to create new data or update/modify existing data at the specified resource
- `DELETE` - Used to delele existing data at the specified resource



**Common URL Convention**

- `/users` - [GET]  Listing of all resource
- `/users/<id>` - [GET] Details of a specific resource
- `/users` - [POST] Create a new resource
- `/users/<id>` - [PUT] Replace existing resource 
- `/users/<id>` - [PATCH] Modify existing resource
- `/users/<id>` - [DELETE] Delete existing resource

