# Rest API

## Faculties

### GET /api/v1/faculties

Gets all Faculties.

*Request body*

none

*Response*

```json
{
  "payload": [
    {
      "id": 1,
      "name": "Fakulteten för datavetenskap",
      "councils": [
        {
          "id": 1,
          "name": "Rådet för datornördar",
          "description": "Nerds R US, vi som capsar och dricker jolt cola",
          "facultyId": 1
        }
      ]
    },
    {
      "id": 2,
      "name": "Fakulteten för ngntingannat",
      "councils": [
        {
          "id": 2,
          "name": "Rådet för snickare",
          "description": "Hammare och spik!!!",
          "facultyId": 2
        }
      ]
    }
  ]
}
```

### POST /api/v1/faculties

Create a Faculty

*Request body*

```json
{
	"name": "Some Faculty name"
}
```

*Response*

```json
{
  "payload": {
    "id": 3,
    "name": "Some Faculty name",
    "updatedAt": "2017-04-25T14:18:50.857Z",
    "createdAt": "2017-04-25T14:18:50.857Z"
  }
}
```

### GET /api/v1/faculties/:id

Get the faculty with the provided id. This will return the Faculty and all councils.

*Request body*

none

*Response*

```json
{
  "payload": {
    "id": 1,
    "name": "Fakulteten för datavetenskap",
    "councils": [
      {
        "id": 1,
        "name": "Rådet för datornördar",
        "description": "Nerds R US, vi som capsar och dricker jolt cola",
        "facultyId": 1
      }
    ]
  }
}
```

### DELETE /api/v1/faculties/:id

Delete the faculty with the specified Id.

*Request body*

none

*Response*

```json
{
  "payload": 1
}
```

Payload is 1 on success and 0 on fail. Aka response is 0 if the Faculty was not found.

### PATCH /api/v1/faculties/:id

Change the information of a faculty.

*Request body*

```json
{
      "name": "Some Faculty name sdlasdk"
}
```

*Response*

```json
{
  "payload": 1
}
```

Faculty name is unique so if you try to edit a faculty with a name that already exists then respons is 500 internal server error.
Payload is 0 if faculty id was not found.

### Template

Description

*Request*

```json
{
  "year": ""
}
```

*Response*
