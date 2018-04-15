# UserCenter

> A easy login/register/update user center.

> you can use it to finish register or login or update.

> You have to tell me that you need to use it
and I need to apply for a project id for you.

> Or you can use the code build your own user center.

> you can use it by token(need save in header or parameter)

> I can provide the log when you need it

# How to use it

> go [server](http://usercenter.stalary.com/swagger-ui.html)

> use /facade/project input your project name it will return:
```
"data": {
    "projectId": 1,
    "key": "5c175866c8"
  }
```
> please save projectId and key in your db or cache

## Token

> use /token/register to register，at least you input
```
{
  "password": "123456",
  "projectId": 1,
  "remember": false,
  "username": "hawk"
}
key: 5c175866c8
```
> if you need role definition，you can input role when you register，The default is 0

> it will return
```
"data": "c970209b8df0419c6712cb96f1fbc58dde9bedd233f3e79c069b4be1eeaafee4"
``` 
  
> you can get user information by token

> please use /facade/token   

> you need input your token and key.

> it will return 
```
"data": {
    "id": 1,
    "createTime": "2018-03-27T03:25:20.000+0000",
    "username": "stalary",
    "password": "abb8acd50d72f5961b7440b826cdaa3b2a9129b2",
    "projectId": 1,
    "remember": false
  }
```

> if you need get your project every user statistics

> you can use /facade/statistics

> you will receive
```
"data": [
    {
      "id": 1,
      "createTime": "2018-03-26T17:59:53.000+0000",
      "userId": 1,
      "loginCount": 5,
      "city": "[{\"address\":\"北京\",\"count\":5}]",
      "lateLoginTime": "2018-03-27T05:29:12.000+0000"
    },
    {
      "id": 2,
      "createTime": "2018-03-27T03:42:11.000+0000",
      "userId": 2,
      "loginCount": 7,
      "city": "[{\"address\":\"北京\",\"count\":6},{\"address\":\"济南\",\"count\":1}]",
      "lateLoginTime": "2018-03-27T05:23:19.000+0000"
    }
  ]
```

> The ways to login
- use /facade/token get user information save your cache
- use /facade/token when you need user information
                              
#### Developed by stalary and hawk