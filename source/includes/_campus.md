# Campuses
## Campus Object
An booking object contain all of information of a campus.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `id` |    integer   |   Identify the campus. |
| `code` | string |   Campus code. |
| `name` |    string   |   Name of the campus. |
| `email` |    string   |   Email of the campus. |
| `address` | string | Address. |
| `city` |    string  | City. |
| `state`| string| State. |
|`currency`| string | The currency of the campus.|
|`square_meters`| json | Square Meters. |
|`desks`| boolean | Status of campus |
|`zip`| string | Type of campus |
| `created_at` | timestamp with timezone | Creation date  |
| `updated_at` | timestamp with timezone | Updated date   |
|`latitude`| double | Latitude campus |
|`longitude`| double | Longitude of campuses |

## Get Campuses

#### HTTP Campuses Request
With this request you can get the information about the campuses <br></br>
`GET https://api.talentgarden.com/v1/campuses`

```shell
curl "https://api.talentgarden.com/v1/campuses" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        "data": [
        {
            "id": 59,
            "code": "BCT",
            "name": "Talent Garden Barcelona Turrò",
            "email": "barcelona@talentgarden.com",
            "address": "Carrer Ramón Turró 169-A",
            "city": "Barcelona",
            "state": "CT",
            "country": "ES",
            "currency": "EUR",
            "phone": "+34910780234",
            "square_meters": 3010,
            "desks": 326,
            "zip": "08005",
            "created_at": "2021-02-11T11:36:14.416Z",
            "updated_at": "2021-02-11T11:36:14.416Z",
            "latitude": 41.3986556,
            "longitude": 2.2010949,
            "sender_name": "TAGBarca",
            "short_name": "Barcellona"
        },
        {
            "id": 23,
            "code": "BSC",
            "name": "Talent Garden Brescia",
            "email": "brescia@talentgarden.it",
            "address": "Via Cipro 66",
            "city": "Brescia",
            "state": "BS",
            "country": "IT",
            "currency": "EUR",
            "phone": "+390305537045",
            "square_meters": 700,
            "desks": 45,
            "zip": "25124",
            "created_at": "2014-10-09T12:18:53.000Z",
            "updated_at": "2019-12-04T10:50:05.000Z",
            "latitude": 45.5246252,
            "longitude": 10.2102432,
            "sender_name": "TAGBrescia",
            "short_name": "Brescia"
        },
        ...
    ]
}
```
#### Query Campuses Parameters
You can use this parameter to filter the bookings or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
|`code` | RMO | Return only campus with specified `code`.|


## Get Campuses by ID

#### HTTP Campuses Request
With this request you can get all information about specific campus.  <br></br>
`GET https://api.talentgarden.com/v1/campuses/:id`

```shell
curl "https://api.talentgarden.com/v1/campuses/48" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
    "id": 48,
    "code": "WIL",
    "name": "Talent Garden Vienna Liechtensteinstraße",
    "email": "vienna@talentgarden.at",
    "address": "Liechtensteinstraße 111-115",
    "city": "Wien",
    "state": "Wien",
    "country": "AT",
    "currency": "EUR",
    "phone": "+4312058183",
    "square_meters": 5000,
    "desks": 420,
    "zip": "1090",
    "created_at": "2018-11-28T17:14:57.000Z",
    "updated_at": "2020-03-06T15:35:48.000Z",
    "latitude": 48.2284578,
    "longitude": 16.3558698,
    "sender_name": "TAGWien",
    "short_name": "Wien"
}
```




