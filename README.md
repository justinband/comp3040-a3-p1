# Hockey Rinks in Manitoba

This API provides information about public or outdoor hockey rinks in Manitoba based on a given postal code and search radius (in km). An integer can also be given to specify the number of hockey rinks to return. A search for hockey rinks will revolve around the postal code provided.

The hockey rink information given in the response will contain the number of rinks at a given location, the name of the rinks, and their operating hours. More about the response can be found in the [sample response](#sample-response) section.

## Endpoint(s)

Our API is very simple, as there is only one endpoint. This endpoint can be hit using a GET request.

`GET /rinks` List all hockey rinks in Manitoba

### Parameters

| Parameter   |  Type  | Required |        Description            |
|-------------|--------|----------|-------------------------------|
| `postalcode`| string | YES      | location to base search on    |
| `radius`    |   int  | YES      | search radius in km           |
| `minrinks`    |   int  | NO       | minimum number of hockey rinks to get |

## Sample Request

These are some sample requests to get information about hockey ricks for a given postal code and search radius.

```
https://api.hockeyrinks.org/rinks?postalcode="r3x0h9"&radius=10&number=1

https://api.hockeyrinks.org/rinks?postalcode="r2n2r9"&radius=3
```

A request can also be made with no parameters to get all the hockey rinks in Manitoba.

```
https://api.hockeyrinks.org/rinks
```

## Sample Response

The response is formatted in JSON. The response will contain information regarding where the hockey rink is located, the hours of operation, the number of rinks at the location, and the distance (in km) from the postal code sent in the request. 

The type definitions for the object can be seen [here](#response-object-type-definitions).

``` json
{
    "southdale": {
        "rink":"Southdale Community Centre",
        "postalcode":"r3n0f3",
        "numRinks":2,
        "openingtime":"0900",
        "closingtime":"2000",
        "distance":6
    },     
    "keith bodley arena": { 
        "rink":"Keith Bodley Arena",
        "postalcode":"r3t2k1",
        "numRink":1,
	"openingtime":"0800",
	"closingtime":"2300",
        "distance":4
    },
    "winakwa": {
        "rink":"Winakwa Community Centre",
        "postalcode":"r2j4d1",
        "numRinks":3,
        "openingtime":"1000",
        "closingtime":"2200",
        "distance":7
    },
    "status":"OK"
}
```

### Response Object Type Definitions

The type definitions for the response JSON object:

| Response     |  Type  |          Description                               |
|--------------|--------|----------------------------------------------------|
| `rink`       | string | the name of the hockey rink                        |
| `postalcode` | string | the postal code of the hockey rink                 |
| `numRinks`   | int    | the number of hockey rinks available               |
| `openingtime`| string | the opening time of the rink                       |
| `closingtime`| string | the closing time of the rink                       |
| `distance`   | int    | the distance to the rink from input location in km |
