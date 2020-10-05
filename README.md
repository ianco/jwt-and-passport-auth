# How To Implement API Authentication with JSON Web Tokens and Passport

From:  https://www.digitalocean.com/community/tutorials/api-authentication-with-json-web-tokensjwt-and-passport

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
