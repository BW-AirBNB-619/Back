# how to login with oauth2 for my boy troy
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
```
#post to  https://ww-foundation.herokuapp.com/properties/user/{userid}/property

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

.UPDATE to https://ww-foundation.herokuapp.com/properties/property/{propid}
can send a single property
example
```
"name": "newname"

```
.DELETE to https://ww-foundation.herokuapp.com/properties/property/{id}



