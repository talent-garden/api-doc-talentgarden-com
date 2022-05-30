# Pagination

It is almost never a good idea to return all resources of your database at once. Consequently, you 
should provide a pagination mechanism. In this case this mechanism is this json object.

```json
{
  "pagination": {
    "page": 1,
    "per_page": 50,
    "total_elements": 2,
    "total_pages": 1
  } 
} 
```

It's possible to use the parameters **per_page** and 
**page**, which are well-known from databases.

| Filed    |      Type      | Description |
|----------|---------------|----------------------------------------------|
| `per_page`| integer | The number of elements in one page.|
|`page`| integer | The current page.|
|`total_elements`| integer | Total number of events.|
|`total_pages`| integer | Total number of pages.|
