Departments
=======================

Get departments
----------

* `GET /locations/64/departments.json` will return all departments

```json
[
  {
    "created_at": "2014-11-04T12:21:54+01:00",
    "updated_at": "2014-11-13T15:07:09+01:00",
    "id": 39164,
    "name": "asdasd",
    "color": "c4a5c8",
    "location_id": 64,
    "position": null,
    "creator_id": 493,
    "user_ids": [493]
  }
]
```

Get department
----------

* `GET /locations/64/departments/85015.json` will return the specified department.

```json
{
  "created_at": "2014-11-04T12:21:54+01:00",
  "updated_at": "2014-11-13T15:07:09+01:00",
  "id": 39164,
  "name": "asdasd",
  "color": "c4a5c8",
  "location_id": 64,
  "position": null,
  "creator_id": 493,
  "user_ids": [493]
}
```

Create department
--------------

* `POST /locations/64/departments.json` will create a new department from the parameters passed.

```json
{
  "visibility": "staff",
  "name": "Advanced training",
  "color": "d9be50",
  "user_selectable": true,
  "include_weekends": true,
  "position": 1
}
```

This will return `201 Created` with the current JSON representation of the department if the creation was a success.


Update department
--------------

* `PUT /locations/64/departments/83959.json` will update the department from the parameters passed.

```json
{
  "color": "c4a5c8"
}
```

Add users to department
--------------

put 'add_users' => 'departments#add_users'
put 'remove_users' => 'departments#remove_users'


* `PUT /locations/64/departments/83959/add_users.json` will add users to the department.

```json
{
  "user_ids": [1,2,3]
}
```

Remove users from department
--------------

* `PUT /locations/64/departments/83959/remove_users.json` will remove users from the department.

```json
{
  "user_ids": [1,2,3]
}
```

Delete department
--------------

* `DELETE /locations/64/departments/83959.json`
