## Week 16 - Day 1

#### User Addresses Manager

Submission folder `submissions/<your_folder>/week_16/day_1/session_1`

**NOTE: The API urls and the request and response formats for both server_csv.py and server_json.py should remain the same**

**Backend** - Filename `server_csv.py`

File - `users.csv`
```
id, name, mobile, email
```

File - `addresses.csv`
```
id, user_id, line_1, city, pincode
```

### FSD.FLSK.3.1
- List the Users

### FSD.FLSK.3.2
- Create an user

### FSD.FLSK.3.3
- Get the details of an user along with his addresses

### FSD.FLSK.3.4
- Modify the user details

### FSD.FLSK.3.5
- Delete an user

### FSD.FLSK.3.6
- Add an address to the user

### FSD.FLSK.3.7
- Modify the details of a particular address

### FSD.FLSK.3.8
- Delete a particular address

**Backend** - Filename `server_json.py`

File - `user_addresses.json`

```json
[
	{
        "id" : <number>,
        "name": <string>,
        "mobile": <string>,
        "email": <string>,
        "addresses": [
            {
				"id": <number>,
        		"line_1": <string>,
        		"city": <string>,
        		"pincode": <string>
            }
        ]
    }
]
```

### FSD.FLSK.3.9
- List the Users

### FSD.FLSK.3.10
- Create an user

### FSD.FLSK.3.11
- Get the details of an user along with his addresses

### FSD.FLSK.3.12
- Modify the user details

### FSD.FLSK.3.13
- Delete an user

### FSD.FLSK.3.14
- Add an address to the user

### FSD.FLSK.3.15
- Modify the details of a particular address

### FSD.FLSK.3.16
- Delete a particular address