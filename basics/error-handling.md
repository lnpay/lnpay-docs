---
description: How to handle the errors
---

# Error Handling

You can expect all errors to have the same JSON response structure. For example here is what a **404** will look like: 

```text
HTTP/1.1 404 Not Found
Content-Type: application/json

{
  "name": "Not Found Exception",
  "message": "The requested resource was not found.",
  "code": 0,
  "status": 404,
  "type": "NotFoundException"
}
```

A **500** error may look like this: 

```text
HTTP/1.1 500 Internal Server Error
Content-Type: application/json

{
  "name": "Internal Server Error",
  "message": "Something very bad happened",
  "code": 0,
  "status": 500,
  "type": "InternalServerErrorException"
}
```

