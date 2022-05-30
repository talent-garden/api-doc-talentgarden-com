# Organizations
## Organization Object
An organization object contain all of information of a organization.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `id` |    integer   |   Identify the organization. |
| `hs_object_id` | integer |   Identify the organization into Hubspot system. |
| `netsuite_id` |  string | Identify the organization into Netsuite system. |
| `name` |    string   |   The name of the organization. |
| `address` |    string   |   The address of the organization. |
| `country` |    string   |   The country of the organization. |
| `state` |    string   |   The state of the organization. |
| `city` |    string   |   The city of the organization. |
| `phone_prefix` |   string   |   The phone prefix of the organization's number. |
| `phone_number` |   integer   |   The phone number of the organization. |
| `billing_email` | string | Billing email. |
| `pec_email` |   string  |Pec email. |
| `sdi_code` | string | The SdI is a public legal platform for issuing, transmitting and storing invoices. |
| `postal_code` | string | A postal code is a series of letters for the purpose of sorting mail. |
| `vat` | string | Vat number. |
| `fiscal_code` | string | Fiscal code. |
| `linkedin_url` | string | Linkedin url   |
| `created_at` | timestamp with timezone | Creation date  |
| `updated_at` | timestamp with timezone | Updated date   |
| `expires_at` | timestamp with timezone | Expired date   |
| `type` | string | Which kind of organization  |

## Get Organization

#### HTTP Organization Request
With this request you can get all information about own organizations.<br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`GET https://api.talentgarden.com/v1/organizations`

<br></br> **Allow query parameters** <br></br> 

#### Query Organizations Parameters
You can use this parameter to filter the organization or you can sort them.

Parameter |
--------- | ---------
`hs_object_id` |
`name` |  
`address` |
`state`|
`city`|
`postal_code`|
`vat`|
`fiscal_code`|
`phone`|
`pec` |
`type` |


```shell
curl "https://api.talentgarden.com/v1/organizations" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "1",
            "hs_object_id": "7036330761",
            "netsuite_id": null,
            "name": "Talent Garden",
            "address": "Via Ostiense 92",
            "country": null,
            "state": "Italy",
            "city": "Milan",
            "prefix_number": "+39",
            "phone_number": "3339999002",
            "billing_email": null,
            "pec_email": null,
            "code_sdi": null,
            "postal_code": null,
            "vat": null,
            "fiscal_code": null,
            "linkedin_url": null,
            "type": "company",
        }
    ],
    "pagination": {
        "page": 1,
        "per_page": 50,
        "total_elements": 0,
        "total_pages": 1
    }
}
```

## Get Organization by ID

#### HTTP Organization Request
With this request you can get all information about user selected by id.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`GET https://api.talentgarden.com/v1/organizations/1`

```shell
curl "https://api.talentgarden.com/v1/organizations/1" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
 {
            "id": "1",
            "hs_object_id": "5959981987",
            "netsuite_id": null,
            "name": "Talent Gardens",
            "address": null,
            "country": null,
            "state": null,
            "city": null,
            "phone_prefix": null,
            "phone_number": null,
            "billing_email": null,
            "pec_email": null,
            "code_sdi": null,
            "postal_code": null,
            "vat": null,
            "fiscal_code": null,
            "linkedin_url": null,
            "created_at": "2022-03-04T09:21:37.525Z",
            "updated_at": "2022-03-10T14:04:59.562Z",
            "expires_at": null,
            "type": "company",
        }
```

## Update Organization 

#### HTTP Organizations Request
With this request you can update the organization data.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`PATCH https://api.talentgarden.com/v1/organizations/1`

```shell
curl -X PATCH "https://api.talentgarden.com/v1/organizations/1" \
      -H "Authorization: Bearer YOUR_JWT"
       --data {"name": "Talent Garden"}
```

> The above command returns JSON structured like this:

```json
 {
            "id": "1",
            "hs_object_id": "5959981987",
            "netsuite_id": null,
            "name": "Talent Garden",
            "address": null,
            "country": null,
            "state": null,
            "city": null,
            "phone_prefix": null,
            "phone_number": null,
            "billing_email": null,
            "pec_email": null,
            "code_sdi": null,
            "postal_code": null,
            "vat": null,
            "fiscal_code": null,
            "linkedin_url": null,
            "created_at": "2022-03-04T09:21:37.525Z",
            "updated_at": "2022-03-10T14:04:59.562Z",
            "expires_at": null,
            "type": "company",
        }
```

## Get Organization Members

#### HTTP Organizations Request
With this request you can get all members include in your organization.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`GET https://api.talentgarden.com/v1/organizations/1/members`

```shell
curl  "https://api.talentgarden.com/v1/organizations/1/members" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
 {
    "data": [
        {
            "id": "101",
            "auth0_id": "auth0|5a373783e1ff174",
            "first_name": "Alessandro",
            "last_name": "Bianchi",
            "full_name": "Alessandro Bianchi",
            "email": "alessandro.bianchi@talentgarden.com",
            "phone_prefix": "+39",
            "phone_number": "3338882930",
            "created_at": "2015-10-29T09:07:29.000Z",
            "updated_at": "2021-07-01T14:12:37.916Z",
            "last_access_at": null,
            "last_access_campus": null,
            "role_id": 1,
            "role": "owner"
        },
        {
            "id": "102",
            "auth0_id": "auth0|5bfebb81d42c0ab6b8cb",
            "first_name": "Giovanni",
            "last_name": "Rossi",
            "full_name": "Giovanni Rossi",
            "email": "giovanni.rossi@talentgarden.com",
            "phone_prefix": "+39",
            "phone_number": "39123446777",
            "created_at": "2018-11-28T17:00:00.000Z",
            "updated_at": "2021-07-01T14:12:38.110Z",
            "last_access_at": "2021-10-13T12:18:04.000Z",
            "last_access_campus": 59,
            "role_id": 2,
            "role": "admin"
        },
        {
            "id": "103",
            "auth0_id": "auth0|5cc068de10e86693a8",
            "first_name": "Luca",
            "last_name": "Rossi",
            "full_name": "Luca Rossi",
            "email": "luca.rossi@talentgarden.com",
            "phone_prefix": "+39",
            "phone_number": "31203945197",
            "created_at": "2019-04-24T15:46:52.000Z",
            "updated_at": "2021-07-01T14:12:38.229Z",
            "last_access_at": null,
            "last_access_campus": null,
            "role_id": 3,
            "role": "member"
        },

    ],
    "pagination": {
        "page": 1,
        "per_page": 50,
        "total_elements": 3,
        "total_pages": 1
    }
}
```

## Update Organization Member Role

#### HTTP Organizations Request
With this request you can update the role of your members. You can choose admin or member role. The member cannot access to Connect platform, the admin have the access to Connect platform.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`PATCH https://api.talentgarden.com/v1/organizations/1/members/:user_id`

```shell
curl -X PATCH "https://api.talentgarden.com/v1/organizations/1/103" \
      -H "Authorization: Bearer YOUR_JWT"
       --data {"role": "admin" | "member" }
```

> The above command returns JSON structured like this:

```json
  {
            "id": "103",
            "auth0_id": "auth0|5cc068de10e86693a8",
            "first_name": "Luca",
            "last_name": "Rossi",
            "full_name": "Luca Rossi",
            "email": "luca.rossi@talentgarden.com",
            "phone_prefix": "+39",
            "phone_number": "31203945197",
            "created_at": "2019-04-24T15:46:52.000Z",
            "updated_at": "2021-07-01T14:12:38.229Z",
            "last_access_at": null,
            "last_access_campus": null,
            "role_id": 2,
            "role": "admin"
        },
```

## Delete Member

#### HTTP Organizations Request
With this request you can remove members from your organization.  <br></br> **Only admin or owner of organization can use this endpoint** <br></br>

`DELETE https://api.talentgarden.com/v1/organizations/1/members/:user_id`

```shell
curl -X DELETE "https://api.talentgarden.com/v1/organizations/1/103" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
  {
            "id": "103",
            "auth0_id": "auth0|5cc068de10e86693a8",
            "first_name": "Luca",
            "last_name": "Rossi",
            "full_name": "Luca Rossi",
            "email": "luca.rossi@talentgarden.com",
            "phone_prefix": "+39",
            "phone_number": "31203945197",
            "created_at": "2019-04-24T15:46:52.000Z",
            "updated_at": "2021-07-01T14:12:38.229Z",
            "last_access_at": null,
            "last_access_campus": null,
            "role_id": 2,
            "role": "admin"
        },
```