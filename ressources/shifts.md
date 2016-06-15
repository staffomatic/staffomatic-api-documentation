Shifts
=======================

Get shifts
----------

* `GET /schedules/1699/shifts.json` will return all shifts for specified schedule
* `GET /locations/64/shifts.json` will return all shifts for specified location
* `GET /shifts.json?from=2016-07-01T00%3A00%3A00%2B02%3A00&until=2016-08-01T00%3A00%3A00%2B02%3A00` will return all shifts for specified datetime range
* `GET /shifts.json?department_ids%5B%5D=214` will return all shifts for specified departments

```json
[
  {
    "created_at": "2015-02-17T17:58:45+01:00",
    "updated_at": "2015-02-17T18:02:01+01:00",
    "id": 3997004,
    "desired_coverage": 1,
    "note": "",
    "open_end": false,
    "full": false,
    "location_id": 64,
    "department_id": 47280,
    "ends_at": "2015-02-16T16:00:00+01:00",
    "starts_at": "2015-02-16T08:00:00+01:00",
    "schedule_id": 107739,
    "applied_user_ids": [ ],
    "assigned_user_ids": [ ],
    "cancelled_user_ids": [ ]
  }
]
```

Get shift
----------

* `GET /schedules/83959/shifts/3068100.json` will return the specified shift.

```json
{
  "created_at": "2015-02-17T17:58:45+01:00",
  "updated_at": "2015-02-17T18:02:01+01:00",
  "id": 3997004,
  "desired_coverage": 1,
  "note": "",
  "open_end": false,
  "full": false,
  "location_id": 64,
  "department_id": 47280,
  "ends_at": "2015-02-16T16:00:00+01:00",
  "starts_at": "2015-02-16T08:00:00+01:00",
  "schedule_id": 107739,
  "applied_user_ids": [ ],
  "assigned_user_ids": [ ],
  "cancelled_user_ids": [ ]
}
```

Create shift
--------------

* `POST /schedules/83959/shifts.json` will create a new shift from the parameters passed.

```json
{
  "starts_at": "2015-07-20T08:00:00+02:00",
  "ends_at": "2015-07-20T16:00:00+02:00",
  "open_end": false
  "department_id": 39164
  "desired_coverage": 2
  "note": ""
}
```

This will return `201 Created` with the current JSON representation of the shift if the creation was a success.


Update shift
--------------

* `PUT /schedules/83959/shifts/3068107.json` will update the schedule from the parameters passed.

```json
{
  "note": "sunshine is coming, don not forget your suncream!"
}
```

Delete shift
--------------

* `DELETE /schedules/83959/shifts/3068107.json`

will delete the shift specified and return 204 No Content if that was successful. If the user does not have access to delete the shift, you'll see 403 Forbidden.
