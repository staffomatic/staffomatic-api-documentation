Special Days
=======================

Get special day
----------

* `GET /locations/64/special_days.json` will return all special_days for specified location
* `GET /special_days.json?from=2016-07-01T00%3A00%3A00%2B02%3A00&until=2016-08-01T00%3A00%3A00%2B02%3A00` will return all special_days for specified datetime range

```json
[
  {
    "created_at": "2012-12-06T09:21:11+01:00",
    "updated_at": "2012-12-06T09:21:11+01:00",
    "id": 1,
    "starts_at": "2012-01-01T00:00:00+01:00",
    "ends_at": "2012-01-01T00:00:00+01:00",
    "name": "Neujahrstag",
    "description": null,
    "color": "d9be50",
    "public_holiday": true,
    "show_in_schedule": true,
    "allow_absences": true,
    "all_day": true,
    "location_id": 64,
    "creator_id": 493
  }
]
```

Get special day
----------

* `GET /locations/64/special_days/85015.json` will return the specified special day.

```json
{
  "created_at": "2012-12-06T09:21:11+01:00",
  "updated_at": "2012-12-06T09:21:11+01:00",
  "id": 1,
  "starts_at": "2012-01-01T00:00:00+01:00",
  "ends_at": "2012-01-01T00:00:00+01:00",
  "name": "Neujahrstag",
  "description": null,
  "color": "d9be50",
  "public_holiday": true,
  "show_in_schedule": true,
  "allow_absences": true,
  "all_day": true,
  "location_id": 64,
  "creator_id": 493
}
```

Create special day
--------------

* `POST /locations/64/special_days.json` will create a new special day from the parameters passed.

```json
{
  "starts_at": "2012-01-01T00:00:00+01:00",
  "ends_at": "2012-01-01T00:00:00+01:00",
  "name": "Neujahrstag",
  "description": "But awesome Party!",
  "color": "d9be50",
  "public_holiday": true,
  "show_in_schedule": true,
  "allow_absences": true,
  "all_day": true,
}
```

This will return `201 Created` with the current JSON representation of the special day if the creation was a success.


Update special day
--------------

* `PUT /locations/64/special_days/83959.json` will update the special day from the parameters passed.

```json
{
  "allow_absences": false
}
```

Delete special day
--------------

* `DELETE /locations/64/special_days/83959.json`
