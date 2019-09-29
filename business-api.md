### Check Server Status

**Request:**

    GET /api/ping
    
**Response:**
```javascript  
{
   err:  false,
   msg:  "pong",
   time:  1569750557563
}
```

</br></br>
## Authentication
All API endpoints are Authenticated using `Bearer token Authorization`.
Each Protected Endpoint should have these header values in API calls:

|KEY  | VALUE |DESCRIPTION |
| ------------- |:-------------:| -----:|
|Authorization|Bearer `07cbefr5...`| This requires **Business Apikey**. Contact us for more info support@trailingcrypto.com|
| x-requested-with | XMLHttpRequest | This is to always receive response in JSON|
|Content-Type|application/x-www-form-urlencoded|In Post requests where you need to submit form data|

</br></br>

## User Profile Endpoints

### Get Profile Info
    GET /api/user/profile
**Response:**
```Javascript
{
    "id": "5d8f158b97f6971d342e75c3",
    "_id": "5d8f158b97f6971d342e75c3",
    "name": "Jennifer Lopez",
    "email": "jenni.lopez@gmail.com",
    "provider": "email",
    "type": 1,
    "apikey": 'sdfasdf33-asdfasdf3adf------'
    "referred": 0
}
```
**Possible Values:**

provider: `email`, `google`, `facebook`

type: `TRIAL:1, FREE:2, PAID:3, TELEGRAM_ADMIN:4, BUSINESS:5`

referred: Count of users signed-up using current user referral link


### Create a new user account

    POST /auth/email/register

 
 **Parameters:**
 
|Key |Value  | Description|
|--|--|--|
|name  | Emma Watson |User name|
|email|emma.watson@gmail.com|Must be unique, Can be fake/non-existent emails 
|password| securepassphrase| This can be used to manually login on users behalf
|preverified|1| Request authorized with business apikey can create pre-verified accounts otherwise user needs to verify their email address while registering

**Response:**
```Javascript
{
    "error": false,
    "msg": "User Successfully Created",
    "apikey": "923be3c8-10ec-4928-8460-a3cb3bc59060"
}
```
<br/><br/>

More Endpoints coming soon...
