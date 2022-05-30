# Bookings
## Booking Object
An booking object contain all of information of a book.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `resource_id` |    integer   |   Identify the resource of the book.|
| `user_id` | integer |   Identify the user that book a resource. |
| `from` |  timestamp with timezone | Date and time of star of book.  |
| `to` |    timestamp with timezone   |   Date and time of finish book. |
| `created_at` | timestamp with timezone | Date and time of book creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update. |
| `organization_id` |   integer  | From which organization you did the booking. |

## Get Bookings

#### HTTP Request
With this request you can get all information about the all booking. <br></br>
`GET https://api.talentgarden.com/v1/bookings`

```js
const axios = require('axios');
const url = `https://api.talentgarden.com/v1/bookings`
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
axios.get(url, config)
  .then((response) => { console.log(response) })
  .catch((error) => { console.log(error) })
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": 64,
            "resource_id": "24",
            "user_id": "11152",
            "from": "2021-02-26T08:30:00.000Z",
            "to": "2021-02-26T09:30:00.000Z",
            "created_at": "2021-02-15T16:14:19.000Z",
            "updated_at": "2021-02-15T16:14:19.000Z",
            "organization_id": 1
        },
        {
            "id": 75,
            "resource_id": "24",
            "user_id": "11152",
            "from": "2021-03-09T08:30:00.000Z",
            "to": "2021-03-09T09:30:00.000Z",
            "created_at": "2021-02-15T17:31:26.000Z",
            "updated_at": "2021-02-15T17:31:26.000Z",
            "organization_id": 1
        }
        
    ]
}
```
#### Query Parameters
You can use this parameter to filter the bookings or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
`resource_id` | 24 or 24,25,26 | Return only bookings with specified `resource_id` or multiple `resource_id`.|
`user_id` | 1 | Return only bookings with specified `user_id`.|
`from`    | 2021-11-25T08:00:00.000Z | Return all bookings grater or equal of parameter
`to`      | 2021-11-25T08:00:00.000Z | Return all bookings less or equal of parameter
`sortby` | from | Return all bookings sorted by the fields of object.|

## Get Booking by ID

#### HTTP Request
With this request you can get all information about specific book.  <br></br>
`GET https://api.talentgarden.com/v1/bookings/:id`

```js
const axios = require('axios');
const url = `https://api.talentgarden.com/v1/bookings/64`
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
axios.get(url, config)
  .then((response) => { console.log(response) })
  .catch((error) => { console.log(error) })
```

> The above command returns JSON structured like this:

```json
{
    "id": 64,
    "resource_id": "24",
    "user_id": "11152",
    "from": "2021-02-26T08:30:00.000Z",
    "to": "2021-02-26T09:30:00.000Z",
    "created_at": "2021-02-15T16:14:19.000Z",
    "updated_at": "2021-02-15T16:14:19.000Z",
    "organization_id": 1
}
```

#### URL Parameters

Parameter | Description
--------- | -----------
id | The id of the book to retrieve.



## Create Booking

#### HTTP Request
With this request you can create a new book.  <br></br>
`POST https://api.talentgarden.com/v1/bookings`

```js
const axios = require('axios');
const url = `https://api.talentgarden.com/v1/bookings/64`
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
const data = {
    resource_id: 24,
    from: "2021-03-09T08:30:00.000Z",
    to: "2021-03-09T09:30:00.000Z",
    organization: 1,
} 
axios.post(url, config)
  .then((response) => { console.log(response) })
  .catch((error) => { console.log(error) })
```
> The above command returns JSON structured like this:

```json
{
        "id": 75,
        "resource_id": "24",
        "user_id": "11152",
        "from": "2021-03-09T08:30:00.000Z",
        "to": "2021-03-09T09:30:00.000Z",
        "created_at": "2021-02-15T17:31:26.000Z",
        "updated_at": "2021-02-15T17:31:26.000Z",
        "organization_id": 1
}
```

#### Body Parameters
Parameter | Description
--------- | -----------
resource_id | The id of the resource to book.
from | booking start date and time.
to | booking finish date and time.
organization_id | From which organization you do the booking. 


## Delete Booking by ID

#### HTTP Request
With this request you can delete a book with specific id.  <br></br>

`DELETE https://api.talentgarden.com/v1/bookings/:id`

```js
const axios = require('axios').default;
const url = `https://api.talentgarden.com/v1/bookings`
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
axios.delete(url, config)
  .then((response) => { console.log(response) })
  .catch((error) => { console.log(error) })
```
#### URL Parameters

Parameter | Description
--------- | -----------
id | The id of the book to delete.

