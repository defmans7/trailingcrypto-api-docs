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

## Authentication
All API endpoints are Authenticated using `Bearer token Authorization`.
Each Protected Endpoint should have these header values in API calls:

|KEY  | VALUE |DESCRIPTION |
| ------------- |:-------------:| -----:|
|Authorization|Bearer `07cbefr5...`| Api Key to authenticate the requests|
| x-requested-with | XMLHttpRequest | This is to always receive response in JSON|
|Content-Type|application/x-www-form-urlencoded|In Post requests where you need to submit form data|


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
    "referred": 0
}
```
**Possible Values:**
provider: `email`, `google`, `facebook`
type: `TRIAL:1, FREE:2, PAID:3, TELEGRAM_ADMIN:4, BUSINESS:5`
referred: Count of users signed-up using current user referral link

### Configure Exchange API Keys

    POST /api/user/saveapikey
 
 **Parameters:**
 
|Key |Value  | Description|
|--|--|--|
|exchange  | binance |Exchange for which api key needs to be configured|
|key|binance api key|User needs to generate a new API key for each app or tool 
|secret| binance api secret|This is stored encrypted on trailingcrypto server and once configured won't be visible to user again for security reasons.
|uid|users uid| Only for exchanges which requires uid like CEX.IO
|password|api key passphrase| Only for exchange which requires passphrase like Kucoin.com|

**Response:**
```Javascript
{
    "status": true
}
```
