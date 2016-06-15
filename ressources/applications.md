Applications
=======================

Get applications
----------

* `GET /shifts/3068101/applications.json` will return all applications for specified shift
* `GET /locations/64/applications.json` will return all applications for specified location
* `GET /schedules/212625/applications.json` will return all applications for specified schedule
* `GET /applications.json?user_ids%5B%5D=493` will return applications for the specified user
* `GET /applications.json?from=2016-03-31T22%3A00%3A00.000Z&until=2016-06-29T22%3A00%3A00.000Z` will return applications between datetime range
* `GET /applications.json?department_ids%5B%5D=1` will return applications for the department's
* `GET /applications.json?state%5B%5D=accept` will return accept applications

```json
[
  {
    "created_at": "2014-12-01T17:30:25+01:00",
    "updated_at": "2014-12-01T17:30:25+01:00",
    "id": 3743340,
    "user_id": 493,
    "shift_id": 3068101,
    "schedule_id": 83959,
    "location_id": 64,
    "creator_id": 493,
    "state": "assigned",
    "shift_starts_at": "2015-07-21T08:00:00+02:00",
    "shift_ends_at": "2015-07-21T16:00:00+02:00",
    "department_id": 39164,
    "attended": true,
    "attend_starts_at": null,
    "attend_ends_at": null,
    "intermission": 0,
    "cancel_reason": null,
    "duration": 28800
  }
]
```

Get application
----------

* `GET /shifts/3068101/applications/1699.json` will return the specified application.

```json
{
  "created_at": "2014-12-01T17:30:25+01:00",
  "updated_at": "2014-12-01T17:30:25+01:00",
  "id": 3743340,
  "user_id": 493,
  "shift_id": 3068101,
  "schedule_id": 83959,
  "location_id": 64,
  "creator_id": 493,
  "state": "assigned",
  "shift_starts_at": "2015-07-21T08:00:00+02:00",
  "shift_ends_at": "2015-07-21T16:00:00+02:00",
  "department_id": 39164,
  "attended": true,
  "attend_starts_at": null,
  "attend_ends_at": null,
  "intermission": 0,
  "cancel_reason": null,
  "duration": 28800
}
```

Create application
--------------

You always need to specify the `do` parameter to execute the application state for the user.

| do      | result                |
|-------- |---------------------- |
| apply   | apply user to shift   |
| assign  | assign user to shift  |

* `POST /shifts/3068101/applications.json` will create a newapplications from the parameters passed.

```json
{
  "user_id": 493,
  "do": "apply"
}
```

This will return `201 Created` with the current JSON representation of the applications if the creation was a success.


Update applications
--------------

* `PUT /applications/3743342.json` will update the applications from the parameters passed.

```json
{
  "attended": true,
  "attend_starts_a": "2015-07-21T08:00:00+02:00",
  "attend_ends_at": "2015-07-21T16:00:00+02:00",
  "intermission": 0
}
```

if you want to change the `state` of an application, you can use following actions:

| do          | init state      | result state | Explanation                                                 |
|-----------  |---------------- |------------- |-----------------------------------------------------------  |
| accept      | `applied`       | `assigned`   | Accept an applied application                               |
| revert      | `assigned`      | `applied`    | Reverts an assigned application                             |
| cancel      | `assigned`      | `canceled`   | Cancel an application, you must provide a `cancel_reason`   |
| revoke      | `canceled`      | `assigned`   | Revokes an canceled application                             |
| supersede   | `canceled`      | `assigned`   | switch out the users, and assign the application            |

```json
{
  "do": "revert"
}
```

Delete applications
--------------

* `DELETE /applications/3743342.json`

**Note:** You can only delete `applied` applications.
