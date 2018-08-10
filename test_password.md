
## Create `account` Collection
Run MongoDB service, open cmd and type `mongo`, enter
```
> show dbs
admin
local

> use test (will create 'test' db)
switched to bd test 

> show collections
(no collection yet)

> db.createCollection("account")
{ "ok" : 1 }

> show collections
account
```
## Insert Test ID and Password
ID 1 : "test1" & Password 1 : "password"    
ID 2 : "test2" & Password 2 : "password"   

```
> db.account.insert({ "_id":"test1", "password":"$2a$10$6tGpszC5i7B.br12D9Qn0.ZFkUNz9MxUnowataw.XUyIeHQfLcsEe", "roles" : [ "USER", "ADMIN"] })
> db.account.insert({ "_id":"test2", "password":"$2a$10$6tGpszC5i7B.br12D9Qn0.ZFkUNz9MxUnowataw.XUyIeHQfLcsEe", "roles" : [ "USER", "SUPPORT"] })
```
**Notes:**
* `BCrypt` hash for string "password" => "$2a$10$6tGpszC5i7B.br12D9Qn0.ZFkUNz9MxUnowataw.XUyIeHQfLcsEe" 
* used `BCrypt` => intended for using in Spring application, you can use other hash
