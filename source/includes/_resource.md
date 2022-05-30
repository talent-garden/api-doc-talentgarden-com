# Resources
## Resource Object
An booking object contain all of information of a resource.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `campus_id` |    integer   |   Identify the campus of the resource.|
| `image_url` | string |   Identify the url of image. |
| `capacity` |  integer | Number of seats in the resource.  |
| `name` |    string   |   Name of the resource. |
| `description` |    string   |   Description of the resource. |
| `created_at` | timestamp with timezone | Date and time of book creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update. |
| `floor`| integer| Floor number|
|`privacy_level`| string | level of privacy inside the resource|
|`services`| json | Features resource |
|`available`| boolean | Status of resource |
|`type`| string | Type of resource |
|`organizations`| array | Which organization can see get the resources |
|`purchase_url`| string | url where to buy |

## Get Resources

#### HTTP Resources Request
With this request you can get the information about the resources, you need to be part at least one organization. <br></br>
Get your organization id from this [get roles](#get-roles) section.
Return ***only available*** resources for your organization <br></br> 
`GET https://api.talentgarden.com/v1/organizations/:id/resources`

```shell
curl "https://api.talentgarden.com/v1/organizations/1/resources" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "119",
            "campus_id": 53,
            "image_url": null,
            "capacity": 8,
            "name": "Meeting Room Mezzanine",
            "description": null,
            "created_at": "2019-06-06T11:55:40.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z",
            "floor": 0,
            "privacy_level": "Private",
            "services": {
                "natural_light": false,
                "hdmi_cable": true,
                "air_conditioned": false,
                "socket": true,
                "whiteboard": false,
                "monitor": "43"
            },
            "available": true,
            "type": "meeting_room",
            "organizations": [],
            "purchase_url": null
        },
        {
            "id": "120",
            "campus_id": 53,
            "image_url": null,
            "capacity": 5,
            "name": "Meeting Room Floor 2",
            "description": null,
            "created_at": "2019-06-06T12:01:44.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z",
            ...
        },
        {
            "id": "121",
            "campus_id": 53,
            "image_url": null,
            "capacity": 5,
            "name": "Meeting Room Floor 3",
            "description": null,
            "created_at": "2019-06-06T12:08:11.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z",
            ...
        }
    ]
}
```
#### Query Resources Parameters
You can use this parameter to filter the bookings or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
|`campus_id` | 53 | Return only resources with specified `campus_id`.|
| `capacity` | 4 | Return only resources with capacity 4.|
| `name` | MR01 | Return only resources with name equal MR01.|
| `floor` | 2 | Return only resources with floor equal to 2.|
| `privacy_level` | not_very_private | Return only resources with privacy_level 'not very private'.|
| `type` | meeting_room | Return only resources with type meeting_room.|


## Get Resources by ID

#### HTTP Resources Request
With this request you can get all information about specific book.  <br></br>
`GET https://api.talentgarden.com/v1/organizations/:id/resources/:resourceId`

```shell
curl "https://api.talentgarden.com/v1/organizations/1/resources/119" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
    "id": "119",
    "campus_id": 53,
    "image_url": null,
    "capacity": 8,
    "name": "Meeting Room Mezzanine",
    "description": null,
    "created_at": "2019-06-06T11:55:40.000Z",
    "updated_at": "2021-02-12T11:02:44.496Z",
    "floor": 0,
    "privacy_level": "Private",
    "services": {
        "natural_light": "FALSE",
        "hdmi_cable": "FALSE",
        "air_conditioned": "TRUE",
        "socket": "TRUE",
        "whiteboard": "FALSE",
        "monitor": "43"
    },
    "available": true,
    "type": "meeting_room",
    "organizations": [],
    "purchase_url": null
}
```

#### URL Request Parameters

Parameter | Description
--------- | -----------
id | The id of your organization.
resourceId | The resource id that you want.




