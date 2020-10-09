# How To Implement API Authentication with JSON Web Tokens and Passport

From:  https://www.digitalocean.com/community/tutorials/api-authentication-with-json-web-tokensjwt-and-passport

## Run mongodb from the mypdx project

Start the mypdx app:

```
./manage start
```

To setup mongodb, get the docker id:

```
docker ps
docker exec -it 5c3b9f918329 bash
```

... and then in the docker shell ...

```
mongo "mongodb://root:example@localhost:27017/"
use passport-jwt
db.createUser({user:"root", pwd:"example", roles:[{ role: "readWrite", db: "passport-jwt" }]})
show users
```

Then exit the shell.

## Start the jwt example app

In a separate bash shell:

```
git clone https://github.com/ianco/jwt-and-passport-auth.git
cd jwt-and-passport-auth
node app.js
```

Then check out this link:  https://www.digitalocean.com/community/tutorials/api-authentication-with-json-web-tokensjwt-and-passport

Go to Step 9 Testing with Postman

- post to the "/signup" route to create a user
- "/login"
- test access to the secure route "/user/profile"

Note:  Changed the auth method to use a header with name "Authorization" and value "JWT <the long token value>", where the token is obtained from the "/login" service

e.g. "Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7Il9pZCI6IjVmN2ZhOTg2ODNhODExYzQ5NmNkMTMzZiIsImVtYWlsIjoiZXhhbXBsZUBleGFtcGxlLmNvbVxuIn0sImlhdCI6MTYwMjIxMTE3OX0.f70Gmre6jIjIcHfIMpkuT-2crN9UKKcRS7J4mo7LvFE"

