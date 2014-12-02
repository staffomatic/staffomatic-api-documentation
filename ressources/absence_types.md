Absence Types
=======================

Get absence types
----------

* `GET /locations/64/absence_types.json` will return all absence_types

```json
[
  {
    "created_at": "2012-09-17T23:03:55+02:00",
    "updated_at": "2013-08-26T01:52:10+02:00",
    "id": 1,
    "visibility": "staff",
    "name": "Urlaub",
    "color": "d9be50",
    "user_selectable": true,
    "location_id": 64,
    "include_weekends": true
  }
]
```

Get absence type
----------

* `GET /locations/64/absence_types/85015.json` will return the specified absence.

```json
{
  "created_at": "2012-09-17T23:03:55+02:00",
  "updated_at": "2013-08-26T01:52:10+02:00",
  "id": 1,
  "visibility": "staff",
  "name": "Urlaub",
  "color": "d9be50",
  "user_selectable": true,
  "location_id": 64,
  "include_weekends": true
}
```

Create absence type
--------------

* `POST /locations/64/absence_types.json` will create a new absence from the parameters passed.

```json
{
  "visibility": "staff",
  "name": "Advanced training",
  "color": "d9be50",
  "user_selectable": true,
  "include_weekends": true
}
```

This will return `201 Created` with the current JSON representation of the absence if the creation was a success.


Update absence type
--------------

* `PUT /locations/64/absence_types/83959.json` will update the absence from the parameters passed.

```json
{
  "visibility": "schedulers",
  "color": "749ec1"
}
```

Delete absence type
--------------

* `DELETE /locations/64/absence_types/83959.json`
