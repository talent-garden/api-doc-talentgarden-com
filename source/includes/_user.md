# Users
## User Object
An user object contain all of information of a user.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `id` |    integer   |   Identify the user. |
| `auth0_id` | string |   Identify the user into auth0 system. |
| `first_name` |  string | The first name of the user. |
| `last_name` |    string   |   The last name of the user. |
| `full_name` |    string   |   The full name of the user. |
| `email` |   string   |   The email of the user. |
| `phone_prefix` |   string   |   The phone prefix of the user's number. |
| `phone_number` |   integer   |   The phone number of th user. |
| `created_at` | timestamp with timezone | Date and time of user creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update data user. |
| `date_of_birth` | date | Date of birthday of the user. |
| `deleted` | boolean | True if the user was deleted. |
| `last_access` | date | Date of last access. |
| `last_access_campus` |    integer   |  Identify the campus. |
## Get Users

#### HTTP Users Request
With this request you can get all information about the all users.<br></br> **Only admin can use this endpoint** <br></br>
`GET https://api.talentgarden.com/v1/users`

```shell
curl "https://api.talentgarden.com/v1/users" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
      {
        "id":"22",
        "auth0_id":"auth0|123456789012345667",
        "first_name":"Mario",
        "last_name":"Rossi",
        "full_name":"Mario Rossi",
        "email":"mariorossi@tag.com",
        "phone_prefix":"+39",
        "phone_number":"2235641240",
        "created_at":"2014-10-08T10:20:10.000Z",
        "updated_at":"2020-11-16T12:15:42.889Z",
        "date_of_birth":"1984-08-28T00:00:00.000Z",
        "deleted":false,
        "last_access":"2014-10-08T10:20:10.000Z",
        "last_access_campus":"12",
      },
      ...
    ]
}
```
#### Query Users Parameters
You can use this parameter to filter the users or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
`email` | mariorossi@tag.it | Return only user with specified `email`.|
`full_name` | mario rossi| Return only user with specified `full_name`.|
`sort_by` | email | Return all bookings sorted by email.|
`sort_by_desc` | full_name | Return all bookings sorted by full name in descending order. |

## Get User by ID

#### HTTP Users Request
With this request you can get all information about user selected by id.  <br></br>
`GET https://api.talentgarden.com/v1/users/22`

```shell
curl "https://api.talentgarden.com/v1/users/22" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
        "id":"22",
        "auth0_id":"auth0|123456789012345667",
        "first_name":"Mario",
        "last_name":"Rossi",
        "full_name":"Mario Rossi",
        "email":"mariorossi@tag.com",
        "phone_prefix":"+39",
        "phone_number":"2235641240",
        "created_at":"2014-10-08T10:20:10.000Z",
        "updated_at":"2020-11-16T12:15:42.889Z",
        "date_of_birth":"1984-08-28T00:00:00.000Z",
        "last_access":"2014-10-08T10:20:10.000Z",
        "last_access_campus":"12",
      }
```

## Get My User

#### HTTP Users Request
With this request you can get all information about own user.  <br></br>
`GET https://api.talentgarden.com/v1/users/me`

```shell
curl "https://api.talentgarden.com/v1/users/me" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
        "id":"22",
        "auth0_id":"auth0|123456789012345667",
        "first_name":"Mario",
        "last_name":"Rossi",
        "full_name":"Mario Rossi",
        "email":"mariorossi@tag.com",
        "phone_prefix":"+39",
        "phone_number":"2235641240",
        "created_at":"2014-10-08T10:20:10.000Z",
        "updated_at":"2020-11-16T12:15:42.889Z",
        "date_of_birth":"1984-08-28T00:00:00.000Z",
        "last_access_at": "1970-01-20T03:08:08.323Z",
        "last_access_campus": 59
      }
```
## Create User

#### HTTP Users Request
With this request you can insert a new user.
  <br></br>
`POST https://api.talentgarden.com/v1/users`

#### Body User Parameters
You can use this parameter to create new user.

Parameter | example | 
--------- | ------- |
`first_name` | mario | 
`last_name` | rossi |
`email` | mariorossi@tag.it| 
`phone_prefix` | +39 | 
`phone_number` | 3391029463 | 
`date_of_birth` | 1995-10-10 |

##### Attention
The fields **first_name**, **last_name**, **email**, **phone_prefix** and **phone_number** are mandatory.

## Update User

#### HTTP Users Request
With this request you can get all information about specific user.
  <br></br>
`PATCH https://api.talentgarden.com/v1/users/:id`

```shell
curl -X PATCH "https://api.talentgarden.com/v1/users/:id" \
      -H "Authorization: Bearer YOUR_JWT"
```

#### Body Users Parameters
You can use this parameter to update data of specific user.

Parameter | example | 
--------- | ------- |
`first_name` | mario | 
`last_name` | rossi |
`email` | mariorossi@tag.it| 
`phone_prefix` | +39 | 
`phone_number` | 3391029463 | 
`password` | 123456#„«#“‘#789 |
`profile_image` | file.jpg | 

##### Attention
To update user's passwords it is necessary that the email field is not present.

To update your profile **image** you need to use **form-data** payload.


## Create Device

#### HTTP Users Request
With this request you can insert new user's device.
  <br></br>
`POST https://api.talentgarden.com/v1/users/devices`

```shell
curl -x POST "https://api.talentgarden.com/v1/users/devices" \
      -H "Authorization: Bearer YOUR_JWT"
      --data {"token": "sdkalsfkhalsfhjalncaukeab","manufacturer": "OnePlus","mac_address": "P1:28:57:13:J2:C4","model": "ONEPLUS A5000","product": "OnePlus5", "platform": "Android"}
```

#### Body Device Parameters
You can use this parameter to insert data of specific device.

Parameter | example | 
--------- | ------- |
`token`| sdkalsfkhalsfhjalncaukeabkcjabfkauevbaevkauefkaubvclaevbleaivbalv,
`manufacturer`| OnePlus|
`mac_address`| XX:XS:11:11:X1:X1|
`model`| ONEPLUS A5000|
`product`| OnePlus5|
`platform`| Android |

The **mac_address** parameter is **mandatory**

## Get Devices

#### HTTP Devices Request
With this request you can get all information about own devices.  <br></br>
`GET https://api.talentgarden.com/v1/users/:id/devices`

```shell
curl "https://api.talentgarden.com/v1/users/00000/devices" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns Array structured like this:

```json
[
      {
            "id": 1,
            "user_id": "00000",
            "token": "sdkalsfkhalsfhjalncaukeabkcjv",
            "manufacturer": "Iphone XX",
            "mac_address": "c6:00:00:00:f2:c4",
            "model": "XX",
            "product": "OnePlus5",
            "platform": "IOS",
            "created_at": "2021-04-28T07:59:04.146Z"
      }
]
```

## Get Roles

#### HTTP Devices Request
With this request you can get all information about your roles.  <br></br>
`GET https://api.talentgarden.com/v1/users/me/roles`

```shell
curl "https://api.talentgarden.com/v1/users/me/roles" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns Array structured like this:

```json
{
    "data": [
        {
            "organization_id": "1",
            "role": "member"
        },
        {
            "organization_id": "456",
            "role": "admin"
        },
        {
            "organization_id": "204",
            "role": "owner"
        }
    ]
}
```

