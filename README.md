# Hockey Rinks in Manitoba

This API will return a response containing public or outdoor hockey rinks in Manitoba, based upon the input parameters given. A search begins based on the input parameter `postalcode`.

## Endpoint(s)

`GET /rinks` List all hockey rinks in Manitoba

### Parameters

| Parameter   |  Type  | Required |        Description            |
|-------------|--------|----------|-------------------------------|
| `postalcode`| string | YES      | location to base search on    |
| `radius`    |   int  | YES      | search radius in km           |
| `number`    |   int  | NO       | number of hockey rinks to get |

## Sample Request

`https://api.hockeyrinks.org/rinks?postalcode="r3x0h9"&radius=10&number=2`

## Sample Response

``` json
{
    "southdale": {
        "rink":"southdale",
        "postal":"r3n0f3",
        "numRinks":2,
        "openingTime":"0900",
        "closingTime":"2000",
        "distance":6
    },     
    "keith bodley arena": { 
        "rink":"Keith Bodley Arena",
        "postalCode":"r3t2k1",
        "numRink":1,
	"openingTime":"0800",
	"closingTime":"2300",
        "distance":4
    },
    "winakwa": {
        "rink":"winakwa",
        "postal":"r2j4d1",
        "numRinks":3,
        "openingTime":"1000",
        "closingTime":"2200",
        "distance":7
    },
    "status":"OK"
}
```

## Response parameters

| Response     |  Type  |          Description                                       |
|--------------|--------|------------------------------------------------------------|
| `rink`       | string | the name of the hockey rink                                |
| `postal`     | string | the postal code of the hockey rink                         |
| `numRinks`   | int    | the number of hockey rinks available                       |
| `openingTime`| string | the opening time of the rink                               |
| `closingTime`| string | the closing time of the rink                               |
| `distance`   | int    | the distance to the rink from input location in kilometers |
