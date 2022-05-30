# Invitations
## Invitation Object
An organization object contain all of information of a organization.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `id` |    integer   |   Identify the organization. |
| `organization_id` | integer |   Identify the organization . |
| `user_id` |    integer   |   Identify the user that create the invitation. |
| `email` |    string   |   Who receive the invite. |
| `created_at` | timestamp with timezone | Creation date.  |
| `sent_at` | timestamp with timezone | Sending date.   |
| `registered_at` | timestamp with timezone | Registration date.   |
| `status` | string | Pending/Registered.   |
| `role_id` | integer | Role associates with the invitation.  |

## Get Invitation

#### HTTP Invitation Request
With this request you can get all information about your inviatation associate with specific organization.<br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`GET https://api.talentgarden.com/v1/organizations/:id/invitations`

<br></br> **Allow query parameters** <br></br> 

#### Query Users Parameters
You can use this parameter to filter the users or you can sort them.

Parameter | example
--------- | ---------
`status` | pending/registered


```shell
curl "https://api.talentgarden.com/v1/organizations/1/invitations" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "77",
            "organization_id": "1",
            "user_id": "16925",
            "email": "luigi.bianchi@ext.talentgarden.com",
            "created_at": "2022-03-13T15:30:45.972Z",
            "sent_at": "2022-03-13T15:30:49.495Z",
            "registered_at": null,
            "status": "pending",
            "role_id": 3,
            "role": "member"
        },
        {
            "id": "79",
            "organization_id": "1",
            "user_id": "16925",
            "email": "mario.rossi@talentgarden.com",
            "created_at": "2022-03-13T16:26:13.476Z",
            "sent_at": "2022-03-13T16:26:14.584Z",
            "registered_at": null,
            "status": "pending",
            "role_id": 3,
            "role": "member"
        },
        ...
    ],
    "pagination": {
        "page": 1,
        "per_page": 50,
        "total_elements": 30,
        "total_pages": 1
    }
}
```
## Create Invitation

#### HTTP Request
With this request you can create a new invitation.  <br></br>
**Only admin or owner of organization can use this endpoint** <br></br>
!!!**Attention**!!! <br>
If the email already exists in our database the invited contact will be automatically add to the organization  <br></br>
`POST https://api.talentgarden.com/v1/organizations/:id/invitations`

```js
const axios = require('axios');
const url = `https://api.talentgarden.com/v1/organizations/:id/invitations`
const config = {
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer YOUR_JWT'
  },
};
const data = {
    role: "member",
    user_id: 11412,
    email: "newinvitation@test.com",
} 
axios.post(url, config, data)
  .then((response) => { console.log(response) })
  .catch((error) => { console.log(error) })
```
> The above command returns JSON structured like this:

```json
 {
            "id": "77",
            "organization_id": "1",
            "user_id": "11412",
            "email": "newinvitation@test.com",
            "created_at": "2022-03-13T15:30:45.972Z",
            "sent_at": "2022-03-13T15:30:49.495Z",
            "registered_at": null,
            "status": "pending",
            "role_id": 3,
            "role": "member"
        },
```

#### Body Parameters
Parameter | Description
--------- | -----------
role | Role type: admin/member.
user_id | Who creates the invitation.
email | The email that receives the invite.

## Delete Invitation

#### HTTP Organizations Request
With this request you can remove members from your organization.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`DELETE https://api.talentgarden.com/v1/organizations/1/invitations/:inv_id`

```shell
curl -X DELETE "https://api.talentgarden.com/v1/organizations/1/77" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
 {
            "id": "77",
            "organization_id": "1",
            "user_id": "16925",
            "email": "anita.kristjansdottir@ext.talentgarden.com",
            "created_at": "2022-03-13T15:30:45.972Z",
            "sent_at": "2022-03-13T15:30:49.495Z",
            "registered_at": null,
            "status": "pending",
            "role_id": 3,
            "role": "member"
        }
```