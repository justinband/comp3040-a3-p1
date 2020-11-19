# Hockey Rinks in Manitoba

This API will return a response containing public or outdoor hockey rinks in Manitoba, based upon the input parameters given.

## Endpoint(s)

`GET /rinks` List all hockey rinks in Manitoba

### Parameters

| Parameter   |  Type  |          Description          |
|-------------|--------|------------------------------|
| `postalcode`| string | location to base search on    |
| `radius`    |   int  | search radius in km           |
| `number`    |   int  | number of hockey rinks to get |

## Sample Request


## Sample Response

```
{
      "southdale":
	{
      	"rink":"southdale",
	"postal":"r3n0f3",
	"numRinks:"2",
	"openingTime:"0900"
	"closingTime:"2000"
	"distance":"6"
	},
	
	"winakwa":
	{
	"rink":"winakwa",
	"postal":"r2j4d1",
	"numRinks:"3",
	"openingTime:"1000"
	"closingTime:"2200"
	"distance":"7"
	},
      
      "status":"OK"
 }
```
