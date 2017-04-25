# Rest API

## Faculties

### GET /api/v1/faculties

Description

*Request*

```json
{
  "year": ""
}
```

*Response*

Gets all Faculties.

*Request body*

none

*Response*

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
