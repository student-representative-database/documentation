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

Create a Faculti

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

### Template

Description

*Request*

```json
{
  "year": ""
}
```

*Response*
