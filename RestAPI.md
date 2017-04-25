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

Change the information of a council.

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

### GET /api/v1/employees/

Get all Employees 

Request body*

none

*Response*

```json
{
  "payload": [
    {
      "id": 1,
      "firstName": "Fredrik",
      "lastName": "Olsson",
      "phone": "0123456-123",
      "email": "fredriko.olsson@gmail.com",
      "faculty": "data...",
      "position": "hkjhk",
      "profileUrl": "kllökök",
      "password": "$2a$08$7Vovn6bWqkzFnuAlOH2a6eXIUvbZwBLtuIawJPEvAptRtImkaoLq."
    },
    {
      "id": 2,
      "firstName": "Fredrik",
      "lastName": "Olsson",
      "phone": "0123456-123",
      "email": "fredriko.olsson@gmail.com",
      "faculty": "data...",
      "position": "hkjhk",
      "profileUrl": "kllökök",
      "password": "$2a$08$dDQOmp6I1idEmFkmYS2x7eSw4X/R78qJnujZkoVDa272lS5Dc.7SK"
    }
  ]
}
```

### GET /api/v1/employees/:employyeId

Get one Employee

Request body*

none

*Response*

```json
{
  "payload": {
    "id": 1,
    "firstName": "Fredrik",
    "lastName": "Olsson",
    "phone": "0123456-123",
    "email": "fredriko.olsson@gmail.com",
    "faculty": "data...",
    "position": "hkjhk",
    "profileUrl": "kllökök",
    "password": "$2a$08$7Vovn6bWqkzFnuAlOH2a6eXIUvbZwBLtuIawJPEvAptRtImkaoLq."
  }
}
```

### POST /api/v1/employees/

Create one Employee

Request body*

```json
{
    "firstName":"Fredrik",
    "lastName":"Olsson",
    "phone":"0123456-123",
    "email":"fredriko.olsson@gmail.com",
    "faculty":"data...",
    "position":"hkjhk",
   "profileUrl":"kllökök",
    "password":"dingDong"
}
```

*Response*

```json
{
  "payload": {
    "id": 2,
    "firstName": "Fredrik",
    "lastName": "Olsson",
    "phone": "0123456-123",
    "email": "fredriko.olsson@gmail.com",
    "faculty": "data...",
    "position": "hkjhk",
    "profileUrl": "kllökök",
    "password": "$2a$08$dDQOmp6I1idEmFkmYS2x7eSw4X/R78qJnujZkoVDa272lS5Dc.7SK",
    "updatedAt": "2017-04-25T14:42:32.590Z",
    "createdAt": "2017-04-25T14:42:32.590Z",
    "EmployeePositionId": null
  }
}
```

### DELETE /api/v1/employees/:employyeId

DELETE one Employee

Request body*

none

*Response*

```json
{
  "payload": 1
}
```

### PATCH /api/v1/employees/:employyeId

Edit one Employee

Request body*

```json
{
    "firstName":"Andras",
    "lastName":"Olsson",
    "phone":"0123456-123",
    "email":"fredriko.olsson@gmail.com",
    "faculty":"data...",
    "position":"hkjhk",
   "profileUrl":"kllökök",
    "password":"dingDong"
}
```

*Response*

```json
{
  "payload": 1
}
```

## User/Student

### GET /api/v1/users/

Get all Students 

Request body*

none

*Response*

```json
{
  "payload": [
    {
      "id": 1,
      "firstName": "Fredrik",
      "lastName": "Olsson",
      "phd": false,
      "phone": "0123456-123",
      "email": "fredriko.olsson@gmail.com",
      "faculty": "data...",
      "graduationYear": "1970-01-01T00:00:02.018Z",
      "password": "$2a$08$tKvF9bV/dsAfBox9C2JfSO2Q8Cctqs69vnGup6ibG/2NJoi2/ttPK"
    },
    {
      "id": 2,
      "firstName": "Andras",
      "lastName": "Balla",
      "phd": true,
      "phone": "0123456-123",
      "email": "andrasBalla@gmail.com",
      "faculty": "data...",
      "graduationYear": "1970-01-01T00:00:02.018Z",
      "password": "$2a$08$.rtHP0Jsq741AZ4HaDsz1ejtVZbYG78xEkVJP4iELGI/caEi183TC"
    }
  ]
}
```

### GET /api/v1/employees/:employyeId

Get one Student

Request body*

none

*Response*

```json
{
  "payload": {
    "id": 3,
    "firstName": "Pär",
    "lastName": "Popniten",
    "phd": false,
    "phone": "0123456-123",
    "email": "pär@gmail.com",
    "faculty": "data...",
    "graduationYear": "1970-01-01T00:00:02.018Z",
    "password": "$2a$08$qvMqnhJqguCX8bXt1qMDvew0PSXI1SqHulxmEPH2lEUA6yl00ZSx6"
  }
}
```

### POST /api/v1/users/

Create one Student

Request body*

```json
{
    "firstName":"Fredrik",
    "lastName":"Olsson",
    "phd":true,
    "phone":"0123456-123",
    "email":"fredriko.olsson@gmail.com",
    "faculty":"data...",
    "graduationYear":"2019-06-01",
    "password":"dingDong"
}
```

*Response*

```json
{
  "payload": {
    "id": 5,
    "firstName": "Fredrik",
    "lastName": "Olsson",
    "phd": true,
    "phone": "0123456-123",
    "email": "fredriko.olsson@gmail.com",
    "faculty": "data...",
    "graduationYear": "2019-06-01T00:00:00.000Z",
    "password": "$2a$08$s92iT5UmhCKE6M4QYMOtceaZVpmbKHZY6dWIRvl.KHcV.Pnf9kExy",
    "updatedAt": "2017-04-25T14:54:37.111Z",
    "createdAt": "2017-04-25T14:54:37.111Z"
  }
}
```

### DELETE /api/v1/users/:userId

DELETE one Employee

Request body*

none

*Response*

```json
{
  "payload": 1
}
```

### PATCH /api/v1/users/:userId

Edit one Employee

Request body*

```json
{
    "firstName":"Fredrik",
    "lastName":"Olsson",
    "phd":true,
    "phone":"0123456-123",
    "email":"fredriko.olsson@gmail.com",
    "faculty":"data...",
    "graduationYear":"2019-06-01",
    "password":"dingDong"
}
```

*Response*

```json
{
  "payload": 1
}
```

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
