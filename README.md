# how to login with oauth2
Authenticating with OAUTH2 is similar to JWT as both return a token upon success. The main difference is the header and url path.

Existing users admin/password, cinnamon/1234567

# to create user

.post to https://ww-foundation.herokuapp.com/createnewuser
```
expects a username password and email,

{
"username": "bob",
"password": "123",
"email": "bob@bob.com"
}

```

Example login Request:
```
axios.post('https://ww-foundation.herokuapp.com/createnewuser/login', 
    `grant_type=password&username=${this.state.username}&password=${this.state.password}`, 
    {
        headers: {
            // btoa is converting our client id/client secret into base64
            Authorization: `Basic ${btoa('lambda-client:lambda-secret')}`,
            'Content-Type': 'application/x-www-form-urlencoded'
        }
    }
)
```
# ALL PROPERTY ENDPOINTS

# .GET all
```
https://ww-foundation.herokuapp.com/properties/properties
returns all props, restricted by admins
```

# .GET by id
```
https://ww-foundation.herokuapp.com/properties/property/{id} ONLY PROPERTY 7 AND 12 EXIST BY DEFAULT UNLESS ADDED BY YOU
returns specefic property, you can only see your property unless admin 
```


# .POST
```
https://ww-foundation.herokuapp.com/properties/user/{userid}/property
expects a full object
{

    "name": "",
    "bedrooms": 0,
    "neighbourhood": "",
    "roomtype": "",
    "minimumnights": 0,
    "numberofreviews": 0,
    "price": 0
}
```

# .PATCH
```
https://ww-foundation.herokuapp.com/properties/property/{propid}
expects any existing property

"name": "newname"

```


# .PUT

```
https://ww-foundation.herokuapp.com/properties/property/{id}
expects a full object and will replace currently existing object at the given id
{

    "name": "",
    "bedrooms": 0,
    "neighbourhood": "",
    "roomtype": "",
    "minimumnights": 0,
    "numberofreviews": 0,
    "price": 0
}

```

# .DELETE
``` do i need to explain
https://ww-foundation.herokuapp.com/properties/property/{id}
```


