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

### GET /api/v1/faculties/:facultyId

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

### DELETE /api/v1/faculties/:facultyId

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

### PATCH /api/v1/faculties/:facultyId

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

## Councils

### GET /api/v1/faculties/:facultyId/:councilId

Get one council from a specific faculty. 

*Request body*

none

*Response*

```json
{
  "payload": {
    "id": 1,
    "name": "Rådet för datornördar",
    "description": "Nerds R US, vi som capsar och dricker jolt cola",
    "facultyId": 1,
    "studentPositions": 2,
    "phdPositions": 2,
    "councilInstances": [
      {
        "id": 1,
        "councilId": 1,
        "year": 2017,
        "positions": [
          {
            "id": 1,
            "councilInstanceId": 1,
            "year": 2017,
            "phd": false,
            "vacant": true
          },
          {
            "id": 2,
            "councilInstanceId": 1,
            "year": 2017,
            "phd": false,
            "vacant": true
          },
          {
            "id": 3,
            "councilInstanceId": 1,
            "year": 2017,
            "phd": false,
            "vacant": true
          }
        ]
      }
    ]
  }
}
```

### POST /api/v1/faculties/:facultyId

Create a council in a faculty. Id here is the Faculty id.

*Request*

```json
{
    "name": "Rådet för datornördar",
    "description": "Nerds R US, vi som capsar och dricker jolt cola",
    "facultyId": "1",
    "studentPositions": "2",
    "phdPositions": "2"
}
```

*Response*

```json
{
  "payload": {
    "id": 3,
    "name": "Rådet för datornördar",
    "description": "Nerds R US, vi som capsar och dricker jolt cola",
    "facultyId": 1,
    "studentPositions": 2,
    "phdPositions": 2,
    "updatedAt": "2017-04-25T14:35:27.123Z",
    "createdAt": "2017-04-25T14:35:27.123Z"
  }
}
```

### DELETE /api/v1/faculties/:facultyId/:councilId

Delete a council.

*Request body*

none

*Response*

```json
{
  "payload": 1
}
```

Payload is 1 on success and 0 on fail. Aka response is 0 if the Faculty was not found.

### PATCH /api/v1/faculties/:facultyId

Change the information of a faculty.

*Request body*

```json
{
    "name": "Rådet för datornördar 2",
    "description": "Nerds R US, vi som capsar och dricker jolt cola",
    "facultyId": "1",
    "studentPositions": "2",
    "phdPositions": "2"
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

## Employee/Staff

### GET /api/v1/faculties/:facultyId/:councilId

### Template

Description

*Request*

```json
{
    "name": "Rådet för datornördar",
    "description": "Nerds R US, vi som capsar och dricker jolt cola",
    "facultyId": "1",
    "studentPositions": "2",
    "phdPositions": "2"
}
```

*Response*
